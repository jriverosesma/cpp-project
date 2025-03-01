# C++ Project Template

## Table of contents

1. [Overview](README.md#1-overview)
2. [Features](README.md#2-features)
3. [Install](README.md#3-install)
4. [Tests](README.md#4-tests)
---

## 1. Overview

This repository contains an example of a simple C++ library and can be used as a template for other projects.

## 2. Features

In this repository you will find the following items:

- C++ source code: `src` and `include` folder.
- Unit tests for `MyLib` using [Catch2](https://github.com/catchorg/Catch2).
- Python binding of C++ function of `MyLib`: `src/binding.cpp`.
- CMake build instructions for a static `MyLib` library: `CMakeLists.txt`.
- Example C++ project using `MyLib` as a library: `example/`.
- Example of Python script using C++ `MyLib` binding for Python: `example/main.py`.
- Dockerfile for creating an Ubuntu image and building `MyLib` project inside it: `Dockerfile`.

## 3. Install

### 3.1 Pre-requisites

- C++ compiler.
- CMake.
- Optional: Python >= 3 to use [pre-commit](https://pre-commit.com).

### 3.2 Setup

Run the following command to build the `MyLib` project and its corresponding Python binding:

```bash
./build_all.sh -t <build_type> # `build_type` can be "debug" or "release" and defaults to "release" if not specified
```

The above command also builds an example C++ project using the `MyLib` library and runs a Python script using the `MyLib` Python binding.

**Note**: You can run `chmod +x build_all.sh` to add execution permissions to the build script.

### 3.3 Set up pre-commit (Optional)

The following instructions allows to set up pre-commit for code development in this project:

```bash
conda create -n mylib python=3.10 --no-default-pacakges -y
conda activate mylib
pip install black clang-format pre-commit
pre-commit install
```

## 4. Tests

After building the `MyLib` project you can run the project tests using the following command:

```bash
ctest --test-dir build -R MyLibTests
```
