# Android Dynamic Partition Tools Suite

[简体中文](README_zh-CN.md)

A standalone build system for Android Dynamic Partition tools.

This project builds Android Dynamic Partition related tools:

- `lpmake`
- `lpadd`
- `lpflash`
- `lpunpack`
- `lpdump`

## Features

- One-command build with `build.sh`
- Automatically builds required static libraries
- Automatically downloads and builds protobuf
- No Android SDK, Android NDK, or full Android build environment required
- Supports multiple architectures:
  - x86_64 (`amd64`)
  - ARM64 (`aarch64`)

## Origin

This project is based on:

- Dargons10/lpunpack_and_lpmake

Original repository:

https://github.com/Dargons10/lpunpack_and_lpmake

The original project provides a standalone build system for:

- `lpmake`
- `lpunpack`

This project extends the original build system with:

- Unified `build.sh`
- Additional Android Dynamic Partition tools:
  - `lpadd`
  - `lpflash`
  - `lpdump`
- Automatic static library compilation
- Automatic protobuf build
- Multi-architecture build support
- GitHub Actions release builds

## Requirements

### Build Dependencies

The following packages are required to build this project:

- Linux operating system
- Git
- Make
- Clang / LLVM
- GNU binutils
- CMake
- Autoconf
- Automake
- Libtool
- pkg-config
- Perl
- Python 3

## Required commands:

```text
git
make
clang
clang++
ar
strip
cmake
autoconf
automake
libtool
pkg-config
perl
python3
Debian / Ubuntu
```
## Install all dependencies:
```text
sudo apt update

sudo apt install -y \
    git \
    make \
    clang \
    llvm \
    binutils \
    cmake \
    autoconf \
    automake \
    libtool \
    pkg-config \
    perl \
    python3
 ```
## Notes
The build script automatically downloads and builds protobuf.
No additional protobuf package installation is required.
Required static libraries are built automatically during the build process.

### Build
Run:
./build.sh
The build script will:
Detect the host architecture
Prepare protobuf dependency
Build required Android static libraries
Generate protobuf source files
Build LP tools
Strip output binaries
Debug Build
Show detailed build commands:
DEBUG=1 ./build.sh

### Output
After successful build:
```text
bin/
├── lpmake
├── lpadd
├── lpflash
├── lpunpack
└── lpdump
```
### Usage
Dump dynamic partition metadata:
./bin/lpdump super.img
Create dynamic partition images:
./bin/lpmake

### Clean Build
Build artifacts can be removed safely:
rm -rf bin third_party
They will be regenerated automatically during the next build.

### License
Based on Android Open Source Project components.
