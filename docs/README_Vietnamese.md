[Tiếng Việt](./README_Vietnamese.md) | [English](../README.md) | [中国人](./README_Chinese.md) | [日本語](./README_Japanese.md) | [русский](./README_Russian.md)
## Hướng dẫn sử dụng Google Test
#### Hướng dẫn cài đặt
Đầu tiên, clone Google Test từ kho lưu trữ GitHub của dự án. Có thể clone từ link https://github.com/google/googletest hoặc clone kho lưu trữ này về thiết bị cục bộ của bạn:
```bash
$ git clone https://github.com/google/googletest.git
```
hoặc
```bash
$ git clone https://github.com/ionicola/google_test_1.14.0.git
```
Tiếp theo, sử dụng CMake để build framework, sử dụng cmd/powershell/gitbash trên thiết bị cục bộ của bạn và chạy lần lượt các dòng lệnh dưới đây. (Hãy chọn 1 lựa chọn)
Nếu bạn đã cài đặt C++ compiler bằng **MSYS2**, hãy sử dụng các lệnh dưới đây:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "Unix Makefiles" ..
$ make -j4
```
Hoặc nếu bạn đã cài đặt C++ compiler bằng **MinGW64**, hãy sử dụng các lệnh dưới đây:
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "MinGW Makefiles" ..
$ make -j4
```
(Nếu bạn sử dụng repository này, chúng tôi đã build sẵn những thứ cần thiết và bạn không cần sử dụng các dòng lệnh phía trên nữa.)
Tiếp theo, di chuyển tới thư mục `build/lib/` và sao chép toàn bộ file thư viện đã được xây dựng ở trong folder `lib/`. Paste những file này vào `msys64/ucrt64/lib/` hoặc `MingW64/lib/` (các thư mục này nằm trong phần **MSYS2** hoặc **MinGW64** mà bạn đã cài đặt C++ compiler). Các file này có tên như sau:
```
libgmock.a
libgmock_main.a
libgtest.a
libgtest_main.a
```
Tiếp theo, di chuyển tới thư mục `googletest/include/` và sao chép thư mục `gtest` (thư mục này bao gồm các file header của framework). Paste thư mục này vào `msys64/ucrt64/include/` hoặc `MingW64/include/`.
Cuối cùng, di chuyển tới thư mục `googletest/include/` và sao chép thư mục `gmock` (thư mục này bao gồm các file header của framework). Paste thư mục này vào `msys64/ucrt64/include/` hoặc `MingW64/include/`. 
Hoàn thành, bây giờ bạn đã có thể sử dụng Google Test framework bằng cách include header trong project của bạn:
```.cpp
#include <gtest/gtest.h>
```