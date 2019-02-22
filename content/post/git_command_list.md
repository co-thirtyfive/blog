---
title: "Git コマンド 一覧"
date: 2019-02-23T04:13:02+09:00
draft: false
categories: ["Git"]
tags: ["GitHub","Git","コマンド"]
---

# Gitコマンド一覧

### コピペで使用する用

---

<br>

` 初期設定 `
``` commnd
git config --global user.name "XXXX"
git config --global user.email "XXXX@hogehoge.com"
```

<br>

` ローカルにリポジトリを作成する `
``` commnd
git init
git add .
git commit -m "initial commit"
```

<br>

` ローカルリポジトリをリモートリポジトリにプッシュする `
``` commnd
git remote add origin https://github.com/XXXX/XXXX.git
git push -u origin master
```

<br>

` リモートリポジトリからローカルリポジトリにクローンを作成する `
``` commnd
git clone https://github.com/XXXX/XXXX.git
```

<br>

` リモートから変更を取得する(pull) `
``` commnd
git pull
```

<br>

` リモートから変更を取得する(fetch) `
``` commnd
git fetch
git merge origin/master
```

<br>

` コミットするためのファイル登録(ファイル別) `
``` commnd
git add ファイル名
```

<br>

` コミットするためのファイル登録(全てのファイル・ディレクトリ) `
``` commnd
git add .
```

<br>

` 追加されるファイルを調べる `
``` commnd
git add -n
```

<br>

` 変更されたファイルを追加する `
``` commnd
git add -u
```

<br>

` git addしたファイルを除外する `
``` commnd
git rm --cached
```

<br>

` ファイルの変更、追加をコミットする `
``` commnd
git commit -m "コミットメッセージ"
git commit -a -m "コミットメッセージ"(-aのオプションは変更を自動検出する)
```

<br>

` ローカルの変更を確認する `
``` commnd
git status
```

<br>

` ローカルリポジトリとリモートリポジトリのファイル差分を抽出する `
``` commnd
git diff ファイル名
```

<br>

` commitの変更履歴を確認する `
``` commnd
git log
```

<br>

` コミットのハッシュ値で指定したコミットの変更点を見る `
``` commnd
git show コミットのハッシュ値
```

<br>

` リモートリポジトリにプッシュ `
``` commnd
git push origin ブランチ名
```

<br>

` ファイル登録を取り消しする `
``` commnd
git reset HEAD ファイル名
```

<br>

` コミットを取り消しする `
``` commnd
git reset --hard HEAD^ (直前のコミットを取り消して、ともにワークディレクトリの内容も書き換える)
git reset --soft HEAD^ (直前のコミットを取り消して、ワークディレクトリの内容はそのままにする)
git reset --hard HEAD~{i} (i個前のコミットを取り消して、ともにワークディレクトリの内容も書き換える)
git reset --soft HEAD~{i} (i個前のコミットを取り消して、ワークディレクトリの内容はそのままにする)
```

<br>

` コミットを打ち消しする `
``` commnd
git revert コミットのハッシュ値
```

<br>

` コミットメッセージを修正する `
``` commnd
git commit --amend "新しいコミットメッセージ"
```

<br>

` プッシュの取り消しをする `
``` commnd
git reset --hard 戻したいコミットのハッシュ値
git push -f
```

<br>

` ローカルリポジトリでブランチを作成する `
``` commnd
git branch ブランチ名
```

<br>

` ローカルリポジトリでブランチを切り替えする `
``` commnd
git checkout ブランチ名
```

<br>

` ブランチの作成と切り替えをする `
``` commnd
git branch -b ブランチ名
```

<br>

` ブランチ名の変更をする `
``` commnd
git branch -m 古いブランチ名 新しいブランチ名
```

<br>

` ブランチを削除する `
``` commnd
git branch -d ブランチ名
```

<br>

` ローカルブランチをリモートリポジトリに反映する `
``` commnd
git push -u origin ローカルのブランチ名
```

<br>

` リモートブランチをローカルに反映する `
``` commnd
git branch ブランチ名 origin/ブランチ名
```

<br>

` リモートブランチをローカルに反映して、切り替えをする `
``` commnd
git checkout -b ブランチ名 origin/ブランチ名
```

<br>

` 全てのブランチを確認する `
``` commnd
git branch -a
```

<br>

` ブランチを比較する `
``` commnd
git diff ブランチ名 ブランチ名
```

<br>

` ブランチをマージ(分岐元のブランチで実行)する `
``` commnd
git merge ブランチ名
```

<br>

` ブランチをリベース(分岐先のブランチで実行)する `
``` commnd
git rebase ブランチ名
```

<br>

` 変更点を一時退避させる `
``` commnd
git stash save
```

<br>

` 退避した作業の一覧を確認する `
``` commnd
git stash list
```

<br>

` 退避した作業を戻す `
``` commnd
git stash apply stash名
```

<br>

` 退避した作業を消す `
``` commnd
git stash drop stash名
```

<br>

` 退避した作業を全て消す `
``` commnd
git stash clear
```

<br>

` ファイル削除する `
``` commnd
git rm -f  ファイル名
```

<br>

` ファイルをリネームする `
``` commnd
git mv 元のファイル名 変えたいファイル名
```

<br>

` ファイルを最新のコミット状態に戻す `
``` commnd
git checkout HEAD ファイル名
```

<br>

` ファイルを指定したコミットまで戻す `
``` commnd
git checkout コミットのハッシュ値 ファイル名
```

<br>

` .gitignoreを無視して追加する `
``` commnd
git add -f ファイル名
```

<br>

` ディレクトリだけ登録する(.gitkeepをディレクトリに作成する) `
``` commnd
touch ディレクトリ名/.gitkeep
```

<br>

---

` コミットメッセージの修正方法(例: 3件目のコミットメッセージを修正) `
``` commnd
git rebase -i HEAD~3
```

<br>

` 上記のコマンド実行でVimが起動して、最新コミットから上で指定した過去３件のコミットが表示されます `
``` commnd
git rebase -i HEAD~3
```

<br>

` 上記のコマンド実行でVimが起動して、最新コミットから上で指定した過去３件のコミットが表示されます `
``` vim:
pick {コミットID} {コミットメッセージ} ※ 3件目
pick {コミットID} {コミットメッセージ} ※ 2件目
pick {コミットID} {コミットメッセージ} ※ 1件目(最新コミット)
```
<br>

[Vimコマンド一覧](https://co-thirtyfive.github.io/2019/02/23/vim_command_list/)

<br>

` 上記のpickをeditあるいはeに変更してファイルを保存して、下記のコマンドでコミットする `
``` commnd
git commit --amend
```

<br>

` そして下記のコマンドを実行して完了となります `
``` commnd
git rebase --continue
```

---


---


