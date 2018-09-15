jdk8u-dev patch
---------------

## Compile OpenJDK8 with LLVM for mips64el

```
export CC=clang
export CXX=clang++

./configure
make images
```

## FAQ

* Q: error: unknown instruction for inline asm "cvt.s.pl %0, %4\n\t"
* A: The missing instructions for mips64el was [implemented by Aleksandar Beserminji!](https://reviews.llvm.org/D50437)
