# workshop on opensource in hpc

## xBGAS (boston univ)
* start with rv64 xBGAS arch
* BRISC-V design infrastructure
* next phase converged network on chip

## system-level design: luca carloni - columbia
* mostly focued on heterogeneous high performance embedded systems
* biggest challenge: complexity of system integration
* embedded scalable platforms: architecture + methodology (DAC 2016)

## keynote: nick malaya - amd
* moore law dead, dennard scaling dying, open source alive ?
* architectures are exploding
* how to use opensource to help with portability, maintainability, etc.
* oss is not free: needs lots of commitments
* SW & arch work & move together (david keyes - algorithmic adaptations to extreme scale computing)
* full open source is needed for scientific computing (too many black boxes)
* incentives are not aligned (doesn't get you tenture/promoted)
* HIP (c++ interface to cuda api), portable to amd/rocm and nvidia/cuda
* trying to get performance portability
* starting to think about how to integrate things like HIP in openmp/openacc
* https://github.com/ROCmSoftwarePlatform/rocALUTION
* docs, bug tracking & fixing need better incentives
* build for science/$ not flops
* big barrier & language gap betweeen app devs and hardware designers (vendors)
* co-design should be like open source software
* problems are optimized for hardware, how do we flip it instead ?
### key questions:
* solving the attribution problem
* line between performance / portability
* standard api's as an answer?
* learn more about perf across hardware / software
* make co-design more open
