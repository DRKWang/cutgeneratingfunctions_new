# Target
- install the cgal_swig_bindings into sage

# So far
- It has been installed successfully by [packaging it into a normal package](https://doc.sagemath.org/html/en/developer/packaging.html) using ```sdh_cmake``` etc. The scripts is as follows:
  ```
  cd src

  echo "Configuring cgal_swig_bindings."

  sdh_cmake -DCGAL_DIR=/usr/local/opt/cgal/lib/cmake/CGAL \
  -DBUILD_PYTHON=ON \
  -DBUILD_JAVA=OFF

  sdh_make

  sdh_make_install
  ```
- It should be mentioned that the tarball of cgal_swig_bindings is not the same as the tarball compressed by the folder downloaded from cgal_swig_bindings. The difference between them is changing from ```find_package(Python COMPONENTS Interpreter Development)``` to ```find_package(Python 3.7 EXACT COMPONENTS Interpreter Development)```.

- Dependencies is a big issue for flawlessly running the cgal_swig_packages. Many modules will be imported with errors when the corresponding [dependencies](https://doc.cgal.org/latest/Manual/thirdparty.html) is missing. Also, not all dependencies can be found via homebrew.


# Reference
- [cmake template](https://mjmorse.com/blog/cmake-template/)
- [cmake wiki](https://gitlab.kitware.com/cmake/community/-/wikis/home)
- [cmake find package grammary](https://cmake.org/cmake/help/latest/command/find_package.html#search-procedure)
- [dependencies of cgal](https://doc.cgal.org/latest/Manual/thirdparty.html)
