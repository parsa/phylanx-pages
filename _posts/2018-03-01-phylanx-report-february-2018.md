---
layout: post
title:  "Phylanx Report: February 2018"
date:   2018-03-01 00:00:00 -0500
author: Adrian Serio
categories: Phylanx
tags: [Phylanx, Project Report]
---
The sixth month of work focused on work in the following areas:

  - Performance analysis
  - Refactoring
  - Debugging features
  - Jupyter Notebook Integration
  - Singularity Integration
  - Visualization

### Organizational activities and results

  - Weekly group-meeting, minutes:
      - [February 1st](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_02.01.18.docx | absolute_url }})
      - [February 8th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_02.08.18.docx | absolute_url }})
      - [February 15th](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_02.15.18.docx | absolute_url }})
      - [February 22nd](https://docs.google.com/viewer?url={{ "/assets/reports/meeting_02.22.18.docx | absolute_url }})
  - Phylanx Seminars
      - [Phylanx Seminar: PhySL]({% post_url 2018-02-15-phylanx-seminar-physl %})
      - [Phylanx Seminar: PhyFun]({% post_url 2018-02-27-phylanx-seminar-phyfun %})

### Development activities and results

  - Algorithms Highlighted: Logistic Regression, ALS
      - First Python version of ALS implemented
      - Initial `@Phylanx` (decorator) ports of:
          - K-Means
          - T-sne
          - PCA
  - Performance Counters – Created `lra_csv_instrumented` example to
    demonstrate the instrumentation of performance counters in Phylanx
  - Created a PhySL interpreter
  - Added HDF5 Read/Write primitives
  - Improved error messages
      - Provide line and column information
      - Added detailed error messages
  - Working instance of PhyFun front end working in a Jupyter Notebook
      - <https://github.com/STEllAR-GROUP/phylanx/wiki/Jupyter-Notebook>
  - Created visualization of execution tree
      - Shows dependencies between primitives
      - Displays information gathered by performance counters
          - Name of each primitive instance
          - Average time per primitive instance
          - Direct vs Plain actions

![phylanx_fibonacci_visualization.png](/assets/phylanx_fibonacci_visualization_04.02.18.png)

#### Repository activity January 28th – February 28th:

![github_pulse_february_2018.png](/assets/github_pulse_february_2018_04.02.18.png)

#### Code statistics

Language      | No. of Files |  Blank Lines |   Comment Lines |  Code Lines
--------------|--------------|--------------|-----------------|-------------
 C++          |     197      |    8597      |        2790     |     38988
 C/C++ Header |     137      |    2476      |        1892     |      9610
 CMake        |      61      |     593      |         479     |      2334
 Python       |      28      |     512      |         347     |      1520
 YAML         |       2      |      19      |          11     |        55
 Dockerfile   |       1      |       2      |           4     |        32
 Markdown     |       1      |      11      |           0     |        29
 INI          |       1      |       0      |           0     |         8
**SUM**       |       428    |     12210    |          5523   |     52576

### Impact on other projects

  - Vcpkg
      - Pull Request: Using vcpkg\_from\_github() for HPX (PR
        [\#2830](https://github.com/Microsoft/vcpkg/pull/2830))
      - Highfive library does not install cmake files (Issue
        [\#2715](https://github.com/Microsoft/vcpkg/issues/2715))
      - Ticket: \`vcpkg install boost:x64-windows\` does not install the
        pdb files (Issue
        [\#2705](https://github.com/Microsoft/vcpkg/issues/2705))
  - Blaze Ticket: Views can be initialized from rvalues (Issue
    [\#159](https://bitbucket.org/blaze-lib/blaze/issues/159/views-can-be-initialized-from-rvalues#comment-43593884))
  - HighFive ticket: dataspace.getDimension() for zero-dimensional
    data-space will cause out-of-bounds index (Issue
    [\#98](https://github.com/BlueBrain/HighFive/issues/98))
  - HPX Pull Requests:
      - Making sure resource partitioner is not accessed if its not
        valid (PR
        [\#3202](https://github.com/STEllAR-GROUP/hpx/pull/3202))
      - Fixing optional::swap (PR
        [\#3201](https://github.com/STEllAR-GROUP/hpx/pull/3201))
      - Optionally disable printing of diagnostics during terminate (PR
        [\#3188](https://github.com/STEllAR-GROUP/hpx/pull/3188))
      - Fixing the handling of quoted command line arguments (PR
        [\#3160](https://github.com/STEllAR-GROUP/hpx/pull/3160))

