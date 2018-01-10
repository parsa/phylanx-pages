---
layout: post
title:  "Phylanx Report: December 2017"
date:   2018-01-05 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The fourth month of work focused on work in the following areas:

* Visualization
    * Setting up visualization tools on our local cluster
    * Creating an OTF2 profile of Phylanx
* Python Bindings
    * Came up with two potential solutions to bind Python code to AST
* Performance
    * Instrumenting performance counters into the AST to report useful statistics
    * Analyze the performance of the Phylanx LRA example
        * Determine where improvements can be made
    * Begin exposing SIMD methods to AST
* Research
    * Begin comparing our approach to Spartan and to TensorFlow

### Organizational activities and results

* Weekly group-meeting, minutes:
    * [December 7th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_12.07.17.docx" | absolute_url }})
    * [December 14th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_12.14.17.docx" | absolute_url }})
    * [December 21st](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_12.21.17.docx" | absolute_url }})
* [Phylanx Seminar]({% post_url 2017-12-15-phylanx-seminar-the-agave-platform %})

### Development activities and results

* Algorithms Highlighted: Logistic Regression, ALS
* Primitives Created: overall, we have now implemented 44 computational primitives (see here: <https://github.com/STEllAR-GROUP/phylanx/tree/master/phylanx/execution_tree/primitives>)
* Issues Created: 16
* Issues Closed: 3
* Pull Requests Created: 10
* Pull Requests Closed: 9

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
 C++          |     116      |    3606      |        1574     |     15442
 C/C++ Header |      87      |    1790      |        1307     |      7539
 CMake        |      47      |     492      |         395     |      2004
 Python       |      14      |     164      |         128     |       590
 YAML         |       2      |      19      |          11     |        51
 Markdown     |       1      |      11      |           0     |        29
 Dockerfile   |       1      |       2      |           4     |        21
**SUM**       |     268      |    6084      |        3419     |     25676

### Impact on other projects

* Reported issues in Blaze
