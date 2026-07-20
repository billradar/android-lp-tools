# Android LP Tools

[简体中文](README_zh-CN.md)

A standalone build system for Android Dynamic Partition tools.

This project builds the following tools:

- `lpmake`
- `lpadd`
- `lpflash`
- `lpunpack`
- `lpdump`

## Features

- One-command build with `build.sh`
- Automatically builds required static libraries
- Automatically downloads and builds protobuf
- Supports multiple architectures:
  - ARM64 (`aarch64`)
  - x86_64

## Build

Run:

```bash
./build.sh
The build script will:
Detect the host architecture
Prepare protobuf dependency
Build required Android static libraries
Generate protobuf source files
Build LP tools
Strip output binaries
Debug Build
To show detailed build commands:
DEBUG=1 ./build.sh
Output
After a successful build:
bin/
├── lpmake
├── lpadd
├── lpflash
├── lpunpack
└── lpdump
Usage
Dump dynamic partition metadata:
./bin/lpdump super.img
Create dynamic partition images:
./bin/lpmake
Requirements
Linux
clang / clang++
ar
make
git
The build script automatically handles protobuf compilation.
License
Based on Android Open Source Project components.
