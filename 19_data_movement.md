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
