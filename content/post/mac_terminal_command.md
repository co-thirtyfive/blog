---
title: "Macターミナルコマンド一覧"
date: 2019-02-23T04:14:57+09:00
draft: false
categories: ["command"]
tags: ["Apple","mac","OSX","ターミナル"]
---

# Macのターミナルコマンド
用語
ディレクトリ                       (フォルダ)
カレントディレクトリ         (現在いるディレクトリ)
ホームディレクトリ             (ターミナルを起動時のデフォルトのディレクトリ)

※下記でよく出てくる ` hoge ` とはプログラム業界でよく使われる仮名です。

# コマンド一覧

---
## ls コマンド
カレントディレクトにあるファイルを表示。（listの略）
<br>

``` commnd:
ls      (カレントディレクトリにあるファイルやディレクトリを表示する)  
ls -l   (ファイルやディレクトリの詳細も同時に表示する)  
ls -a   (隠しファイルも含めファイルやディレクトリを全て表示する)  
ls −la  (隠しファイルを含む全てのファイルやディレクトリの詳細を表示する)  
```   
<br>
隠しファイルとは通常では表示されないようになっているファイルやディレクトリ。
<br>
重要なファイルは、通常では表示されません。
<br>
隠しファイルは名前の前に「.（ドット）」がついているファイルやディレクトリです。
<br>

---
## cd コマンド

カレントディレクトリにあるファイルに移動。（change directoryの略）
<br>

``` commnd:
cd hoge  (hogeディレクトリに移動)
cd ~/    (ホームディレクトリに移動)
cd ..    (一つ上の階層のディレクトリに移動)
```   
<br>

---
## pwd コマンド

カレントディレクトリのパスを表示。（print working directoryの略）
<br>

``` commnd:
pwd  (カレントディレクトリのパスを表示する)
```   
<br>

---
## touch コマンド

中身が空のファイルを作る。
<br>

``` commnd:
touch hoge.html  (hoge.htmlという中身が空のファイルを作る)
※ここでいう空のファイルとは何も記述されていないファイルのこと
```   
<br>

---
## mkdir コマンド

新しい空のディレクトリを作る。（make directoryの略）
<br>

``` commnd:
mkdir hoge  (hogeというディレクトリを作る)
```   
<br>

---
## mv コマンド
ファイルを移動または、ファイル名を変更。（moveの略）
<br>

``` commnd:
mv hoge.html tmp/         (hoge.htmlというファイルを相対パスでtmp/に移動する)
mv hoge.html hoge2.html   (hoge.htmlというファイルをhoge2.htmlに名前変更する)
```   
<br>

---
## cp コマンド
ファイルをコピー。（copyの略）
<br>

``` commnd:
cp hoge.html tmp/         (hoge.htmlを相対パスでtmp/というディレクトリの中にコピー)
cp hoge.html hoge2.html   (hoge.htmlをhoge2.htmlという名前でコピー)
cp −r dir /tmp/           (dirというディレクトリとその中身を絶対パスで/tmp/にコピー)
```   
<br>

---
## rm コマンド
ファイルを削除する。（removeの略）
<br>

``` commnd:
rm hoge.html   (hoge.htmlを削除)
rm -r hoge     (hogeというディレクトリとその中身を削除)
rm -f hoge     (hogeファイルを警告なしで削除)
rm -rf hoge    (hogeディレクトリとその中身を警告なしで削除)
```   
<br>

#### ※取り返しがつかない操作のため、ターミナルコマンドに慣れていない方は使わない方がいいです。

---
## openコマンド
ターミナルからFinderでファイルを開く。
<br>

``` commnd:
open .   (現在のターミナルのディレクトリFinderで開く)
open ~/  (ホームディレトリをFinderで開く)
```   
<br>

---
## source コマンド
ファイルの設定を読み込み有効にする。
<br>

``` commnd:
source ~/.bash_profile  (ホームディレクトリにある.bash_profileに書き込んだ設定を読み込み有効にする)
source .bash_profile    (カレントディレクトリにある.bash_profile設定を読み込み有効にする)
```   
<br>

---
## history コマンド
コマンド履歴を表示する。
<br>

``` commnd:
history       (これまで実行してきたコマンドの履歴を表示)
history -c    (これまで実行してきたコマンドの履歴を消去)
```   
<br>

---
