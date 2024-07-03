[Tiếng Việt](docs/README_Vietnamese.md) | [English](./README.md) | [中国人](docs/README_Chinese.md) | [日本語](docs/README_Japanese.md) | [русский](docs/README_Russian.md)
## Guideline for Google Test
#### Instruction for installing
First, clone the Google Test from project's GitHub. Link to https://github.com/google/googletest or clone this repository to your local device:
```bash
$ git clone https://github.com/google/googletest.git
```
or
```bash
$ git clone https://github.com/ionicola/google_test_1.14.0.git
```
Next, build the framework using CMake, run each command lines below in your cmd/powershell/gitbash. (Choose 1 option below)
If you install **MSYS2** C++ compiler, run the following command:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "Unix Makefiles" ..
$ make -j4
```
Or if you install **MinGW64** C++ compiler, run the following command:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "MinGW Makefiles" ..
$ make -j4
```
(This repository includes files pre-built by the author, you may not need to do the above steps if using this repository.)

Move to folder `build/lib/` and copy all built library files in the `lib/` folder. Paste this files to `msys64/ucrt64/lib/` or `MingW64/lib/` folder (these folders are located in the **MSYS2** or **MinGW64** section where you installed the C++ compiler).
Built library files include:
```
libgmock.a
libgmock_main.a
libgtest.a
libgtest_main.a
```
Then, move to folder `googletest/include/` and copy folder `gtest` (this folder include header files). Paste this files to `msys64/ucrt64/include/` or `MingW64/include/` folder.
Finally, move to folder `googlemock/include/` and copy folder `gmock` (this folder include header files). Paste this files to `msys64/ucrt64/include/` or `MingW64/include/` folder.
Now, you can use Google Test framework by using this header in your project: 
```.cpp
#include <gtest/gtest.h>
```
