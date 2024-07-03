[Tiếng Việt](./README_Vietnamese.md) | [English](../README.md) | [中国人](./README_Chinese.md) | [日本語](./README_Japanese.md) | [русский](./README_Russian.md)
## Google Test のガイドライン
#### インストール手順
まず、プロジェクトの GitHub から Google Test をクローンします。https://github.com/google/googletest にリンクするか、このリポジトリをローカル デバイスにクローンします。
```bash
$ git clone https://github.com/google/googletest.git
```
または
```bash
$ git clone https://github.com/ionicola/google_test_1.14.0.git
```
次に、CMake を使用してフレームワークをビルドし、cmd/powershell/gitbash で以下の各コマンド ラインを実行します。(以下のオプションを 1 つ選択してください)
**MSYS2** C++ コンパイラをインストールする場合は、次のコマンドを実行します。
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "Unix Makefiles" ..
$ make -j4
```
または、**MinGW64** C++ コンパイラをインストールする場合は、次のコマンドを実行します。
```bash
$ cd googletest/
$ mkdir build/
$ cd build/
$ cmake -G "MinGW Makefiles" ..
$ make -j4
```
(このリポジトリには作成者によって事前に構築されたファイルが含まれているため、このリポジトリを使用する場合は上記の手順を実行する必要がない場合があります。)
`build/lib/` フォルダーに移動し、`lib/` フォルダー内のすべてのビルド済みライブラリ ファイルをコピーします。このファイルを `msys64/ucrt64/lib/` または `MingW64/lib/` フォルダーに貼り付けます (これらのフォルダーは、C++ コンパイラをインストールした **MSYS2** または **MinGW64** セクションにあります)。
ビルド済みライブラリ ファイルには次のものが含まれます。
```
libgmock.a
libgmock_main.a
libgtest.a
libgtest_main.a
```
次に、`googletest/include/` フォルダに移動し、`gtest` フォルダをコピーします (このフォルダにはヘッダー ファイルが含まれています)。このファイルを `msys64/ucrt64/include/` または `MingW64/include/` フォルダに貼り付けます。
最後に、`googlemock/include/` フォルダに移動し、`gmock` フォルダをコピーします (このフォルダにはヘッダー ファイルが含まれています)。このファイルを `msys64/ucrt64/include/` または `MingW64/include/` フォルダに貼り付けます。
これで、プロジェクトでこのヘッダーを使用して Google Test framework を使用できるようになります。
```.cpp
#include <gtest/gtest.h>
```