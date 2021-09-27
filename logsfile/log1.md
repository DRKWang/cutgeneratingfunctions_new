# Overview

### Assignments (Nov 25th, 2020)
1. Looking for library for geometric storage/ hash
2. Searching the library in Python or C/C++ or Julia 
3. The interface clean, implement clean, maintaining clean

### Search strategies
- Looking for the high dimensional data structure

- Search from Google, stackoverflow, youtube, Chinese website, github, google scholar

- Use the keyword: geometric storage, cutting generate function, geometry data structure, computational geometry, sparse data structure, Spatial algorithms, locality sensitive hashing, computer graphics, quad-tree, Range trees, Segment trees, 

- Some typical [geometric data structure](https://en.wikipedia.org/wiki/Category:Geometric_data_structures).

### Libraries

##### 1.Shapely [github](https://github.com/Toblerity/Shapely) (take care)

- Introduction: Shapely is a BSD-licensed Python package for manipulation and analysis of planar geometric objects. It is based on the widely deployed GEOS (the engine of PostGIS) and JTS (from which GEOS is ported) libraries. Shapely is **not concerned with data formats or coordinate systems**, but can be readily integrated with packages that are. 

- Main objects (LinearStrings, LinearRings, Polygons, Collections of Lines, ...)

- Review: Seemingly, it is not use geomeotric storage, it is kind of a port of GEOS and JTS. The interface of it is fine, but the implement of it mainly depends on the GEOS. On top of that, it is just a usually store in a ordinary python way, which means they are stored in list or other classical things. Rather than geometric data structure.

<div>
<img src="attachment:image.png" align="left" width="700"/>
</div>

- The interface of it looks like this.
<div>
<img src="attachment:image.png" align="left" width="700"/>
</div>

##### 2. GEOS [github](https://github.com/libgeos/geos) [website](https://trac.osgeo.org/geos/wiki#no1) (take care)

- Introduction: GEOS (Geometry Engine - Open Source) is a C++ port of the ​JTS Topology Suite (JTS). It aims to contain the complete functionality of JTS in C++. This includes all the ​OpenGIS Simple Features for SQL spatial predicate functions and spatial operators, as well as specific JTS enhanced functions. GEOS provides spatial functionality to many other projects and products.

- Main features
  - Geometries: Point, LineString, Polygon, MultiPoint, MultiLineString, MultiPolygon, GeometryCollection
  - Predicates: Intersects, Touches, Disjoint, Crosses, Within, Contains, Overlaps, Equals, Covers
  - Operations: Union, Distance, Intersection, Symmetric Difference, Convex Hull, Envelope, Buffer, Simplify, --Polygon Assembly, Valid, Area, Length,
  - Prepared geometries (pre-spatially indexed)
  - STR spatial index
  - OGC Well Known Text (WKT) and Well Known Binary (WKB) encoders and decoders.

- Review: it is also a port of JTS. (Java Topology Suite)

##### 3.CGAL [website](https://www.cgal.org/) (take care)

- Introduction: CGAL is a software project that provides easy access to efficient and reliable geometric algorithms in the form of a C++ library. CGAL is used in various areas needing geometric computation, such as geographic information systems, computer aided design, molecular biology, medical imaging, computer graphics, and robotics.

- Main feature: The library offers data structures and algorithms like triangulations, Voronoi diagrams, Boolean operations on polygons and polyhedra, point set processing, arrangements of curves, surface and volume mesh generation, geometry processing, alpha shapes, convex hull algorithms, shape reconstruction, AABB and KD trees...

- Review: It provides many objects in computing geometry. Many of them are 2D or 3D, but it is still resourceful because it also gives many high dimensional algorithm.

##### 4.SymPy [Github](https://github.com/sympy/sympy) (not good)
- SymPy is a Python library for symbolic mathematics. It aims to become a full-featured computer algebra system (CAS) while keeping the code as simple as possible in order to be comprehensible and easily extensible. SymPy is written **entirely** in Python.

- Main feature: Point, Line, Segment, Ray, Ellipse, Circle, Polygon, RegularPolygon, Triangle

- Review: It only provides the basic objects in geometry, so I do not believe it will implement some advanced data structure in it.

##### 5.scipy.spatial [website](https://docs.scipy.org/doc/scipy/reference/spatial.html) (not good)
- Mainfeature: KTDTree, cKDTree, Voronoi, ...
<div>
<img src="attachment:image.png" width="700"/>
</div>

- Review: It only provides some static geometric data structure.

##### 6.PyVisiLibity [website](https://karlobermeyer.github.io/VisiLibity1/) (not good)

- VisiLibity1 is a free open source C++ library for 2D floating-point visibility algorithms, path planning, and supporting data types. It is intended for use in robot and sensor network design software. Other possible applications include, e.g., manufacturing, facility location, architectural/urban planning, games, and education. The entire library consists only of a single compilation unit (one .hpp + one .cpp file) with no dependence on 3rd party libraries. It is therefore suitable for applications where simple visibility and path planning computations are needed but the power of a larger computational geometry library is not necessary.

- visibility polygons, visibility graphs, Euclidean shortest paths for a point, Python, Ruby, and Matlab bindings

- More focusing on the visibilization.

##### 7. Qhull [website](http://www.qhull.org/) (not good)

- Qhull computes the convex hull, Delaunay triangulation, Voronoi diagram, halfspace intersection about a point, furthest-site Delaunay triangulation, and furthest-site Voronoi diagram. The source code runs in 2-d, 3-d, 4-d, and higher dimensions. Qhull implements the Quickhull algorithm for computing the convex hull. It handles roundoff errors from floating point arithmetic. It computes volumes, surface areas, and approximations to the convex hull. Qhull does not support triangulation of non-convex surfaces, mesh generation of non-convex objects, medium-sized inputs in 9-D and higher, alpha shapes, weighted Voronoi diagrams, Voronoi volumes, or constrained Delaunay triangulations.

- It is made in C with a C++ interface.

##### 8. GUDHI Geometry Understanding in Higher dimensions [website](https://gudhi.inria.fr/) (take care)

- The GUDHI library is a generic open source C++ library, with a Python interface, for Topological Data Analysis (TDA) and Higher Dimensional Geometry Understanding. The library offers state-of-the-art data structures and algorithms to construct simplicial complexes and compute persistent homology.

- It is C++ lib with a Python interface. Simplex tree, Skeleton blockers and Toplex map and [others](http://gudhi.gforge.inria.fr/doc/latest/).

##### 9.Gfxpoly [website](http://gfxpoly.quiss.org/) [github](https://github.com/matthiaskramm/gfxpoly) (not good)

- gfxpoly is a library for doing geometric polygon operations. (like polygon intersection, union, hidden surface removal, stroke to outline conversion, wind rule conversion etc.) It aims to be more easily embeddable than e.g. GX, livarot or CGAL, faster and more stable than libart, and is distributed under a non-commercial license (BSD-2).

##### 10. PCL [website](https://pointclouds.org/) (take care)

- The Point Cloud Library (PCL) is a standalone, large scale, open project for 2D/3D image and point cloud processing. PCL is released under the terms of the BSD license, and thus free for commercial and research use.

- Main feature: segmentation, kdtree, Octree, and so on.

- This is implemented by C++, the source is quite clear to understand.

##### 11.Boost.Geometry [website](https://www.boost.org/doc/libs/1_74_0/libs/geometry/doc/html/index.html) [github](https://github.com/boostorg/geometry) (not good)

- Boost.Geometry, part of collection of the Boost C++ Libraries, defines concepts, primitives and algorithms for solving geometry problems.
- Main objects: polygon, convex hull and other basic geometry objects.
- It offers the basic geometry objects and algorithms for computing, which seemingly do not contain advanced data structure. But the logic of it is quite clear, see the following images.

<div>
<img src="attachment:image.png" align="left" width="700"/>
</div>

- To see more details about updating

##### 12. NURBS-Python [website](https://github.com/orbingol/NURBS-Python) (not good)

- NURBS-Python (geomdl) is a pure Python, self-contained, object-oriented B-Spline and NURBS spline library for Python versions 2.7.x, 3.4.x and later.

- NURBS-Python (geomdl) provides convenient data structures and highly customizable API for rational and non-rational splines along with the efficient and extensible implementations of the following algorithms:
- Spline evaluation, Derivative evaluation, Knot insertion, Knot vector refinement.

##### 13.isect [github](https://github.com/anvaka/isect) (too small)

- This library allows you to find all intersections in a given set of segments.

##### 14. Wykobi [github](https://github.com/ArashPartow/wykobi) (not good, only 2D and 3D)

- Wykobi is an efficient, robust and simple to use multi-platform 2D/3D computational geometry library. Wykobi provides a concise, predictable, and deterministic interface for geometric primitives and complex geometric routines implemented in C++.

- The algorithms can data structure mainly focus on 2D/3D.

##### 15. polytope [github](https://github.com/tulip-control/polytope) (not good, too small)

- This is the source repository for polytope, a toolbox for geometric operations on polytopes in any dimension. Documentation is available in the directory doc/ and also at https://tulip-control.github.io/polytope/ The directory examples/ contains examples.

- This is made by python.

##### 16.inpoly-python [github](https://github.com/dengwirda/inpoly-python) (not good, too small)

- A fast 'point(s)-in-polygon' routine for Python.

##### 17.pympc [github](https://github.com/TobiaMarcucci/pympc) (take care)

- pympc is a pyhton toolbox for Model Predictive Control (MPC) of linear and hybrid systems.
  - This toolbox implements several algorithms for:
  
    polyhedral computations,
    
    computation of maximum constraint-admissible invariant sets,
    
    MPC of linear systems,
    
    explicit MPC of linear systems,
    
    MPC for hybrid systems in piecewise-affine form.

- This project may be a good reference.

##### 18.pypolyline [github](https://github.com/urschrei/pypolyline) (not good)

- Fast Google [Polyline](https://developers.google.com/maps/documentation/utilities/polylinealgorithm) Encoding and Decoding

##### 19.miniball [github](https://github.com/marmakoide/miniball) (not good)
- A Python module to efficiently compute the smallest bounding ball of a point set, in arbitrary number of dimensions.
    The algorithm runs in approximatively linear time in respects to the number of input points. This is NOT a derivative nor a port of Bernd Gaertner's C++ library.
    
- We may use it because it is in arbitrary number of dimensions. 

##### 20.polliwog [github](https://github.com/lace/polliwog) (not good)
- 2D and 3D computational geometry library which scales from prototyping to production.
- Includes vectorized geometric operations, transforms, and primitives like planes, polygonal chains, and axis-aligned bounding boxes. Implemented in pure Python/NumPy. Lightweight and fast.

- This libaray is a bit small. And the reader guild has not been finished yet.

##### 21.CGLibPy [github](https://github.com/rhtbapat/CGLibPy) (not good)
- The library has not been finished yet, and only implements those basic geometry objects.
##### 22.libigl [github](https://github.com/libigl/libigl) (take care)

- ibigl is a simple C++ geometry processing library. We have a wide functionality including construction of sparse discrete differential geometry operators and finite-elements matrices such as the cotangent Laplacian and diagonalized mass matrix, simple facet and edge-based topology data structures, mesh-viewing utilities for OpenGL and GLSL, and many core functions for matrix manipulation which make Eigen feel a lot more like MATLAB.

##### 23.cinolib [github](https://github.com/mlivesu/cinolib) (take care)

- A generic programming header only C++ library for processing polygonal and polyhedral meshes.

- This library has a clear and resourceful [tutorial](https://github.com/mlivesu/cinolib/tree/master/examples).

##### 24.Euclid [github](https://github.com/unclejimbo/Euclid) (take care)

- Euclid is a header only library for geometry processing and shape analysis.
    It contains some utilities and algorithms which extend and cooperate with other popular libraries around there, like Eigen(libigl), CGAL, to name a few.
    The purpose of Euclid is not to replace any of the above packages, but to glue things together as well as to provide more algorithms which do not appear in those libraries.
    
##### 25.DGtal [github](https://github.com/DGtal-team/DGtal) [website](https://dgtal.org/) (take care)
- DGtal is a generic open source library for Digital Geometry programming for which the main objective is to structure different developments from the digital geometry and topology community. The aims are numerous: make easier the appropriation of our tools for a neophyte (new PhD students, researchers from other topics,...), permit better comparisons from new methods with already existing approaches and to construct a federative project. Another objective of DGtal is to simplify the construction of demonstration tools to share new results and potential efficiency of the proposed work.

- This library is large and quite resourceful.

- ![image.png](attachment:image.png)

##### 26.Topology ToolKit [website](https://topology-tool-kit.github.io/gallery.html) [github](https://github.com/topology-tool-kit/ttk) (take care)
- The Topology ToolKit (TTK) is an open-source library and software collection for topological data analysis and visualization.

    TTK can handle scalar data defined either on regular grids or triangulations, in 2D, 3D, or more. It provides a substantial collection of generic, efficient and robust implementations of key algorithms in topological data analysis. 
    
### Other resources

1. https://deeplearning.lipingyang.org/computational-geometry-in-python/

2. https://www.cs.princeton.edu/~rs/AlgsDS07/16Geometric.pdf

3. [Comparison of the different algorithms for Polygon Boolean operations](https://web.archive.org/web/20110720075903/http://www.complex-a5.ru/polyboolean/comp.html)
