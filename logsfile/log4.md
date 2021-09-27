# Targets


1. Set the sage and CGAL-swig in the same platform.
2. Read the papers.
3. Email the github account.

# Results

1. There are 2 ways to make it. And it turns out that the code made from conda are the same as the code made from swig except the latter has more .cxx files

- Install CGAL from conda.
    Run ```conda install -c conda-forge cgal```. After installing it, find "CGAL" folder under the ```site-packages``` directory and move it to the ```/Users/binshuaiwang/Sage/sage-9.2/local/lib/python3.8/sites-packages```.

- Compile the source C code into python code.

    Run the following code in the terminal:
    
    ```brew install cgal```

    ```brew install swig```

    ```git clone https://github.com/CGAL/cgal-swig-bindings.git```

    ```cd cgal-swig-bindings```

     Replace the python paths below with the correct version for your system.

    ```cmake -DCGAL_DIR=/usr/local/lib/cmake/CGAL \
    -DBUILD_PYTHON=ON \
    -DBUILD_JAVA=OFF \
    -DPYTHON_LIBRARIES=/usr/local/lib/python3.9 \
    -DPYTHON_LIBRARY=/usr/local/Cellar/python@3.9/3.9.1/Frameworks/Python.framework/Versions/3.9/lib/libpython3.9.dylib\
    -DPython_FRAMEWORKS=/usr/local/Cellar/python@3.9/3.9.1/Frameworks/Python.framework \
    -DPYTHON_INCLUDE_DIR=/usr/local/Cellar/python@3.9/3.9.1/Frameworks/Python.framework/Headers ```
    
    ```make```
    
    Get into the ```cgal-swig-bindings/build-python``` and move the "CGAL" folder to the ```/Users/binshuaiwang/Sage/sage-9.2/local/lib/python3.8/sites-packages```.

- Although we can import it successfully, it can not be used right now because it has some confliction with sage in terms of the data type. 

![image.png](attachment:image.png)
