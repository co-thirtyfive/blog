---
title: "HUGOでGitHubPagesにブログを開設する方法"
date: 2019-02-23T03:54:36+09:00
draft: false
categories: ["HUGO"]
tags: ["GitHub","HUGO"]
---

# HUGOをインストールしブログを投稿する方法(初心者向け)
このブログは、いくつかある静的サイトジェネレーターの中のHUGOで作りました。  
自分へのメモも含めて公開までの流れを書いていきたいと思います。  

前提環境  
Mac

必要なステップは以下のものです。

[GitHubアカウントの作成](https://co-thirtyfive.github.io/2019/02/23/github_account_get/)

---

事前準備
GitHubでリポジトリを作成します。
ブログ用に作るリポジトリは２つです。

1. blog  
<br>
ソース管理用リポジトリ（他の名前でも問題ないですが下記のコマンドをコピペで使えなくなります）  
<br>

2.  ` username ` .github.io  
<br>
実際のブログを公開するためのGitHub Pagesのリポジトリ  
※GitHub Pagesを使うには ` username.github.io ` というリポジトリを作らないとダメみたいです。  
また  ` username `  はGitHubのアカウントを作った時のユーザー名です。
例) hogehogeというユーザー名でアカウントを作成した場合は ` hogehoge.github.io ` となります。

<br>

---

1. HUGOのインストール  
2. HUGOで記事の作成方法  
3. GitHubへのプッシュ

## 1 HUGOのインストール

