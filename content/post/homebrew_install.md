---
title: "Homebrewのインストールから操作"
date: 2019-02-23T04:14:24+09:00
draft: false
categories: ["Homebrew"]
tags: ["Homebrew","Mac"]
---

# Homebrewのインストール( 初心者向け )

<br>



<br>

まずはインストールに必要なツールをターミナルでインストールします。  

<br>

※将来的にApple製品のアプリを作る場合はXcodeをインストールすることをオススメします。  

<br>

下記のコマンドをターミナルにそのままコピペしてエンターキーを押してください。

<br>

```commnd:
xcode-select --install
```  
<br>

次に[Homebrew](https://brew.sh/index_ja)にアクセスしてインストールの下に書かれているスクリプトを  

<br>

ターミナルに貼り付けて実行してください。

注)下記のスクリプトは2019年2月20日現在のものなので、念のためサイトに行き最新のスクリプトをコピーしてください。  

<br>

```commnd:
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```  
