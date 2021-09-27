# Target
- fix the error for "missing the CGAL library".
- find the patches for the cgal_bindings.

# Progression
- The error has been fixed, which is due to previously just installing the CGAL library of homebrew and not installing the original CGAL files. \
  However, the cgal still goes wrong, which may be caused by versions problems.

- The cgal_bindings has not been updated for a while, why not we use the setup.py in cgal_swig_bindings, \
which has been installed successfully previously in the way of cmake.
- We still need the CGAL library to be installed, where should we place CGAL library inside the sage?
