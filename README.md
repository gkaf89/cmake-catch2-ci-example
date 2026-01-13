# cmake-catch2-ci-example

This repository contains a minimal CMake-based project building a trivial C++ library with [Catch2-based](https://github.com/catchorg/Catch2) unit tests.

## Build

Install CMake and Catch2 in version 3 globally. Then follow the steps below:

```shell
$ mkdir build && cd build
$ cmake .. -DBUILD_TESTING=On
$ make
$ make test
```
