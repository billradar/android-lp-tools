# Android LP Tools

[English](README.md)

一个用于构建 Android 动态分区（Dynamic Partition）工具的独立构建项目。

本项目用于生成以下 Android 动态分区工具：

- `lpmake`
- `lpadd`
- `lpflash`
- `lpunpack`
- `lpdump`

## 特性

- 使用 `build.sh` 一键构建
- 自动编译所需静态库
- 自动下载并编译 protobuf
- 不需要完整 Android SDK、NDK 或 Android Build 环境
- 支持多种架构：

  - x86_64 (`amd64`)
  - ARM64 (`aarch64`)

## 环境依赖

### 编译依赖

构建本项目需要：

- Linux 操作系统
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

需要的命令：

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
```

### Debian / Ubuntu

安装全部依赖：

```bash
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

### 说明

- 构建脚本会自动下载并编译 protobuf。
- 不需要额外安装 protobuf 开发包。
- 所需静态库会在构建过程中自动生成。

## 构建

执行：

```bash
./build.sh
```

构建脚本会自动完成：

1. 检测当前系统架构
2. 准备 protobuf 依赖
3. 编译 Android 相关静态库
4. 生成 protobuf 源文件
5. 编译 LP 工具
6. 裁剪输出二进制文件

## 调试构建

显示详细编译命令：

```bash
DEBUG=1 ./build.sh
```

## 输出文件

构建成功后：

```text
bin/
├── lpmake
├── lpadd
├── lpflash
├── lpunpack
└── lpdump
```

## 使用方法

查看动态分区信息：

```bash
./bin/lpdump super.img
```

创建动态分区镜像：

```bash
./bin/lpmake
```

## 清理构建文件

以下目录可以安全删除：

```bash
rm -rf bin third_party
```

下次执行构建时会自动重新生成。

## 许可证

本项目基于 Android Open Source Project 相关组件。
