---
title: "GitHubなどの接続で使用するSSHの作成方法"
date: 2019-02-23T04:15:18+09:00
draft: false
categories: ["SSH"]
tags: ["SSH","Git"]
---

# SSHの作成方法

## GitHubなどに使う秘密鍵・公開鍵を作成する方法をメモしておこうと思います。

下記のコマンドでSSHの指定フォルダを作成します。

<br>


``` commnd:
install -m 0700 -d ~/.ssh
```     

上のコマンドで作成したSSHフォルダに下記のコマンドで移動する

<br>

``` commnd:
cd ~/.ssh
```   

<br>

``` commnd:
ssh-keygen -t rsa -b 4096 -C "XXXX@example.com" -f ~/.ssh/id_rsa
Generating public/private rsa key pair.
Enter passphrase (empty for no passphrase):  <-- パスフレーズを入力します（任意）
Enter same passphrase again:  <-- もう一度、パスフレーズを入力します（任意）
Your identification has been saved in id_rsa.
Your public key has been saved in id_rsa.pub.
```   

上記のコマンドで作成されたSSHを下記の確認する。

<br>

``` commnd:
ls
```   

<br>

id_rsa            (秘密鍵)クライアントPCに配置しておくもの

<br>

id_rsa.pub     (公開鍵)接続対象サーバに登録するもの

<br>

公開鍵をコピーする

<br>

``` commnd:
pbcopy < ~/.ssh/id_rsa.pub
```   
