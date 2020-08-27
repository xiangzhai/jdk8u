jdk8u-dev patch
---------------

## Compile OpenJDK8 with LLVM

```
export CC=clang
export CXX=clang++

sh configure --with-debug-level=fastdebug
make images
```
