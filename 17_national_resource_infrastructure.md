# National Research Infrastructue (maybe s/b data infrastructure)

## Intro:
* lots of tools, grids, data commons, science gateways, etc.
* need some coordination / consolidation

## Open Storage Network
* newly funded NSF activity
* to address unmet need with data storage & sharing
* too many usb drives still (ncsa, one guy with PB of data in usb hdds on his desk!)
* OSN trying to address the need that there's a missing storage substrate on NSF investments
* do it in a distributed manner, kind of like xsede
* leverage bigdata hubs
* keep the data near the computation
* CC* activities (not same as campus champs)
* Proposal sites: SDSC, NCCSA, MGHPCC, TACC, STARLIGHT, JHU
* Roll out to more later
* goal look like one storage system
* researchers need to justify why data should go there & be valuable to the community
* Ultimate goal is scale to hundreds of sites
* deployable scalable unit is ~1PB, capable of 40Gbps sequential i/o
* geo-aware replication, fault tolerance, data locality
* optimize for capacity & low cost (cheap & deep)
* $140K / PB
* want to survive a given site going down
### tech specs: 
* ceph
* 8 nodes, 5x 4U data nodes, 3x 1U monitoring nodes
* 1.44PB Raw (8TB drives * 36 drives / node) - using erasure coding
* dual 40Gpbs nics? later says single
* top of rack 100Gbps switch, 32 port, 16 for client, 16 for cluster
* single socket, 1FT core per OSD
* 256G ram, 288TB storage (.89g/tb)
* dual port sas3008, pcie 3.0 x8
* each backplane gets its own sas card, don't want to bottleneck
* Have two now, JHU and Chicago
* Benchmarking wan interconnect
* expect to bring on the rest by end of 2019
### sw details:
* 1 yr of funding, 2 objectives
* globus participating
* layered arch (osg, globus, irods, etc. on top) then secure data api, then osn sw platform, then osn hardware platform
* Secure access API (s3 + oauth2) | globus connect server | ceph radosgw obj stor | remote operations (boot, monitoring, mgmt) {allocation provisioning off to the side}
* globus connect server: same stack, adding s3 api, integration w/ globus auth, federated logins, etc.
* common interface across osn, campus storage, public cloud
* monitor nodes will be DTNs (lb, failover, etc.)
* discussion on additional apis (open to suggestions) - e.g. multi-site replication, data publication

## national research platform & open science grid:
* PRP, NRP, GRP, and internet2
* prp (pacific research platform), bring e2e network at 10gbps and above to 15 campuses into the labs near the west coast ($6M 2015-2020_
* build on prior investment in science dmz's
* create a soccial network of networking experts
* deploy end point devices that are guaranteed to have known IO char & provide reliable & relevant IO perf measurements (to avoid figerpointing)
* FIONA = Flash I/O network appliances (same thing I talked to the GPN guy about & that Steve is running)
* work with researchers & research communities that are ready and hungry to get stuff done
* out of the initial, as always less are ready than they think, but others hear about it & take their place
* successful cyberinfastructure requires social engineering
* FIONette ($250) 1Gbps (wifi), up to the default full speed, racked system (dual 12 core, 10G interfaces, cost $10.5k)
* measurements of prp number of paths & packet loss (containerized perfSONAR MaDDash Dashboards)
* the appliance runs kubernetes containers to do services, metrics, etc. (have service orgs operate services, on local hw)
* layered CI orgs 
    * Science collabs (lsst, ligo, ska, etc.) | science infra (osg, xsede, nrp, etc.) | campus networks | 
* fiona8 (has 8 1080ti)
    * multi-tenant containerized gpu jupyterhug $18.2K
    * machine learning 
* announced may '18 to make nationwide building on regional networks (gpn, tacc-learn, nysernet)
* now called the nrp (was prp), new $2.5mm nsf grant

 
