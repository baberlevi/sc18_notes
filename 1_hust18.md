
# HUST18

## IO presentation:
* taccc blocks people for having IO too high
* ooops (optimal overloaded io protection system)
* intercepts io related functions in user app and 
* works on any posix fs (loaded as a module, and hijacks libc.so fopen)
* if io system is overloaded, insert a wait
* this can be compiled for other systems by putting response times in config file, and then creating a module
* has been tested on tacc, ncar, jhu
* also a tool to modify parms for jobs during runtime
* particularly helpful for openfoam & tensorflow (esp tf which issues an insane amt of filestat)
* (worked with Kevin @jhu)
* contact huang@tacc for deployment details
* question: what about integrating in slurm (it can throttle IO as a CR)

## Cview & NWPerf on Cascade (EMSL @PNNL)
* user & admin views
* using collectd to zmq and graphite
* cview - app, nwperf - web (more admin focused)
* nwperf (more user focused)
* https://github.com/EMSL-MSC/NWPerf
* https://github.com/EMSL-MSC/cview 
* also on dockerhub

## ReFrame : HPC regression tests in python
* a ci based testing system for hpc platforms
* perf logging w/ graylog
* sanity & perf tests
* https://github.com/eth-cscs/reframe 
* run nightly on piz daint, etc. via jenkins
* prod ~90min (nigthly), maint ~10min (man trigger after maint)
* question: somewhere to share tests? in favor, not in place yet

## Profiler tool (aaron welch - ornl)
* 80% of effort porting code to titan was on understanding/restructing code
* focusing on fortran/gcc, approach can be adapted to c/c++
* each time a program is compiled, output is dumped to a db
* when a user asks for profiling, it also is sent to db
* based off work on XALT
* MAP collects samples for profiling
