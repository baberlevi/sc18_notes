# Spack BoF

## Spack ENV
* out now, we need to start trying that out

## Spack Stacks (on the way)
* build on env to enable more automated deployment at hpc centers
* better dependency resolution
* support for language levels (e.g. CXX14, OpenMP5)
* I talked to the lead dev on this quite a while after the bof. He's going to add a slack channel for it, could use help with some features.
* I asked about adding compiler flags to the combinatorial spec, he & Todd agreed we should do that

## Binary packages
* working on this as a new feature, will be on s3 after CI build 
* s3 build will also host a spack mirror

## exascale use
Spack is the delivery platform for ECP (exascale compute project)
Already being used by xSDK team

## Configs
* contribute configs to spack-configs repo
* done: https://github.com/spack/spack-configs/pull/7

## contributions
* ISU is #3 contributor

## maintenance
* discussing stale bot

## working to move a lot of the infrastructure to kubernetes on AWS w/ Kitware's help:
* https://cdash.spack.io/viewProjects.php

## ORNL: OLCF
* were using in-house developed homebrew clone smithy, person who created it left
* using a tiered build system, lowest tier os compiler only, higher tiers reference lower builds as unbuildable external packages
* keep configs and list of specs in git, ci/cd auto build manifests on each login node
* ~1300 repeatable explicit builds, 75 titles, 11 olcf machines
* interested in spack chains 
* want to build spack in containers later
### module naming:
* users prefer minimal hashless modulefile names 
* carefully build to prevent collissions
* expose only modules for explicitly installed specs
* lmod makes this easier, but future may expose all with suffixes
* users just interact with module files (not spack directly)

## LRZ spack use on SuperMUC-NG
* about 150 recipes, result in ~200 modules
* takes about 2 days to rebuild all the packages
* working on some ways to parallelize the build better (using hashes in makefiles as targets)
* cluster is heterogeneous arch, works well for that

## CEA use for development
* lots of complex deps
* multiple sites, multiple linux distros, and isolated networks
* using tcl modules
* future plans: binary distros, all layers (sys, middleware, product) handled by spack

## Questions
* parallel builds (across nodes), yes - on the roadmap
* conda integration? maybe after binaries
* question about using the API - maybe more later

