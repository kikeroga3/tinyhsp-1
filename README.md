# TinyHSP

TinyHSPは**最軽量のHSPを作成する**ことを目標にしたプロジェクトです。マルチプラットフォーム（Windows・Linux・macOS）で動作するインタプリタを作成することを目指しています。

## 更新履歴

- 2017/01/13 字句解析器を修正（長い関数を分割）
- 2017/01/12 ファイル読み込み用のユーティリティを追加
- 2017/01/11 ディレクトリ構成およびMakefileの変更
- 2017/01/10 字句解析器を修正／仕様を変更（wait命令を追加）
- 2017/01/09 電卓を実装（未対応：丸括弧・負の数）
- 2016/11/29 リポジトリを開設

## TinyHSPの仕様（暫定案）

Palo Alto Tiny BASICを参考にした仕様になっています。

- プリプロセッサ
    - なし
- 命令
    - pset
    - color
    - redraw（引数はなし。redraw 1に相当）
    - title
    - wait
- 関数
    - rnd（randomize使用時に相当）
- 構文
    - 繰り返し: repeat...loop（カウンタ変数cntはなし）
    - ジャンプ: \*ラベル・goto・gosub・return
    - 条件分岐: if 比較式 : 処理（else文はなし）
- 変数
    - 変数はa-zの26個のみ（数値型）
    - 配列は@のみ（一次元配列、数値型）
- コメント
    - ;（行頭のみ）
- システム変数
    - システム変数key（stick key,1+2+4+8...相当のキー情報が代入される）
- 演算子
    - 比較演算子: ==, !=, >, >=, <, <=
    - 算術演算子: +, -, *, /
- その他
    - ウィンドウサイズは640x480で固定

## 実装の手順（目安）

1. 字句解析器を実装する
2. 構文解析器を実装する
    1. 再帰下降パーサを手書きで作る
    2. 難しいようなら文法を多少変更する
    3. 手書きが難しいようならyaccを使用する方法に切り替る
    4. それでも難しいならコンパイラの勉強をし直す
3. 構文木生成コードを実装する
4. 構文木実行コードを実装する
5. メモリ管理コードを実装する
6. グラフィック関連の処理を実装する

## 開発者向けのガイド

このプロジェクトは__楽しんで開発しよう__という基本方針で動いています。コミッター向けのルールは次のようなものです。

1. 開発すること自体を楽しむ
2. コミットメッセージは自由に書く
3. C言語で実装する
4. GUIはOpenGL+GLFWで実装する

１から作ることの楽しさを味わうのはもちろん、アルゴリズムに悩んだり難しい処理を実装したり、そういったことを含めて開発を楽しめればと思っています。

### 開発に貢献する方法

TinyHSPの開発に興味のある方は、以下のどの方法でも開発に貢献できます。

1. プルリクエストを送る
    1. リポジトリをフォークする
    2. ローカル環境でコードを変更する
    3. プルリクエストを送る
2. 独自に開発して知らせる
    1. 好きな言語でTinyHSPを実装する
    2. ソースコードを公開し、なんらかの方法で知らせる
3. 質問や不具合・提案などのissuesを立てる
4. ソースコードをダウンロードし、動作テストをする

### リポジトリの管理方法

このリポジトリはおおらかに管理しています。

- __コーディングスタイルの指定はありません__: 基本的にMozillaのコーディングスタイルを念頭に置いて書いてありますが、それに合わせる必要はありません。自由に書いていただいて大丈夫です。
- __自由に新しいディレクトリを作成してください__: コア部分とGUIはC言語で記述しますが、それ以外の部分や新しいディレクトリ内の使用言語は指定しません。自分の使いやすい言語で実装してください。
- __コア部分の書き換えも受け付けています__: その際、多少コードが動かなくなるとか、コンパイルが通らなくなるといったミスは笑って見過ごす、くらいの気軽さで進めていければ、と思っています。
- __管理人の側がミスすることがあるかもしれません__: Github及びGitの扱いにそれほど慣れていないために、ミスすることがあるかもしれません。あらかじめご了承ください。

## どんなことでもissuesにどうぞ

Githubでは掲示板のスレッドのような機能「イシュー」を使うことができます。質問や提案・不具合の報告などがありましたら、ご自由に[Issuesのページ](https://github.com/dolphilia/tinyhsp/issues)からイシューを立てていただければと思います。

※ 注意すべき点として、イシューは削除することができません。イシューを立てる際には内容をよく吟味するようお勧めします。

## リンク

- きっかけ: [TinyHSPの提案](http://hsp.tv/play/pforum.php?mode=all&num=77515)

## ライセンス

TinyHSPはMITライセンスです。
