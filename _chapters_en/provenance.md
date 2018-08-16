---
permalink: "/en/provenance/"
title: "Provenance"
questions:
-   "FIXME"
objectives:
-   "FIXME"
keypoints:
-   "FIXME"
---

## Greg Wilson

Back in the Stone Age, Software Carpentry's lessons spent a few minutes
discussing data provenance:

- Include the string '$Id:$' in every source code file - Subversion would
  automatically fill in the revision ID on every commit to turn it into
  something like '$Id: 12345'.

- Print the script's name, the commit ID, and the date in the header of every
  output file (along with all the parameters used by the script).

It wasn't much, and I don't know how many people ever actually implemented it,
but it did allow you to keep track of which versions of which scripts had
generated which output files in a systematic way.

So here we are today in what I hope is research computing's Bronze Age, and I'm
curious: what do you all actually do to keep track of data provenance? What
tools or methods do you use to record which programs produced which output files
from which input files with which settings and parameters? I was excited about
the Open Provenance effort circa 2006-07 (https://openprovenance.org/opm/), but
it never seemed to catch on. What are people using instead?

## Dav Clark

I just kicked the tires on DVC, and it provides a nice mechanism for manually
tracking inputs and outputs along with code files - all hashed in YAML files.

If you want something automatic, the Gigantum client hooks into Jupyter's
notification system and notes the version, contents of the code cell, and
outputs including thumbnails for images (for at least R and Python). Since we
track the environment and use docker, you should have exceptional
reproducibility. Maybe we are actually in the early industrial age? I'm reminded
a bit of the poem about John Henry...

I've mentioned it a few times before, but there hasn't yet been any interest in
the list, which is a bummer.

But others have reported that it's very easy to get started, and you can find
info on trying the demo server or installing the open source client here:

http://gigantum.com

I'm happy to provide more pointers to our activity record format, but the
easiest way to get started would be to look at an example and browse the
activity tab in the client. The client is a completely different web interface
from Jupyter and is meant to generally replace what you'd do on the command
line. It's still just Git and Docker under the hood, and the activity record is
stored in Berkeley DB IIRC.

I'm happy to help folks dig in, and field any questions or criticism.

## Michael Zingale

we generate a source file at build time containing the metadata for our build
environment for our hydro codes, https://github.com/AMReX-Astro/ This captures
the git hashes and compiler versions and flags, build date, location, etc. and
stores it in output (and example of some of the information is appended below).
Runtime parameters are also included.  Still needed to do is to transfer this
info the image/PDF metadata for plots generated from our output.

the script that is invoked by make is here:

https://github.com/AMReX-Codes/amrex/blob/master/Tools/C_scripts/makebuildinfo_C.py

## Robin Wilson

A few years ago, some colleagues and I created a tool called recipy
(https://github.com/recipy/recipy) that automatically collects provenance
information from Python code. Basically you add a single line ('import recipy')
to the top of your code, and all inputs and outputs along with code version and
package information is automatically tracked in a database. The database can be
interrogated through a command-line interface or a web-based GUI. It was created
to try and be the 'magic', 'no-effort' solution that everyone wants - so they
just don't have to think about this stuff, but it's always recorded.

recipy works by hooking into Python's package importing mechanism, and then
patching packages to make them call recipy logging functions before they do
input/output. Currently we have support for some of the most common Python
libraries for data processing including numpy, pandas, matplotlib,
BeautifulSoup, lxml, GDAL, nibabel and others.

The first version of this code was created at the Software Sustainability
Institute Collaborations Workshop a few years ago, and it was then presented at
EuroSciPy 2015 (see https://www.youtube.com/watch?v=8tysix6Olgc&t=13s). Since
then there has been some development on it, but work has slowed down
significantly recently due to my poor health, and other commitments for the
other authors. I'm now in a situation where I'd like to work on it but don't
have any funding. If anyone is interested in this being further developed and
wants to contribute some development effort or even some funding then please get
in touch!

## Dustin Lang

Down at LegacySurvey.org headquarters, where we are measuring a billion stars
and galaxies (in ~100,000 "naturally parallel" chunks of sky), we record the
version numbers of the major python packages in use in all of the output files.
The top-level python script lives in a tagged live git repo, so we use 'git
describe' for that one, and then most of the rest of the packages are provided
by an idiosyncratic conda-based package management system at the supercomputing
center we use (NERSC.gov).  All in all, it's not pretty.  But you asked what's
happening out in the trenches!  We also log all environment variables and
command-line arguments to a text file per chunk-of-sky, and all the launch
scripts live in our top-level git repo; I would prefer to capture more of that
directly to the output files, but [boring reasons].

Format-wise, our major output files are in FITS format, the ancient standard in
astronomy, which has a key-value header attached to each image or table output.
We also use a nice trick for checksumming: we use the write-to-memory mode of
the fitsio library to write all outputs to memory, compute a sha256 sum on the
in-memory data file, then write it to disk, and then at the end of the run, we
write all the sha256 sums to disk.  This allows us to detect silent i/o failures
(posix-violating not-supposed-to-happen, but we have seen it happen on our
lustre fs) where we write to disk and then checksum the corrupted data.

Three outstanding problems in our setup:

1.  we depend on a lot of input data sets (~4 distinct data sets, 1e5ish files
    and many TB), and versioning those is something of a pain.

2.  our code can checkpoint its state and resume later, but there is no
    guarantee that we are resuming with the same version of the code.  (And
    indeed, often we want to be using a newer version of the code that fixes
    some bug, but we don't want to discard all the correct computation we have
    done up to that point.)  Probably we should just re-log all the versions
    each time we resume.

3.  we log the versions of the code we're *supposed* to be using, but it's
    possible (via PYTHONPATH, eg) that some other version of a package is
    getting imported; we should log full paths or package __version__ strings or
    whatever.  Similarly, we use 'git describe' to get the top-level code
    version, but (gasp) someone could be running uncommitted code in production
    (yeah, I know, it makes me feel sick too).

## Doug Latornell

This may or may not be off-topic. The ocean modeling folks I work with are picky
about the word "data" (which they reserve for measured observations from
instruments in the water). My comments here are about provenance of model run
results. Of course, in a more generally computational interpretation of the word
"data", model results are data too.

Built into one of the tools we built for running the NEMO ocean model in a
reproducible fashion is code that records information about the revisions of all
of the repos involved in the particular model run. That information is stored in
text files that travel with the model results. They are created when the run is
being prepare for submission to the HPC queue, and are stored with the run
results so that it takes an effort of will to separate them from the results
files (not fool-proof, but generally effective). An example of the contents of
such a file is:

```
skookum:07aug18$ cat SS-run-sets_rev.txt
changset:   1880:f7eb987b308b82b00043fdaf8def92b6e0f02ee6
tag:        tip
user:       Susan Allen <sallen@eos.ubc.ca>
date:       Mon Jun 18 16:10:06 2018 -07:00
files:      v201702/hindcast/namelist_smelt_cfg_highzoo v201702/hindcast/runfiles/13nov14hindcast_alpha.yaml
description:
alpha test for hindcast with new file_def.xml
uncommitted changes:
M v201702/nowcast-green/iodef.xml
skookum:07aug18$
```

The code that does this can be found in
https://bitbucket.org/salishsea/nemo-cmd/src/default/nemo_cmd/prepare.py#lines-1039
We use Mercurial, so that is the VCS system that it is implemented for, but
something similar should be possible for Git and Subversion. A Git
implementation is on my todo list, but not at a high enough priority to ever get
any effort.

Repo revision files like that are one aspect of the collection of files about
the model run that we preserve with the model results. There are several other
files that describe the model run and its inputs that also accompany the run
results files. The good news is that those kinds of files are text files so they
are small compared to model results files (no good reason to delete them) and
easily human readable. The goal is to have everything we need in a results
directory to be able to reproduce the run at a later time, and we have good
indications that we are successful in that. Below is the file list from a 1-day
model run:

Doug

```
skookum:07aug18$ ls -1
07aug18nowcast-green.yaml
BoundaryBay.nc
CampbellRiver.nc
CherryPoint.nc
domain_def.xml
field_def.xml
file_def.xml
FridayHarbor.nc
FVCOM_W.nc
grid_rev.txt
HalfmoonBay.nc
iodef.xml
layout.dat
namelist_cfg
namelist_ref
namelist_smelt_cfg
namelist_smelt_ref
namelist_top_cfg
namelist_top_ref
Nanaimo.nc
NeahBay.nc
NEMO-3.6-code_rev.txt
NEMO-Cmd_rev.txt
NEMO_Nowcast_rev.txt
NewWestminster.nc
ocean.output
output.namelist.dyn
output.namelist.sme
output.namelist.top
PatriciaBay.nc
PointAtkinson.nc
PortRenfrew.nc
rivers-climatology_rev.txt
SalishSea_03123360_restart.nc
SalishSea_03123360_restart_trc.nc
SalishSea_1d_20180807_20180807_dia2_T.nc
SalishSea_1d_20180807_20180807_grid_T.nc
SalishSea_1d_20180807_20180807_grid_U.nc
SalishSea_1d_20180807_20180807_grid_V.nc
SalishSea_1d_20180807_20180807_grid_W.nc
SalishSea_1d_20180807_20180807_ptrc_T.nc
SalishSea_1h_20180807_20180807_grid_T.nc
SalishSea_1h_20180807_20180807_grid_U.nc
SalishSea_1h_20180807_20180807_grid_V.nc
SalishSea_1h_20180807_20180807_grid_W.nc
SalishSea_1h_20180807_20180807_ptrc_T.nc
SalishSea_2h_20180807_20180807_dia1_T.nc
SalishSeaCmd_rev.txt
SalishSeaNEMO.sh
SandHeads.nc
SandyCove.nc
Slab_U.nc
Slab_V.nc
solver.stat
Squamish.nc
SS-run-sets_rev.txt
stderr
stdout
tides_rev.txt
time.step
tools_rev.txt
tracers_rev.txt
tracer.stat
VENUS_central_gridded.nc
VENUS_central.nc
VENUS_delta_gridded.nc
VENUS_east_gridded.nc
VENUS_east.nc
Victoria.nc
WoodwardsLanding.nc
XIOS-2_rev.txt
XIOS-ARCH_rev.txt
skookum:07aug18$
```
## Damien Irving

I've written a Data Carpentry lesson on data provenance, which makes use of a
very simple package I've written called cmdline-provenance:

- Lesson: https://data-lessons.github.io/python-aos-lesson/09-provenance/index.html
- Package: http://cmdline-provenance.readthedocs.io/en/latest/

## Robert M. Flight

I've been doing a bunch of work where we really want to track which version of
things were used, and also the basic methods, and finally what input data was
used.

What I ended up implementing was a bunch of JSON metadata.

At raw file copying, a JSON metadata file gets generated with the original
location, new location, and the SHA256 checksum of the original data.

After a transformation step, more metadata is extracted during processing,
including which version of the software did the conversion. This gets added to
the raw copying metadata.

A final processing occurs using an custom R package, and for that package, I
have a git hook that increments the package version on every commit, so every
commit has a corresponding version number. Also, because it is a local custom
pkg, if I have a clean git repo, the git SHA is added to the pkg metadata at
install. During processing, I have a function that gets the parent pkg metadata,
including the SHA if it exists, and adds it to another JSON metadata file. It
also takes the main data class object that gets processed, strips the data bits,
and writes a JSON representation of the main class (so all the methods are
encoded as JSON), which also becomes part of the JSON metadata, in addition to
saving a binary representation of the class with the data attached. All this is
added to the previously existing metadata.

Ideally, I would be capturing the version numbers for all of the pkg's that my
code imports as well, but I haven't gone that far.

## Alex Savio

I have been using and also contributed a bit to Nipype a few years ago, we use
there the W3C Prov Data Model:

https://nipype.readthedocs.io/en/latest/devel/provenance.html

http://prov.readthedocs.io/en/latest/index.html

https://www.w3.org/TR/prov-dm/

## Chris Gates

This is a wonderful thread and thanks to all. In bioinformatics, the web of
dependencies is so dense and brittle, that beyond provenance there is increasing
interest in sharing compute environments in a reproducible way using automated
workflow frameworks and virtualization/containerization. In effect, the
downstream users saying "please document your provenance - and (since I'm too
impatient to read it) also please gather dependent data/programs/workflows into
a an environment that I would actually use". This idea is, of course, distinct
from provenance per se, so I don't want to muddy this thread - but it seems
related, and worth mentioning.

## Thomas Morrell

I think providing a environment that others can use is an important part of the
provenance question.  It’s one thing to document dependencies, but in order to
really make sure they are correct and complete you need to test them in a
compute environment.  https://mybinder.org/ is a great and free example of this
setup.  If you provide dependencies in standard text files, everyone can re-run
your results (in python, R, others) in a virtual compute environment. Showing
researchers the benefits of capturing provenance information is an important
part of driving adoption.

## Exercises {#s:provenance-exercises}

FIXME

{% include links.md %}
