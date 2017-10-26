---
layout: post
title:  "Phylanx Report: September 2017"
date:   2017-10-06 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The first month of work was dedicated to the design and development of the first parts of the infrastructure needed for the overall project.

## Organizational activities and results


* Kick-off meeting (August 24th-25th, 2017), agenda and presentations:
    * [http://stellar.cct.lsu.edu/events/phylanx-kickoff-meeting/](http://stellar.cct.lsu.edu/events/phylanx-kickoff-meeting/)
* Weekly group-meeting, minutes:
    * [September 7th](https://drive.google.com/open?id=0B-L3qi_kGiCLWHlENUZJRWJLbFk)
    * [September 14th](https://drive.google.com/open?id=0B-L3qi_kGiCLSFFlemVqN3g0Q0E)
    * [September 21st](https://drive.google.com/open?id=0B-L3qi_kGiCLamJMNzVJN3hjTFE)
    * [September 28th](https://drive.google.com/open?id=0B-L3qi_kGiCLY1Bic01oem5DM0E)
* Created Mailing list: phylanx@stellar-group.org
    * Archive: http://mail.cct.lsu.edu/pipermail/phylanx/
* Created Website: http://phylanx.stellar-group.org/

## Development activities and results

* Repository created ([https://github.com/STEllAR-GROUP/phylanx](https://github.com/STEllAR-GROUP/phylanx))
    * Wiki created with build instructions, project references, and other information
* Set up continuous integration testing for Linux and Windows platforms
    * Linux: [https://circleci.com/gh/STEllAR-GROUP/phylanx](https://circleci.com/gh/STEllAR-GROUP/phylanx)
    * Windows: [https://ci.appveyor.com/project/hkaiser/phylanx](https://ci.appveyor.com/project/hkaiser/phylanx)
    * This triggers all build/tests on every commit to the repository.
    * Set up a Buildbot: [http://ktau.nic.uoregon.edu:8020/](http://ktau.nic.uoregon.edu:8020/)
* Issues Created: 11
* Issues Closed: 3
* Pull Requests Created: 21
* Pull Requests Closed: 21
* Code statistics:
```
-------------------------------------------------------------------------------
 Language                     files          blank        comment           code
 -------------------------------------------------------------------------------
 C/C++ Header                    44           1189            974           5315
 C++                             35            820            443           3446
 CMake                           43            449            354           1791
 Python                          13            162            126            584
 Perl                             1             27             18            102
 YAML                             2             19             18             56
 Markdown                         1             10              0             23
 Dockerfile                       1              2              5             19
 -------------------------------------------------------------------------------
 SUM:                           140           2678           1938          11336
 -------------------------------------------------------------------------------
```

## Impact on other projects

* HPX: several bug-reports and feature requests have been submitted and addressed which were related to problems and requirements of this project (for instance: [https://github.com/STEllAR-GROUP/hpx/pull/2864](https://github.com/STEllAR-GROUP/hpx/pull/2864))
* Pybind11: created two bug-report tickets ([https://github.com/pybind/pybind11/issues/1061](https://github.com/pybind/pybind11/issues/1061), [https://github.com/pybind/pybind11/issues/1069](https://github.com/pybind/pybind11/issues/1069)), both have been addressed by the Pybind11 team
* Submitted Pull Request to Blaze for HPX integration: [https://bitbucket.org/blaze-lib/blaze/pull-requests/15](https://bitbucket.org/blaze-lib/blaze/pull-requests/15)

