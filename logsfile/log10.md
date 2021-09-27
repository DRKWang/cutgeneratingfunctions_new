# Target

Try to install CGAL_swig_bindings into python3, and then install it into sage.

# So far

- The bindings can be installed into python3 with ```python3 install setup.py``` , but it can not be installed with \
```pip3 install git+https://github.com/CGAL/cgal-swig-bindings.git@master```, whose format comes from [this](https://stackoverflow.com/questions/20101834/pip-install-from-git-repo-branch). The command error is as follows:
```
cgal-swig-bindings git:(master) ✗ pip3 install git+https://github.com/CGAL/cgal-swig-bindings.git@master
Collecting git+https://github.com/CGAL/cgal-swig-bindings.git@master
  Cloning https://github.com/CGAL/cgal-swig-bindings.git (to revision master) to /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-req-build-pda6f2c2
    ERROR: Command errored out with exit status 1:
     command: /Library/Frameworks/Python.framework/Versions/3.7/bin/python3.7 -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'/private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-req-build-pda6f2c2/setup.py'"'"'; __file__='"'"'/private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-req-build-pda6f2c2/setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj
         cwd: /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-req-build-pda6f2c2/
    Complete output (8 lines):
    running egg_info
    creating /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info
    writing /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info/PKG-INFO
    writing dependency_links to /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info/dependency_links.txt
    writing requirements to /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info/requires.txt
    writing top-level names to /private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info/top_level.txt
    writing manifest file '/private/var/folders/83/5bth00bn2m37tw719j2f2p380000gn/T/pip-pip-egg-info-4o85vigj/cgal.egg-info/SOURCES.txt'
    error: package directory 'build/build-python/CGAL' does not exist
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
```

The reason seem to be lack of package directory 'build/build-python/CGAL' in the original downloaded package, whereas this directory will be built automatically when we use ```python3 install setup.py```. The difference between the [cgal_swig_bindings](https://github.com/CGAL/cgal-swig-bindings) and [cgal_bindings](https://pypi.org/project/cgal-bindings/#files), which can be installed via pip3 tarball, is that the latter contains 'build-python/CGAL', which means it does not  need to be built from the source, whereas the former will be built from the source.



