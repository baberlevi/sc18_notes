# HPC Sys Pros
https://github.com/HPCSYSPROS/Workshop18

## Chair intro
* need a way to incentivize writing
* didn't have a huge number of submissions
* artifacts (papers + scripts on github)
* dave clifton 19 chair

## Keynote (Bill Anderson - NCAR, storage engr):
### Best practices for managing 10's of TBs of data 
* ncar has > 100tb
* 38P scratch (short), 22P arch disk (med), 100P tape (long)
* centralized storage (instead of silod per pipeline step) has worked out well
* 'campaign' storage (between scratch & archive) i.e. drives not tape  
* mdtest, IOR for benchmarks
* run benchmarks before/after updates
* t10-pi (standard for data integrity)
* be careful w/ firmware upgrades
* looking into tools like starfish for metadata tracking
* don't backup, don't help users move data, no common tool/method to migrate data
* implemented enforced quotas on archive for first time this yr in 30 yrs

## spectre/meltdown impact as measured by xdmod (buffalo)
* clearly able to see impact of meltdown/spectre on graphs
* they run a number of benchmarks (nwchem, gamess, and some synthetic)
* IMB for mpi benchmark
* had results by mid Jan, and also sent to hpcwire
* these results are just from original patches, july patches show performance is now closer to original

## hybrid compliant cloud/campus hpc (notre dame)
* CUI compliance (NIST 800-171)
* evaluated HPC, all the regular issues
* separate AD via 'Ericom connect'
* using a vpc through their 'shared services' group
* user workstations are in the vpc vlan
* hpc components are on-site in locked racks
* door audit trail
* you can only get to cui hpc nodes through gov-cloud vpc

## cgroups on shared systems: purdue
* background: issue on login nodes w/ users using resources
* created cgroups_py to regular per user and runs in systemd
* script monitors who logins, and sets limits for the user
* only used for cpu/memory now. not io or network

## making containers easier: nvidia
* hpc container maker (tool name)
* https://github.com/NVIDIA/hpc-container-maker   
* building blocks give you an 'ideal' way to install dependencies
* very similar to concept I worked on a year ago (putting spack in singularity)
* have example recipes for easybuild & spack
* claims hpcm is more optimized for containers (1G vs 3G spack and 7G easy build for gromacs)

## deployiing bare metal and container based hpc w/ openhpc
* https://github.com/clusterworks/inception

## xCAT and masterless puppet for conf mgmt
* xCAT for dhcp, pxeboot, disk wipe at boot
* puppet config is part of the xcat config images
* old puppet system used templates, causing issues (training), now just copy in conf files
* version control all the conf files in git
* used to have issues with puppet master keeping up, not anymore
* completely stateless now, you reboot it gets the xcat image runs puppet and starts over
* onboarding new employees is easier
* main take away: go stateless, decentralize, and use git 

## stateless provisioning: argonne/univ colo
* originally tried chroot as a git repo, gets too big, secrets are a problem
* use systemd-nspawn (improved chroot) to create the fs
* inspec (compliance testing framework)

## next gen cluster mgmt arch (paul peltz lanl)
* distribute mgmt functions (dhcp, pxe, etc.)
* want to do rolling updates, tests, etc.
* scalable service nodes
* integrate automated testing
* their solution: kraken (a state engine for system automation)
* tracks state, and moves you from state you are in to state you want
* uses protobuf (eventually consistency model)
* modules do the work
* https://github.com/hpc/kraken    
