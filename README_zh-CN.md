# Android LP Tools

[English](README.md)

一个用于构建 Android 动态分区（Dynamic Partition）工具的独立构建项目。

本项目用于生成以下工具：

- `lpmake`
- `lpadd`
- `lpflash`
- `lpunpack`
- `lpdump`

## 特性

- 使用 `build.sh` 一键构建
- 自动编译所需静态库
- 自动下载并编译 protobuf
- 支持多种架构：

  - ARM64 (`aarch64`)
  - x86_64

## 构建

运行：

```bash
./build.sh
构建脚本会自动完成：
检测当前系统架构
准备 protobuf 依赖
编译 Android 相关静态库
生成 protobuf 源文件
编译 LP 工具
优化输出二进制文件
调试构建
查看详细编译命令：
DEBUG=1 ./build.sh
输出文件
构建成功后：
bin/
├── lpmake
├── lpadd
├── lpflash
├── lpunpack
└── lpdump
使用示例
查看动态分区信息：
./bin/lpdump super.img
创建动态分区镜像：
./bin/lpmake
环境要求
需要：
Linux
clang / clang++
ar
make
git
protobuf 会由构建脚本自动处理。
许可证
本项目基于 Android Open Source Project 相关组件。

