# Intel: compiling & tuning for performance using AVX512

slides: https://tinyurl.com/sc18avx512

test vm on GCE

### there are 7 subsets of avx512
* 2 exclusive to phi (pf, er)
* 2 common (f, cd)
* 3 exclusive to xeon (vl, vw, dq)

-xCORE-AVX512: skylake only
-xCOMMON-AVX512: skylake & knl
-xMIC-AVX512: knl only

intel v17 was very aggressive using 512 regs, then less agressive next versions  
v18 and newer need flag to enable

Notes:
* floating point up/down conversions are really bad for performance
* 'intel advisor' tool can help w/ vector optimization
* contiguous memory access can make a big difference
* array of struct vs struct of arrays
