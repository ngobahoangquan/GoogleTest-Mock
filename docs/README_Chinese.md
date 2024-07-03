[Tiếng Việt](./README_Vietnamese.md) | [English](../README.md) | [中国人](./README_Chinese.md) | [日本語](./README_Japanese.md) | [русский](./README_Russian.md)
## Google Test 指南
#### 安装说明
首先，从项目的 GitHub 克隆 Google Test。链接至 https://github.com/google/googletest 或将此存储库克隆到本地设备：
```bash
$ git clone https://github.com/google/googletest.git
```
或者
```bash
$ git clone https://github.com/ionicola/google_test_1.14.0.git
```
接下来，使用 CMake 构建框架，在 cmd/powershell/gitbash 中运行以下每个命令行。（选择下面的 1 个选项）
如果您安装了 **MSYS2** C++ 编译器，请运行以下命令：
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "Unix Makefiles" ..
$ make -j4
```
或者如果您安装了**MinGW64** C++ 编译器，请运行以下命令：
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "MinGW Makefiles" ..
$ make -j4
```
（此存储库包含作者预先构建的文件，如果使用此存储库，则可能不需要执行上述步骤。）
移动到文件夹“build/lib/”并复制“lib/”文件夹中的所有构建库文件。将这些文件粘贴到“msys64/ucrt64/lib/”或“MingW64/lib/”文件夹（这些文件夹位于您安装 C++ 编译器的 **MSYS2** 或 **MinGW64** 部分）。
构建库文件包括：
```
libgmock.a
libgmock_main.a
libgtest.a
libgtest_main.a
```
然后，移动到文件夹 `googletest/include/` 并复制文件夹 `gtest`（此文件夹包含头文件）。将此文件粘贴到 `msys64/ucrt64/include/` 或 `MingW64/include/` 文件夹。
最后，移动到文件夹 `googlemock/include/` 并复制文件夹 `gmock`（此文件夹包含头文件）。将此文件粘贴到 `msys64/ucrt64/include/` 或 `MingW64/include/` 文件夹。
现在，您可以在项目中使用此标头来使用 Google Test framework：
```.cpp
#include <gtest/gtest.h>
```
