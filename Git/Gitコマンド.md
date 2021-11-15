---
name: "Gitコマンド"
slug: "tiurlhn"
tags: ["Git"]
---

# Gitコマンド

## ユーザー設定

```
git config --global user.name "[USERNAME]"
```

ユーザー名設定

```
git config --global user.email "[EMAIL]"
```

メールアドレス設定

```
git config --list --global
```

ユーザー情報確認


## ローカルリポジトリ作成

```
git init
```

```
git add .
```

```
git commit -m "initial commit"
```


## リモートリポジトリ操作

```
git init --bare --share
```

リモートリポジトリ作成

```
git remote add origin [REPOSITORY]
```

リモートリポジトリ追加

```
git remote -v
```

リモートリポジトリ一覧

```
git remote rm origin
```

リモートリポジトリ削除

```
git remote set-head origin master
```

HEAD設定

```
git fetch --prune
```

## リモートリポジトリから変更を取り込む

```
git fetch
```

リモートから変更を取り込む

```
git merge origin/master
```

マージ

```
git pull
```

git fetch + git merge origin/master


## リポジトリをコピーする

```
git clone [REPOSITORY]
```


## 現在の状況を確認する

```
git status
```

現在の状況を確認する


## 差分確認

```
git diff
```

差分確認


## コミット履歴の確認

```
git log
```

```
git log --pretty=full
```

コミッターも表示


## 履歴の Author と Commiter を変更する

```
git filter-branch -f --env-filter "GIT_AUTHOR_NAME='taro'; GIT_AUTHOR_EMAIL='taro@example.com'; GIT_COMMITTER_NAME='taro'; GIT_COMMITTER_EMAIL='taro@example.com';" HEAD
```


## マージ

```
git checkout master
```

マスターブランチに移動してから

```
git merge [BRANCH_NAME]
```

マージする


## ブランチ関連

```
git branch [BRANCH_NAME]
```

ブランチ作成

```
git branch
```

ブランチ確認

```
git branch --remote
```

リモートブランチの確認

```
git checkout [BRANCH_NAME]
```

ブランチ変更

```
git checkout -b [BRANCH_NAME]
```

ブランチ作成してから変更

```
git rebase master
```

ブランチにマスターの変更を取り込む

```
git branch -d [BRANCH_NAME]
```

ローカルブランチの削除

```
git push origin :branch
```

リモートブランチの削除


## ファイル操作

```
git mv [from] [to]
```

ファイルの移動


## コミットのハッシュ値を取得

```
git rev-parse HEAD
```

```
git rev-parse --short HEAD
```

短縮形


## switch / restore

```
git switch
```

ブランチ切り替え

```
git restore .
```

現在のディレクトリ内のすべてのファイルを復元


## GC

```
git gc --aggressive --prune=all
```

