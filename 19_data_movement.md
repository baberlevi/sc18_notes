# data movement & provenancce

## dacman
* no provenance
* researchers hesitant to update data
* end up with lots of copies

### some tools currently used
* python filecmp
* diff (*nix or git)
* not sscalable, not parallelized

## dacman - new tool from lbl
* not a vcs
* scales on hpc
* query manager keeps a cache, cache misses invoke change tracker, and check the fs
* uses a bi-directional hash index
* indexes are saved on the fs (not just mem)
* there are file & data comparators (md vs content)
* cache is similiar to staging in git
* data scan to get teh list of files in a dir happens before parallelization (seems like a bottleneck?)
* some testing on Cori, results in paper
* amount of change doesn't impact perf, but file count & size does
* part of deduce project (deduce.lbl.gov)
* https://github.com/dghoshal-lbl/dac-man 
* b/c index is on FS, they are dependent on fsio limits 

## stacker - auto movement of data
* ml based decision for data placement
* ~25% reduction in io time
* https://github.com/pradsubedi/Stacker.git
* future work: write path (current focused on read)

## glenn lockwood: nersc, a year in the life of a PFS
* ran instrumented benchmarks daily 
* nersc, alcf, mira, edison, cori
* gpfs, lustre
* used 'tokio' framework to get consolidated data from:
    * darshan
    * slurm
    * lmt
    * ggiostat
* 366 days, 12K runs, 220 metrics per job
* not of insight from aggregate data
* heatmap by time
* vertical (transient) horizontal (systemic IO problem)
* intersection of sma & global mean correlated to OS updates & lustre client bugs
* also tried 14SMA vs 49SMA
* bandwidth contention: one big cause
* cpu load on lustre OSS's during lustre bug time period caused a problem, later high CPU correlated to high true usage
* these methods work well for long-term issues, but not short
* iops & BW top2
* then open, stat, load, MD load, fullness
* https://github.com/nersc/pytokio
* (data is avail too if you want to use it for more analysis)
