# open compute project

## background on the project:
* 200 corp members
* 6K participants
* lots of supplier growth
* about 10 projects w/ subgroups
    * networking one of the bigger groups
    * storage just launched
    * modular DC's
    * openrmc (rack mgmt)
    * open sys firmware (openbmc)
    * etc. (all on web, each has a wiki/charter)
* global summit in march - call for papers, looking for new ideas
* encouraging even closed source vendors to provide documentation, but keep the IP
* looking for case studies, whitepapers, etc.
* recoginition for manufacturers - some rfps asking for this
* colo facilities are also recognized
* global summit: march 14-15, call for participation ends nov 30

## hpc specific:
* dealing a lot with power now (rack & server)

### whitney zhao: hardware engineer at facebook:
#### yosemite
* Yosemite v2: single socket system
* big basin: ml hardware
* both are in production and designed contributed to ocp
* yosemite: designed for perf/watt
* m.2 carrier card with built in pcie switch for large flash capacity
* earlier, to remove 1/4 servers in the chassis, they had to all be off. now only 1 server down at a time
* using skylake-d, 18cores, 4ipc (86w)
* majority of their workload now on 1 socket for best perf/watt
* 128 servers (yosemitev2) in a single rack, v1 was 192
#### big basin
* search, ads, newsfeed, etc. all using ML now
* started experimenting with gpu in 2012, then used HP in '13, and their own design by '15
* current design: 3U, 8x v100, nvlink (2u main box w/ the gpus then a cabled smaller stack on chassis for cpu?
* moving to skylake, cuda9, 100Gbps network
* use for image classification & language translation

### siamak tavallaei, microsoft
* want a common form factor
* all kinds of new hardware, fpga, asic, npu, tpu
* hard for rest of community to respond at the volume they need
* hard to compare & test proprietary solutions
* want a pcie mezz module: high density, flexible, space for accellerators and cooling
  
### inspur: new design: alfie lew
* 16x PCIe expansion box (being used by baidu)
    * gpu or fpga
    * 16x 16lane possible w/ pci switches
    * hooked up to an ocp compute box, with various configurations (1 compute node to all 16, or multi compute nodes, or multi socket servers)
    * quad socket up to 40% better in some instances
* 8x nvlink
    * 1-2 cpus, 8 nvlink connected v100s
    * 3U to let in lots of air
* 8-16x nvlink
    * 4U
* starting to think about other cooling options for future designs, but so far fine w/ air
* really about full rack power density, 17kW air fine, 35kW pushing it, 80kw, need water/immersion
* rack of ocp gear at booth #1235

### iceotope:
* presentation on liquid cooling based modular data centers (shipping containers)
* sub atmospheric pressure in the 'pod' ensures leaks don't cause issues
* part of euroexa project
