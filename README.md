jdk8u-dev patch
---------------

## Compile OpenJDK8 with LLVM

```
export CC=clang
export CXX=clang++

sh configure --with-debug-level=fastdebug
make images
```

## Clang static analyzer

```
scan-build sh configure --with-debug-level=fastdebug
scan-build make CONF=fastdebug JOBS=8
```
