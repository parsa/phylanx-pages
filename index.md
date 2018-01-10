---
layout: page
---
Phylanx is a platform that takes a step toward providing a general purpose system for computations on distributed arrays for applied statistics on commodity cloud systems. Phylanx builds upon Spartan, Theano, and Tensorflow in an effort to generalize array operations specifically to support distributed computing. The system will decompose array computations into a predefined set of parallel operations and employ algorithms which optimize execution and data layout from of a user provided expression graph. Using hints from the user and the optimization step the expression graph will be passed to the HPX runtime which schedules work and infers the data layout on each compute locale arguments.

Phylanx improves upon previous solutions by adding more sophisticated algorithms to optimize data layout, distribution, and tiling on HPC systems, and by using cache-oblivious data layouts to improve the overall performance and scalability of the provided expression evaluations.

To learn more about our project find our repository on [GitHub](https://github.com/STEllAR-GROUP/phylanx) or contact us at [phylanx@stellar-group.org](mailto:phylanx@stellar-group.org)
