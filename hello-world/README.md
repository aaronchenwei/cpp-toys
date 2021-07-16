# C++ Hello World with CMake

## Quick Guide

We start with a simple C++ program:

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello World!" << std::endl;
}
```

Now we create a build directory (out of source compilation), change to it, and configure the project:

```zsh
$ mkdir build
$ cd build/
$ cmake ..
```

Then we build through

```zsh
$ make
```

## Name and location of the build directory

There is nothing special about `build/` - we could have done this instead:

```zsh
$ mkdir -p /tmp/debug
$ cd /tmp/debug
$ cmake /path/to/source
$ make
```

## Benefits of out-of-source compilation

* CMake looks for CMakeLists.txt and processes this file
* CMake puts everything into `${PROJECT_BINARY_DIR}` and does not pollute `${PROJECT_SOURCE_DIR}`
* We can build different binaries with the same source:
    * Sequential and parallel builds
    * Debug build or optimized build
    * Production and debugging compilations
