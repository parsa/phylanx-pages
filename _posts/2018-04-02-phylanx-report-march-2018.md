---
layout: post
title:  "Phylanx Report: March 2018"
date:   2018-04-02 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The seventh month of work focused on work in the following areas:

  * Performance analysis
      * Initial performance comparisons of Phylanx to Numpy, Dask,
        SciKit Learn, and TensorFlow
      * Performance analysis of ALS
  * APEX
      * Adding support for thread parent tracking
  * Visualization
  * HPX version 1.1.0 Release

### Organizational activities and results

  * Weekly group-meeting, minutes:
      * [January 11th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_01.11.18.docx" | absolute_url }})
      * [March 1st](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_03.01.18.docx" | absolute_url }})
      * [March 8th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_03.08.18.docx" | absolute_url }})
      * [March 15th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_03.15.18.docx" | absolute_url }})
      * [March 22nd](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_03.22.18.docx" | absolute_url }})
  * Phylanx Seminars:
      * [Phylanx Seminar: Polyhedral Optimizations]({% post_url 2018-03-12-phylanx-seminar-polyhedral-optimizations %})
      * [Phylanx Seminar: Revealing the Magic of Blaze]({% post_url 2018-03-22-phylanx-seminar-revealing-the-magic-of-blaze %})

### Development activities and results

  * Algorithms Highlighted: Logistic Regression, ALS, K-Means
  * Initial integration of interactive visualization tools inside
    Jupyter Notebook:[![jupyter_notebook_vis_1.png](/assets/jupyter_notebook_vis_1_04.02.18.png)](https://drive.google.com/open?id=1MvaY3kqUxKacUfdpj4GTNJUiDuDY7NqY)

  * Mapped select Numpy functions to Phylanx primitives when placed
    inside of Phylanx decorators
  * Added an OpenScop backend (see related Phylanx seminar)
  * HPX
      * Released HPX version 1.1.0
      * Added trait to enable runtime to schedule an action on a new or
        current thread

### Repository activity March 2nd – April 2nd:

![Capture.png](/assets/Capture_04.02.18.png)

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
 C++          |     231      |    9850      |        3184     |     44867
 C/C++ Header |     155      |    3014      |        2202     |     12167
 CMake        |      64      |     625      |         528     |      2521
 Python       |      32      |     602      |         407     |      2032
 YAML         |       2      |      13      |          15     |        79
 Dockerfile   |       1      |       2      |           4     |        32
 Markdown     |       1      |      11      |           0     |        29
 INI          |       1      |       0      |           0     |         8
**SUM**       |     487      |    4117      |        6340     |     61735

### Impact on other projects

  * Vcpkg Pull Requests:
      * Pull Requests: Updating HPX to V1.1
        ([\#3120](https://github.com/Microsoft/vcpkg/pull/3120))
  * HPX Pull Requests:
      * Apex refactoring with guids
        ([\#3250](https://github.com/STEllAR-GROUP/hpx/pull/3250),
        [\#3245](https://github.com/STEllAR-GROUP/hpx/pull/3245))
      * Adding trait for actions allowing to make runtime decision on
        whether to execute it directly
        ([\#3254](https://github.com/STEllAR-GROUP/hpx/pull/3254))

