---
layout: post
title:  "Phylanx Report: October 2017"
date:   2017-11-01 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The second month of work focused on

* Creating a minimal set of primitives (driven by the use case of implementing a full Logistic Regression Training Algorithm – LRA)
* Migrating the code base from using the [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page) library for all matrix related operations to [Blaze](https://bitbucket.org/blaze-lib/blaze), adapting the build system
* Refactoring the compilation subsystem of Phylanx to enable support for higher order functions

### Organizational activities and results

Added Phylanx to OpenHub: [https://www.openhub.net/p/phylanx](https://www.openhub.net/p/phylanx)
* Weekly group-meeting, minutes:
    * [October 5th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_10.05.17.docx" | absolute_url }})
    * [October 12th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_10.12.17.docx" | absolute_url }})
    * [October 19th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_10.19.17.docx" | absolute_url }})
    * [October 26th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_10.26.17.docx" | absolute_url }})
* Phylanx Seminar: [http://phylanx.stellar-group.org/index.php/2017/10/17/phylanx-seminar/](http://phylanx.stellar-group.org/index.php/2017/10/17/phylanx-seminar/)
    * Explained the current theory, techniques, and methodology used by the Phylanx project
* Given talk at CppCon 2017: The Asynchronous C++ Parallel Programming Model (belated report for Sep)

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/js-e8xAMd1s?rel=0" frameborder="0" allowfullscreen></iframe>

Link: [https://youtu.be/js-e8xAMd1s](https://youtu.be/js-e8xAMd1s)

### Development activities and results

* Algorithms Highlighted: Logistic Regression, ALS
* Primitives Created: overall, we have now implemented 35 computational primitives (see here: [https://github.com/STEllAR-GROUP/phylanx/tree/master/phylanx/execution_tree/primitives](https://github.com/STEllAR-GROUP/phylanx/tree/master/phylanx/execution_tree/primitives))
* Issues Created: 14
* Issues Closed: 9
* Pull Requests Created: 40
* Pull Requests Closed: 40

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
C++           |      98      |   2863       |        1323     |    12456
C/C++ Header  |      78      |   1657       |        1249     |     6970
CMake         |      44      |    464       |         368     |     1865
Python        |      14      |    164       |         128     |      590
Perl          |       1      |     27       |          18     |      102
YAML          |       2      |     19       |          18     |       56
Markdown      |       1      |     11       |           0     |       29
Dockerfile    |       1      |      2       |           5     |       28
**SUM**       |   **239**    | **5207**     |      **3109**   |   **22096**


### Impact on other projects

* Opened ticket for vcpkg: [https://github.com/Microsoft/vcpkg/issues/1996](https://github.com/Microsoft/vcpkg/issues/1996)
