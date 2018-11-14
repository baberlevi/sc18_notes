# XSEDE all campus champions meeting

## open discussion on non-traditional users
* approach users slower
* make sure there's a clear end

## frontera
* new tacc cluster
* coming online in spring, full production by summer
* expect to be in top 10
* potential phase2 with 10x capabilities, ~2025
* xeon platinum, higher clock rates, 65kw cabinets, liquid cooling
* very similar arch to stampede2, just faster
* found in reality, higher clock speeds are better, theoretical on lower freq rarely achieved
* have focused a lot more on storage this time, to be sure it is performant enough
* users rarely stress bw, capacity, and iops
* 3 separate FS, flash requires i/o perf justification, then RR into 3 divided into pools to limit failure domain
* even though 50-60PB, will split it up into smaller FS so no single one > 3B files
* nvidia for single precision
* 6MW peak power (daily expect ~4)
* oil immersion for gpu
* whole thing will support CUI
* persistent vms for all the services that need it 
* all the expected SGCI portals, jupyter, etc.
* OSN (open storage network) - OK (check on this?)
* cloud: mostly for publishing data, new tech, some limited throughput jobs
* xsede funding currently set to expire before frontera ends 
* allocations complicated, but will let things 'cross'
* nsf rules require no project > 10yrs, so xsede will at the least be renamed (previous teragrid, etc.)

## lightning talks:
* check on SPEC benchmark suite
* globus is able to handle hipaa, nist, etc. data and can sign disclosures via UofC
* my lightning talk: https://researchit.github.io/RIT-Presentations/sc18_cc_lightning_talk/index.html

## funding:
* travel funding will be available for champions for conferences
