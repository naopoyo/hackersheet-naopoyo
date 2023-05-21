---
name: "Gitコマンドチートシート"
slug: "tiurlhn"
emoji: "💻"
tags: ["Git"]
---

# Gitコマンドチートシート

## ユーザー設定

### ユーザー名設定

```
git config --global user.name "[USERNAME]"
```

### メールアドレス設定

```
git config --global user.email "[EMAIL]"
```

### ユーザー情報確認

```
git config --list --global
```


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

### リモートリポジトリ作成

```
git init --bare --share
```

### リモートリポジトリ追加

```
git remote add origin [REPOSITORY]
```

### リモートリポジトリ一覧

```
git remote -v
```

### リモートリポジトリ削除

```
git remote rm origin
```

### HEAD設定

```
git remote set-head origin main
```

### 不要なリモートブランチを削除

```
git fetch -p
```


## リモートリポジトリから変更を取り込む

### リモートから変更を取り込む

```
git fetch
```

### マージ

```
git merge origin/main
```

### git fetch + git merge origin/main

```
git pull
```



## リポジトリをコピーする

```
git clone [REPOSITORY]
```


## 現在の状況を確認する

```
git status
```


## 差分確認

```
git diff
```


## コミット履歴の確認

```
git log
```

### コミッターも表示

```
git log --pretty=full
```


## 履歴の Author と Commiter を変更する

```
git filter-branch -f --env-filter "GIT_AUTHOR_NAME='taro'; GIT_AUTHOR_EMAIL='taro@example.com'; GIT_COMMITTER_NAME='taro'; GIT_COMMITTER_EMAIL='taro@example.com';" HEAD
```


## マージ

`checkout` で移動してから `merge`

```
git checkout main
```

```
git merge [BRANCH_NAME]
```


## ブランチ関連

### ブランチ作成

```
git branch [BRANCH_NAME]
```

### ブランチ確認

```
git branch
```

### リモートブランチの確認

```
git branch --remote
```

### ブランチ変更

```
git checkout [BRANCH_NAME]
```

### ブランチ作成してから変更

```
git checkout -b [BRANCH_NAME]
```

### ブランチにマスターの変更を取り込む

```
git rebase main
```

### ローカルブランチの削除

```
git branch -d [BRANCH_NAME]
```

### リモートブランチの削除

```
git push origin :branch
```



## ファイル操作

### ファイルの移動

```
git mv [from] [to]
```


## コミットのハッシュ値を取得

```
git rev-parse HEAD
```

短縮形:

```
git rev-parse --short HEAD
```


## switch / restore

### ブランチ切り替え

```
git switch
```

### 現在のディレクトリ内のすべてのファイルを復元

```
git restore .
```


## GC

```
git gc --aggressive --prune=all
```

