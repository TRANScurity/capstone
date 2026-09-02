# Build the executables

## Install required compilers (Ubuntu/Debian)

```bash
sudo apt-get update
sudo apt-get install -y build-essential gcc-mingw-w64-x86-64
```

## Build Linux x86-64 libraries

```bash
CAPSTONE_ARCHS=x86 \
CAPSTONE_BUILD_CORE_ONLY=yes \
CAPSTONE_STATIC=yes \
CAPSTONE_SHARED=yes \
make -j"$(nproc)" BUILDDIR=build/linux-x86_64
```

Outputs:

```
build/linux-x86_64/libcapstone.so.5
build/linux-x86_64/libcapstone.a
```

Optionally create the conventional linker symlink:

```bash
ln -sf libcapstone.so.5 build/linux-x86_64/libcapstone.so
```

## Build Windows x86-64 libraries

```bash
CFLAGS='-O3 -DCAPSTONE_SHARED' \
LDFLAGS='-Wl,--out-implib,build/windows-x86_64/capstone.dll.a' \
CAPSTONE_ARCHS=x86 \
CAPSTONE_BUILD_CORE_ONLY=yes \
CAPSTONE_STATIC=yes \
CAPSTONE_SHARED=yes \
make -j"$(nproc)" \
BUILDDIR=build/windows-x86_64 \
CROSS=x86_64-w64-mingw32- \
VERSION_EXT=dll
```

Outputs:

```
build/windows-x86_64/capstone.dll
build/windows-x86_64/capstone.dll.a
build/windows-x86_64/capstone.lib
```

For JNA, the runtime files are:

```
Linux:   libcapstone.so.5
Windows: capstone.dll
```

The .a, .dll.a, and .lib files are not required for JNA runtime loading.
