# Installation of the voronoi_intersection code

Dependences
-----------

It may work with older versions, but the more recent, the safer.

* **Gcc** 4.8.1 (C++11 compatibility)
+ **CImg** 1.5.9
+ **Eigen** 3.0
+ **Suitesparse** 4.4.1
+ **Tbb** 4.0
+ **Boost** 1.48
+ **Cgal** 4.0

Construction and compilation
----------------------------

Create a temporary folder

``` sh
cd path/to/voronoi_intersection/
mkdir build
cd build
```
cmake may not find some librairies path by itself. If it doesn't, add them as follow:

``` sh
ccmake .. -DEIGEN3_INCLUDE_DIR=path/to/eigen3/include/eigen3 -DCImg_INCLUDE_DIR=path/to/CImg/include/ -DCMAKE_INCLUDE_PATH=path/to/cmake/include/ -DCMAKE_LIBRARY_PATH=path/to/cmake/lib/ -DTBB_ROOT_DIR=path/to/tbb/ -DSUITESPARSECONFIG_LIBRARY=path/to/libsuitesparseconfig.a 
```

Add paths to any librairy that cmake may have not found and compile

``` sh
make
```


# For old systems

For system such as ubuntu 12.04 or systems where you are not root, the sources may not be up to date. You can install the dependences localy via linuxbrew, which has is own sources.

Dependences of linuxbrew
------------------------

``` sh
sudo apt-get install build-essential curl git m4 ruby texinfo libbz2-dev libcurl4-openssl-dev libexpat-dev libncurses-dev zlib1g-dev
```

Install of linuxbrew
--------------------

``` sh
ruby -e "$(wget -O- https://raw.github.com/Homebrew/linuxbrew/go/install)"
```

Environment variables
---------------------

Add these lines at the end of your ~/.bashrc, to adapt your ENV variables

``` sh
export PATH="$HOME/.linuxbrew/bin:$PATH"
export MANPATH="$HOME/.linuxbrew/share/man:$MANPATH"
export INFOPATH="$HOME/.linuxbrew/share/info:$INFOPATH"
```

Errors and updates
------------------

``` sh
brew doctor
brew update
brew install cgal
```

Library installation
--------------------

``` sh
brew install <libraryname>
```

Finally install the program as described higher

# For old systems with gcc < 4.8.1

Check the instructions on the [Standalone-Installation](https://github.com/Homebrew/linuxbrew/wiki/Standalone-Installation) website.
It allows you to use the linuxbrew compiler chain instead of the old one installed on your machine
For more information about how to use linuxbrew and how to correct possible errors, check [linuxbrew](https://github.com/Homebrew/linuxbrew/) website.
