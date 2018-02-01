---
layout: post
title:  "Phylanx Report: January 2018"
date:   2018-01-31 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The fifth month of work focused on work in the following areas:

* Tiling
* Performance analysis

### Organizational activities and results

* Weekly group-meeting, minutes:
    * [January 11th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_01.11.18.docx" | absolute_url }})
    * January 18th: LSU closed
    * [January 25th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_01.25.18.docx" | absolute_url }})

### Development activities and results

* Algorithms Highlighted: Logistic Regression (LRA), ALS
* Demonstrated first end-to-end algorithm transformation of the LRA algorithm (Python source code) generating internal Phylanx data structures and allowing to execute the generated expression trees on the Phylanx/HPX execution engine (see: [`lra_csv_phyfun_np.py`](https://github.com/STEllAR-GROUP/phylanx/blob/master/examples/algorithms/lra_csv_phyfun_np.py))
* First analysis shows that the achieved performance of the Phylanx LRA algorithm matches (and in certain cases exceeds) the performance of the equivalent Python code that is using a highly optimized Numpy implementation:

![scaling.png](/assets/scaling_01.31.18.png)


See [here](https://github.com/STEllAR-GROUP/phylanx_data/tree/master/Python_vs_Phylanx/25JAN18) for the actual data

* Primitives Created: overall, we have now implemented 51 computational primitives (see here: <https://github.com/STEllAR-GROUP/phylanx/tree/master/phylanx/execution_tree/primitives>)
* Added inspect tool to repository and CI services ensuring formal code quality (guidelines and style)

#### Repository activity January 1st – January 31st:

![stats.png](/assets/stats_01.31.18.png)

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
 C++          |     154      |    4939      |        2401     |     22481
 C/C++ Header |     115      |    2163      |        1542     |      8793
 CMake        |      54      |     541      |         435     |      2138
 Python       |      20      |     216      |         235     |      1084
 YAML         |       2      |      19      |          11     |        54
 Markdown     |       1      |      11      |           0     |        29
 Dockerfile   |       1      |       2      |           4     |        23
**SUM**       |     347      |    7891      |        4628     |     34602

### Impact on other projects

* Blaze Pull Request – Removing `BLAZE_PARALLEL_SECTION` in the HPX
  backend (PR
  [\#18](https://bitbucket.org/blaze-lib/blaze/pull-requests/18/removing-blaze_parallel_section-in-the-hpx))
* HPX Pull Requests:
    * Adding `performance_counter::reinit` to allow for dynamically changing counter sets (PR [\#3138](https://github.com/STEllAR-GROUP/hpx/pull/3118))
    * Local execution of direct actions is now actually performed directly (PR [\#3104](https://github.com/STEllAR-GROUP/hpx/pull/3104))
    * Adding support for generic `counter_raw_values` performance counter type (PR [\#3103](https://github.com/STEllAR-GROUP/hpx/pull/3103))
* Opened ticket for vcpkg – "`vcpkg install blaze:x64-windows -–head` broken" ([\#2696](https://github.com/Microsoft/vcpkg/issues/2696))

