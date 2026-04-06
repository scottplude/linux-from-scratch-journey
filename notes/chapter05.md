# Linux From Scratch (LFS) Build Journey

🪓 Building a complete Linux system from source — no shortcuts.

This repository documents my progress through the Linux From Scratch (LFS) book, including notes, commands, troubleshooting, and lessons learned along the way.

## 📌 Project Goals

- Understand how Linux systems are built from the ground up
- Create a fully functional custom Linux environment
- Document each step for learning and reference

## 🧱 Current Progress

- ✅ Environment setup complete (Chapters 1–4)
- 🔄 Building temporary toolchain (Chapter 5)

## 🔧 Chapter 5 Summary

In this phase, I built a **temporary toolchain** used to construct the final system. This includes:

- Binutils (Pass 1)
- GCC (Pass 1)
- Linux API Headers
- Glibc
- Libstdc++

These tools are installed into `$LFS/tools` and are isolated from the host system.

## 🔁 General Build Process

```bash
tar -xf package.tar.xz
cd package
mkdir build && cd build

../configure --prefix=$LFS/tools \
--with-sysroot=$LFS \
--target=$LFS_TGT \
--disable-nls \
--disable-werror

make
make install

## 🧱 Components Built

- Binutils (Pass 1)
- GCC (Pass 1)
- Linux API Headers
- Glibc
- Libstdc++

## ⚙️ Key Concepts

### Cross Compilation

Tools are built targeting:

```bash
$LFS_TGT

Installation Location
--prefix=$LFS/tools
Keeps temporary tools isolated from the host.

Build Pattern:
Extract package
Create build directory
Configure
Compile
Install

⚠️  Notes / Gotchas
Always verify environment variables:
$LFS
$LFS_TGT
Do not skip build directories (prevents pollution)
Errors often stem from missing dependencies or incorrect paths
