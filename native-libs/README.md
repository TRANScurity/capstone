# Capstone 5.0.9 native libraries

These release libraries target 64-bit x86-64 hosts and contain only Capstone's
x86 disassembler backend (16-bit, 32-bit, and 64-bit x86 decoding).

## Linux x86-64

- `linux-x86_64/libcapstone.so.5`: versioned shared library
- `linux-x86_64/libcapstone.so`: unversioned shared-library copy for linking
- `linux-x86_64/libcapstone.a`: static library

Built with GCC 11.4.0 under Ubuntu 22.04/WSL2.

## Windows x86-64

- `windows-x86_64/capstone.dll`: shared library
- `windows-x86_64/capstone.dll.a`: GNU/MinGW import library for the DLL
- `windows-x86_64/capstone.lib`: GNU static archive

Built with the Ubuntu MinGW-w64 x86-64 cross-compiler. The `.lib` file is a GNU
archive, not an MSVC-format import library; use `capstone.dll.a` when linking
with MinGW.

Public headers remain in the repository's `include/capstone` directory.

## Build configuration

The equivalent Make variables are:

```text
CAPSTONE_ARCHS=x86
CAPSTONE_BUILD_CORE_ONLY=yes
CAPSTONE_STATIC=yes
CAPSTONE_SHARED=yes
```
