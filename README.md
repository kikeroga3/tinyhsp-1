# TinyHSP

![miyuzu_header](https://cloud.githubusercontent.com/assets/13228693/22240053/9dba8334-e25c-11e6-8543-7a537abf6664.png)

TinyHSPは**最軽量のHSPを作成する**ことを目標にしたプロジェクトです。

## ビルド方法

### MinGWでTinyHSPをコンパイルする方法

TinyHSPはOpenGLとGLFWというライブラリを使っているので、
それらを導入する必要があります。

導入の手順:

1. GLFWをダウンロードする
2. include内のGLFWフォルダをMinGW内のincludeフォルダにコピーする
3. 2つの.aファイルをMinGW内のlibフォルダにコピーする
4. glfw3.dllをプロジェクトのフォルダにコピーする

#### 1. GLFWをダウンロードする

OpenGLはMinGWに最初から入っています。
**GLFWライブラリは[GLFWのダウンロードページ](http://www.glfw.org/download.html)から入手**します。

GLFWには32bit版と64bit版があります。
仮に64bit版をダウンロードしたとして話を進めます。

#### 2. include内のGLFWフォルダをMinGW内のincludeフォルダにコピーする

ダウンロードしたフォルダの中に、
`include` というフォルダが入っています。
この中に `GLFW` というフォルダがあるので、
その**GLFWフォルダをMinGWのincludeフォルダにコピー**します。

#### 3. 2つの.aファイルをMinGW内のlibフォルダにコピーする

ダウンロードしたフォルダの中に、
`lib-mingw-w64` というフォルダが入っているので、
この中にある、

- libglfw3.a
- libglfw3dll.a

という**2つの.aファイルをMinGWのlibフォルダにコピー**します。

#### 4. glfw3.dllをプロジェクトのフォルダにコピーする

上と同じ `lib-mingw-w64` フォルダ内に、

- glfw3.dll

というファイルがあるので、
作成したいプロジェクト用のフォルダ内にコピーします。

例えば、**glfw3.dllをtinyhsp.cがあるフォルダと同じ場所にコピー**します。

#### コンパイルする

コンパイルは以下のようにします。

`$ g++ tinyhsp.cpp -o tinyhsp -std=c++11 -lglfw3dll -lopengl32`

## 更新履歴

- 2017/02/10 
- 2017/02/09 neteruhspにGUIを実装する3
- 2017/02/08 neteruhspにGUIを実装する2
- 2017/02/07 neteruhspにGUIを実装する
- 2017/02/05 stb\_image.hを使って画像を描画する
- 2017/01/31 空白文字を考慮して文字列を描画する
- 2017/01/30 Unicode文字列を描画するプロトタイプ
- 2017/01/28 stb\_truetype.hを使って文字を描画するテスト／README.mdにイラストを追加
- 2017/01/27 wait命令が使えるプロトタイプ
- 2017/01/26 改行方式でpset命令も使えるプロトタイプ
- 2017/01/25 改行方式でprint命令のみ使えるプロトタイプ
- 2017/01/24 作り直しを始める／ヘッダー画像を追加／start.hspを読み込むだけのプロトタイプ
- 2017/01/23 作り直しを検討／これ以前のプログラムを1つのディレクトリにまとめた
- 2017/01/22 ディレクトリ構成を変更
- 2017/01/21 README.mdにイラストを追加
- 2017/01/18 パーサを修正
- 2017/01/17 テスト用のMakefileを作成
- 2017/01/16 パーサにテスト用コードを追加
- 2017/01/15 命令トークンを識別するように変更
- 2017/01/14 ピクセル操作のためのファイルを追加
- 2017/01/13 字句解析器を修正（長い関数を分割）
- 2017/01/12 ファイル読み込み用のユーティリティを追加
- 2017/01/11 ディレクトリ構成およびMakefileの変更
- 2017/01/10 字句解析器を修正／仕様を変更（wait命令を追加）
- 2017/01/09 電卓を実装（未対応：丸括弧・負の数）
- 2016/12/29 リポジトリを開設

## リンク

- きっかけ
    - [TinyHSPの提案](http://hsp.tv/play/pforum.php?mode=all&num=77515)
- 使用したライブラリ・フォント
    - [GFLW3](http://www.glfw.org)
    - [exrd / neteruhsp](https://github.com/exrd/neteruhsp)
    - [nothings / stb](https://github.com/nothings/stb)
    - [M+ FONTS](http://mplus-fonts.osdn.jp)
    - [Mgen+](http://jikasei.me/font/mgenplus/)

## ライセンス

TinyHSPはMITライセンスです。