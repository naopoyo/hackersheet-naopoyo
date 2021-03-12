---
name: "Gitユーザー設定"
slug: "lupzxqk"
tags: ["Git"]
---

# Gitユーザー設定

全体の設定は `--global`、リポジトリ専用の設定は `--local`。

## ユーザー名

### 設定

```
git config --global user.name "[USERNAME]"
```

```
git config --local user.name "[USERNAME]"
```

### 確認

```
git config user.name
```

-----

## メールアドレス

### 設定

```
git config --global user.email "[EMAIL]"
```

```
git config --local user.email "[EMAIL]"
```

### 確認

```
git config user.email
```

-----

## 全体の設定を確認する

```
git config --list --global
```

```
cat ~/.gitconfig
```
