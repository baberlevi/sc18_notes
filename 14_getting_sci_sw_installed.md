# Getting Scientific Software installed BoF

## Intro:
* max perf, reliable, reproducible
* sucks for everyone, centers large & small
* until recently, little collaboration across centers

## available tools:
* easybuild
    * experimental support for docker & singularity images
    * integration with openhpc
    * supports tensorflow install
* spack
    * more packages than easybuild
    * python2/3 (easybuild 2 only)
    * more architectures
    * more open license (now)
    * ISU on their slide about sites using it :)
* conda/nix/guix
    * conda - binaries (adds windows, but not other archs), targets end users
    * nix - not focused on scientific sw
    * guix - ?
* singularity
    * good features added in 3.0
* hpc container maker (new player) - nvidia thing
    * spits out singularity or docker
    * challenges for multi-node mpi runs
    * performance ?
* openhpc
    * has some prebuilt, and includes easybuild/spack

## lmod/xalt:
* lmod: all the usual features
* xalt: tracks what exe and libs are used
    * runtime & library usage
    * very lightweight so can be on almost all the time
    * scalar progs are sampled to prevent being overwhelmed
    * not a performance tool
    * site configurable
    * can track package use in R, matlab, and python
    * xalt.readthedocs.io


