jdk8u patch
-----------

## Compile OpenJDK 8 with LLVM

```
export CC=clang
export CXX=clang++
export CFLAGS="-fintegrated-as"
export CXXFLAGS="$CFLAGS"

./configure
make images
```

## FAQ

Q: Error: junk at end of line, first unrecognized character is `0'
A: binutils/gas compatibility issue, [You need to explicitly pass -fintegrated-as for mips64, btw. -fno-integrated-as is the default for that target.](https://github.com/android-ndk/ndk/issues/399#issuecomment-302331441)


