# Description

This project mainly focuses on developing effecient data structures and algorithms, and implementing them in C++ and Python, for exploring new cut-generating functions in high-dimensional space. [try](https://github.com/DRKWang/cutgeneratingfunctions_new/blob/main/rationalpolyhedronfan.ipynb)

# Introduction

The cut-generating function is a family of piecewise linear functions for increasing the speed of solving integer optimization. The information of integer optimization can be found in this [book](https://link.springer.com/book/10.1007/978-3-319-11008-0), and the details of cut-generating function can be found in this [website](https://www.math.ucdavis.edu/~mkoeppe/art/infinite-group/).

In general, we are looking for the piecewise linear functions π(x) in high dimension, with satisfying the 4 following conditions:

1. π(0) = 0
2. π(x) + π(y) ≥ π(x + y) (Subadditivity)
3. π(x) + π(f − x) = 1 (Symmetry)
4. π(x) = π(x + k), for k in Z^d (periodicity)

Those functions in one dimension have been well developped, with using [computer-based method](http://www.optimization-online.org/DB_FILE/2014/11/4646.pdf). However, for high dimension, the main difficulty of exploring and verifying cut-generating functions comes from the verification of the subadditivity, which is a entire verification with heavy computation and hard to find out which subregions in the domain intersects with the minkowski sum for each pair of subregions. Notice that the minkowski sum of two specific subregions only has a local intersection with few subregions, instead of a total retriving. We may arrange [rtree](https://en.wikipedia.org/wiki/R-tree) data structure as a cheapo index library to organize all subregions of the domain for [easily computing their minkowski sum] and [quickly retriving the intersected subregions]. After using rtree data structure, it could filter most non-intersected subregions and improve the computation significantly.

Apart from the above project in the piecewise linear functions, rtree data structure also has been used as a cheapo index library for preliminary filtering the non-containing element of a 
