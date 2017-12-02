---
layout: post
title:  "Phylanx Report: November 2017"
date:   2017-12-01 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The third month of work focused on

* **First Major Milestone Reached:** Fully Functional DSL
    * Generation of Execution Tree
    * Execution of Tree Using HPX
    * Demonstrated by a working implementation of Logistic Regression
* Build system improvements
* Data type changes
* I/O primitives

### Organizational activities and results

* Weekly group-meeting, minutes:
    * [November 2nd](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_11.02.17.docx" | absolute_url }})
    * [November 9th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_11.09.17.docx" | absolute_url }})
    * [November 30th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_11.30.17.docx" | absolute_url }})
* Phylanx Seminar: <http://phylanx.stellar-group.org/index.php/2017/11/08/phylanx-seminar-python-integration/>
    * Discussion of implementation strategies for the Python front-end

### Development activities and results

* Algorithms Highlighted: Logistic Regression, ALS
* Primitives Created: overall, we have now implemented 44 computational primitives (see here: <https://github.com/STEllAR-GROUP/phylanx/tree/master/phylanx/execution_tree/primitives>)
* Issues Created: 5
* Issues Closed: 1
* Pull Requests Created: 14
* Pull Requests Closed: 14

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
C++           |     113      |   3407       |        1500     |     14676
C/C++ Header  |      87      |   1771       |        1305     |      7436
CMake         |      44      |    463       |         371     |      1859
Python        |      14      |    164       |         128     |       590
Perl          |       1      |     27       |          18     |       102
YAML          |       2      |     19       |          18     |        56
Markdown      |       1      |     11       |           0     |        29
Dockerfile    |       1      |      2       |           4     |        18
**SUM**       |   **263**    | **5864**     |      **3344**   |   **24766**

### Impact on other projects

* Addressed a major performance issue in HPX: <https://github.com/STEllAR-GROUP/hpx/pull/3017>
