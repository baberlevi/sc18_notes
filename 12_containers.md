# Containers in HPC BoF

## lightning talks

### (guy right before ECP)
* one concept is to not care that containers run as root (rebuild the nodes) 
    * crowd generally not receptive to this (for good reason)
    * what about filesystem permissions
    * what about ability to update bmc/firmware from root
    * putting nic in promiscuous mode

### ecp software build on spack
built a container on spack
https://e4s.io , 1PM tomorrow
http://oaciss.uoregon.edu/ecp/
https://xsdk.info/

### NCAR
* https://github.com/ncar/inception
* containers curated by admin team for now
* mount namespaces only
* scheduler integrated

## Panel
* SPIN from NERSC built on docker and rancher
* https://docs.nersc.gov/services/spin/getting_started/

### Container performance:
* Kurtzer: need a better way to transfer abis from kernel to user space (for perf & portability)
* Kurtzer: seeing some latencies added through addditional namespaces (i.e. network impacting HFT)
* Question: what about non internet connected computers? Also, tradeoff between portability & performance