まずは[Homebrew](https://co-thirtyfive.github.io/2019/02/23/homebrew_install/)でインストール作業に入ります。  
※もし ` Homebrew ` をインストールされていない方は上記のリンク先にインストール方法を書いていますので  
インストールしてください。  
<br>

Homebrewがインストールされている前提で、画面右上にある虫眼鏡マークをクリックするとSpotlight検索が  
立ち上がります。  
そこで ` terminal ` と打つと下のトップヒットにターミナルが出てきます。  
そのターミナルをクリックするとターミナルという黒いコマンドを打つ画面が立ち上がります。  
そこで下記の四角の中のコマンドをコピーしてターミナルにcommand + vでペーストします。  

``` commnd:
brew install hugo
```     
<br>  
※今後この四角の中のコードは全てターミナル上で使いますので、ターミナルを使用することに慣れていく事をオススメします。  

<br>  


## 2ローカルにリモートリポジトリのクローンを作る

下記のコマンドをターミナルで実行するとフォームディレクトリの直下に作成できます。

<br>

``` commnd:
git clone git@github.com:<username>/blog.git
```     

## 3 HUGOで作業用ディレクトリを作成する。  

このブログでは前提としてブログ記事を書いたりデザインを変更したりするディレクトリ（場所）は  
GitHubで作ったクローンディレクトリと別にします。

クローンで作ったblogフォルダと同じ階層に_blogという名前のディレクトリを作ります。  
<br>
※ディレクトリ名は、クローンで作った  ` ディレクトリ名以外 ` でしたら何でも大丈夫ですが、  
<br>
揃えているとこの後のコマンドをそのままコピペで使うことができます。  
<br>
下記のコマンドでクローンを作ったblogフォルダと同じフォームディレクトリの直下階層に新たに ` _blog ` というフォルダができます。  
<br>

``` commnd:
hugo new site _blog
```   
そしてターミナル操作で下記のコマンドを打ちます。  
<br>
そうする事で、_blogフォルダ内に移動できます。

``` commnd:
cd _blog
```   
<br>


hugoにテーマをインストールします。  

<br>

※テーマはhugoで作るblogのデザイン( 見た目 )の部分になります。  

<br>  

まずは_blogフォルダのthemesフォルダに入るため下記のコマンドを打ちます。  

<br>

※hugoのテーマはこのフォルダに配置します。  

<br>

``` commnd:
cd themes
```   

インストール方法はGitHubのリポジトリをクローンした時と同じく、下記のコマンドでお好きなテーマを  

<br>

themesフォルダにインストールできます。  

<br>

``` commnd:
git clone git@github.com:appernetic/hugo-bootstrap-premium.git
```   
<br>  

※ ` git@github.com:appernetic/hugo-bootstrap-premium.git ` の部分はお好きなテーマをお探し下さい。  

<br>

そしてSpotlight検索で_blogと打つと_blogフォルダ内に入れますので、 ` config.toml ` ファイルをクリックすると、  

<br>

インストールしている場合はXcodeが立ち上がると思います。もしインストールされていなかったら  

<br>

App Storeでインストールできますのでインストールすることをオススメします。  

<br>

Xcodeでファイルの中を見ると、 ` theme= "" ` という記述がありますのでインストールしたテーマ名を  

<br>

下の例のように入れます。  

<br>

` theme= "hugo-bootstrap-premium" `  

<br>  

これから記事を書くために一旦themesフォルダから出るため下記のコマンドを打ちます。  

<br>

``` commnd:
cd ..
```   

<br>
そして新しい記事を生成するためには下記のコマンドを打ちます。  
<br>
そうすると_blogフォルダ内にあるcontentフォルダにpostというフォルダができ、  
<br>
その中に、下記コマンドで作成したファイルが出来ています。

``` commnd:
hugo new post/記事名.md
```   
<br>
上記のファイルはマークダウン記法で書くことが出来、ここに書いたものがこの後に行うコマンドで、  
<br>
処理されて最終的にブラウザで見ることが出来るブログになります。
<br>
それから下記のコマンドでローカルサーバー立ち上げ都度都度で記事のブラウザ表示状態を確認できます。  
<br>

``` commnd:
hugo server -D -t hugo-bootstrap-premium 
``` 
<br>
上記のコマンドを打つと最後の方に

``` commnd:
Web Server is available at http://localhost:51043/ (bind address 127.0.0.1)
Press Ctrl+C to stop
``` 
<br>と出ていますので ` http://localhost:51043/ ` の部分をコピーしてブラウザのアドレスバーに貼り付けて  
叩くとブラウザ表示状態を確認できます。またファイルを保存するたびにローカルサーバが更新され直ぐに  
<br>
変更部分を確認できます。  
<br>
※localhostより後の５桁数字は立ち上げるたびに新たにローカルサーバーを立ち上げるたびに変わるのでその都度コピーしてください。またcontrol + c でローカルサーバーを停止することができます。
<br>
そうして出来た記事は下記のコマンドを叩くことでpublicディレクトリが作成され、そこに公開ファイルが出力されます。
<br>


``` commnd:
hugo -t hugo-bootstrap-premium
``` 

<br>
ここまでで、準備はできたので次にGitクローンのディレクトリであるblogに_blogの状態をコピーする作業に入ります。
<br>
なぜするのかは実際にブログを更新しているフォルダとGitHubを繋げているフォルダが違うからです。  
<br>
なので現在いる_blogディレクトリから一つ上のディレクトリに下記のコマンドで移動します。  
<br>  

``` commnd:
cd ..
```   

<br>
そうすると今までいたのはターミナル上では_blogフォルダでしたが一つ上のディレクトリに移動しましたので、  
<br>
今いる場所は_blogとblogフォルダがいるディレクトリになります。  
<br>


<br>
コピーするため下記のコマンドを打ちます。  
<br>

``` commnd:
cp -p -f -R _blog/* blog/
```   

<br>
そうすると_blogフォルダの中身がGitHubのクローンで作ったblogフォルダにコピーされます。  
<br>

<br>
そして実際のGitHubのリポジトリのblogとco-thirtyfive.github.io.gitにプッシュする作業に入るため  

<br>
blogディレクトリに移動するために下記のコマンドを打ちます。  
<br>

``` commnd:
cd blog
```   

<br>
この時下記の流れを一度だけ行います。  
<br>

---

## リモートリポジトリのサブモジュール化  

<br>  

まずは下記のコマンドでblogフォルダ内のpublicフォルダを削除します。  
<br>


``` commnd:
rm -rf public

```  

<br>
そしてpublicフォルダを公開先リポジトリとしてサブモジュール化するために下記のコマンドを実行します。  
<br>

``` commnd:
git submodule add -b master git@github.com:<userneme>/<userneme>.github.io.git public

```  
<br>  

※   ` username  `  の所はご自身で作ったGitHubアカウント名です。余談ですが、アカウント名とは違う命名で  

<br>

` <not userneme>.github.io.git ` の場合上手くGitHub Pagesが機能しません。  

<br>  


<br>


---  

<br>  
ここまでは初めて記事をGitHub上に上げるときに、一度だけです。  
<br>  
※二回目以降は飛ばします。





<br>
ここから下は連続でコマンドを打ちます。内容は自分のローカルリポジトリをリモートレポジトリにpushするためです。  

<br>


``` commnd:
echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"
cd public
git add .

msg="rebuilding site `date`"
if [ $# -eq 1 ]
then msg="$1"
fi
git commit -m "$msg"

git push origin master
cd ..

git add .
git commit -m "$msg"
git push

```  

<br>  

ここまでやるとGithubの ` <userneme>.github.io ` のリポジトリをログイン後のトップ画面左から選択してください。  

<br>

そうするとリポジトリ名のすぐ下にあるタブにSettingsがありますのでクリックします。  

<br>

そして下の方にスクロールしていくとGitHub Pagesという大項目がありその中に、  

<br>  

` Your site is published at https://co-thirtyfive.github.io/ `  というチェックマークがついた記述が  

<br>  

あると思いますので ` https://co-thirtyfive.github.io/ ` がご自身のGitHub Pagesのアドレスになり、  

<br>  

アクセスすると先ほどプッシュした内容が観れると思います。


