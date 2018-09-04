jdk8u-dev patch
---------------

## Compile OpenJDK 8 with LLVM for mips64el

```
export CC=clang
export CXX=clang++
export CFLAGS="-fintegrated-as"
export CXXFLAGS="$CFLAGS"

./configure
make images
```

## FAQ

Q: Modified LLVM toolchain?
A: Yes! the biggest testcase is [Linux Kernel](https://github.com/loongson-community/linux-stable/issues)

Q: Error: junk at end of line, first unrecognized character is `0'
A: binutils/gas compatibility issue, [You need to explicitly pass -fintegrated-as for mips64, btw. -fno-integrated-as is the default for that target.](https://github.com/android-ndk/ndk/issues/399#issuecomment-302331441)

Q: error: unknown instruction for inline asm "cvt.s.pl %0, %4\n\t"
A: [Implemented by Aleksandar Beserminji](https://reviews.llvm.org/D50437)!
