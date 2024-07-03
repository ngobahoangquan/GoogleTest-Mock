[Tiếng Việt](./README_Vietnamese.md) | [English](../README.md) | [中国人](./README_Chinese.md) | [日本語](./README_Japanese.md) | [русский](./README_Russian.md)
## Руководство для Google Test
#### Инструкция по установке
Сначала клонируйте Google Test из GitHub проекта. Ссылка на https://github.com/google/googletest или клонируйте этот репозиторий на свое локальное устройство:
```bash
$ git clone https://github.com/google/googletest.git
```
или
```bash
$ git clone https://github.com/ionicola/google_test_1.14.0.git
```
Затем создайте платформу с помощью CMake, запустите каждую командную строку ниже в вашем cmd/powershell/gitbash. (Выберите 1 вариант ниже)
Если вы устанавливаете компилятор C++ **MSYS2**, выполните следующую команду:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "Unix Makefiles" ..
$ make -j4
```
Или, если вы устанавливаете компилятор C++ **MinGW64**, выполните следующую команду:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "MinGW Makefiles" ..
$ make -j4
```
(Этот репозиторий включает в себя файлы, предварительно созданные автором; при использовании этого репозитория вам, возможно, не потребуется выполнять описанные выше действия.)
Перейдите в папку `build/lib/` и скопируйте все файлы встроенной библиотеки в папку `lib/`. Вставьте эти файлы в папку `msys64/ucrt64/lib/` или `MingW64/lib/` (эти папки расположены в разделе **MSYS2** или **MinGW64**, где вы установили компилятор C++).
Встроенные файлы библиотеки включают в себя:
```
libgmock.a
libgmock_main.a
libgtest.a
libgtest_main.a
```
Затем перейдите в папку `googletest/include/` и скопируйте папку `gtest` (эта папка содержит файлы заголовков). Вставьте эти файлы в папку `msys64/ucrt64/include/` или `MingW64/include/`.
Наконец, перейдите в папку `googlemock/include/` и скопируйте папку `gmock` (эта папка содержит файлы заголовков). Вставьте эти файлы в папку `msys64/ucrt64/include/` или `MingW64/include/`.
Теперь вы можете использовать Google Test framework, используя этот заголовок в своем проекте:
```.cpp
#include <gtest/gtest.h>
```
