Jan 2nd, 2021

# Target
- download the [cgal-bindings 1.2](https://pypi.org/project/cgal-bindings/#modal-close) and make it as a normal package.
- find the difference between the package of [cgal-bindings 1.2](https://pypi.org/project/cgal-bindings/#modal-close) and package of the official [cgal-swig-bindings](https://github.com/CGAL/cgal-swig-bindings).
- further think how to make the modified version.

# progression
- made the "cgal-swig-bindings", which is an optional pip package.

    Some discussion: 
    - name shoulde be either "cgal-swig-bindings" or "cgal_swig_bindings"?
    - got the error message:
    ```
    ➜  sage git:(cgal_swig_drk) ✗ ./sage -i cgal-swig-bindings
    /Applications/Xcode.app/Contents/Developer/usr/bin/make build/make/Makefile --stop
    ./bootstrap -d
    rm -rf config configure build/make/Makefile-auto.in
    rm -f src/doc/en/installation/*.txt
    rm -rf src/doc/en/reference/spkg/*.rst
    rm -f src/doc/en/reference/repl/*.txt
    rm -f environment.yml
    rm -f src/environment.yml
    rm -f environment-optional.yml
    rm -f src/environment-optional.yml
    src/doc/bootstrap:92: installing src/doc/en/installation/arch.txt and src/doc/en/installation/arch-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/debian.txt and src/doc/en/installation/debian-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/fedora.txt and src/doc/en/installation/fedora-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/cygwin.txt and src/doc/en/installation/cygwin-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/homebrew.txt and src/doc/en/installation/homebrew-optional.txt
    src/doc/bootstrap:66: installing environment.yml, environment-optional.yml, src/environment.yml and src/environment-optional.yml
    src/doc/bootstrap:103: installing src/doc/en/reference/spkg/*.rst
    src/doc/bootstrap:131: installing src/doc/en/reference/repl/options.txt
    bootstrap:73: installing 'config/config.rpath'
    m4/sage_spkg_configures.m4:106: error: AC_SUBST: `SAGE_ENABLE_cgal-swig-bindings' is not a valid shell variable name
    m4/sage_spkg_enable.m4:31: SAGE_SPKG_ENABLE is expanded from...
    m4/sage_spkg_collect.m4:324: SAGE_SPKG_COLLECT is expanded from...
    m4/sage_spkg_configures.m4:106: the top level
    autom4te: /usr/bin/m4 failed with exit status: 1
    aclocal: error: autom4te failed with exit status: 1
    make[1]: *** [configure] Error 1
    make: *** [all-toolchain] Error 2
    ➜  sage git:(cgal_swig_drk) ✗ ./sage -f cgal-swig-bindings
    /Applications/Xcode.app/Contents/Developer/usr/bin/make build/make/Makefile --stop
    ./bootstrap -d
    rm -rf config configure build/make/Makefile-auto.in
    rm -f src/doc/en/installation/*.txt
    rm -rf src/doc/en/reference/spkg/*.rst
    rm -f src/doc/en/reference/repl/*.txt
    rm -f environment.yml
    rm -f src/environment.yml
    rm -f environment-optional.yml
    rm -f src/environment-optional.yml
    src/doc/bootstrap:92: installing src/doc/en/installation/arch.txt and src/doc/en/installation/arch-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/debian.txt and src/doc/en/installation/debian-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/fedora.txt and src/doc/en/installation/fedora-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/cygwin.txt and src/doc/en/installation/cygwin-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/homebrew.txt and src/doc/en/installation/homebrew-optional.txt
    src/doc/bootstrap:66: installing environment.yml, environment-optional.yml, src/environment.yml and src/environment-optional.yml
    src/doc/bootstrap:103: installing src/doc/en/reference/spkg/*.rst
    src/doc/bootstrap:131: installing src/doc/en/reference/repl/options.txt
    bootstrap:73: installing 'config/config.rpath'
    m4/sage_spkg_configures.m4:106: error: AC_SUBST: `SAGE_ENABLE_cgal-swig-bindings' is not a valid shell variable name
    m4/sage_spkg_enable.m4:31: SAGE_SPKG_ENABLE is expanded from...
    m4/sage_spkg_collect.m4:324: SAGE_SPKG_COLLECT is expanded from...
    m4/sage_spkg_configures.m4:106: the top level
    autom4te: /usr/bin/m4 failed with exit status: 1
    aclocal: error: autom4te failed with exit status: 1
    make[1]: *** [configure] Error 1
    make: *** [cgal-swig-bindings-clean] Error 2
    /Applications/Xcode.app/Contents/Developer/usr/bin/make build/make/Makefile --stop
    ./bootstrap -d
    rm -rf config configure build/make/Makefile-auto.in
    rm -f src/doc/en/installation/*.txt
    rm -rf src/doc/en/reference/spkg/*.rst
    rm -f src/doc/en/reference/repl/*.txt
    rm -f environment.yml
    rm -f src/environment.yml
    rm -f environment-optional.yml
    rm -f src/environment-optional.yml
    src/doc/bootstrap:92: installing src/doc/en/installation/arch.txt and src/doc/en/installation/arch-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/debian.txt and src/doc/en/installation/debian-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/fedora.txt and src/doc/en/installation/fedora-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/cygwin.txt and src/doc/en/installation/cygwin-optional.txt
    src/doc/bootstrap:92: installing src/doc/en/installation/homebrew.txt and src/doc/en/installation/homebrew-optional.txt
    src/doc/bootstrap:66: installing environment.yml, environment-optional.yml, src/environment.yml and src/environment-optional.yml
    src/doc/bootstrap:103: installing src/doc/en/reference/spkg/*.rst
    src/doc/bootstrap:131: installing src/doc/en/reference/repl/options.txt
    bootstrap:73: installing 'config/config.rpath'
    m4/sage_spkg_configures.m4:106: error: AC_SUBST: `SAGE_ENABLE_cgal-swig-bindings' is not a valid shell variable name
    m4/sage_spkg_enable.m4:31: SAGE_SPKG_ENABLE is expanded from...
    m4/sage_spkg_collect.m4:324: SAGE_SPKG_COLLECT is expanded from...
    m4/sage_spkg_configures.m4:106: the top level
    autom4te: /usr/bin/m4 failed with exit status: 1
    aclocal: error: autom4te failed with exit status: 1
    make[1]: *** [configure] Error 1
    make: *** [all-toolchain] Error 2
    ```
- cgal-bindings forks from cgal-swig-bindings, but did not be updated for 2 years.


# Resources && Understanding
- [bash languages](https://ryanstutorials.net/bash-scripting-tutorial/bash-script.php)
- [Python framework and instructions](https://pip.pypa.io/en/stable/development/)
