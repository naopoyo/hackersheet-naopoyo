---
name: "anyenvインストール"
slug: "yajhaey"
tags: ["開発環境"]
---

# anyenvインストール

## Homebrewでインストール

```
brew install anyenv
```

## 初期化

```
anyenv install --init
```

~/.configが作成される。

## .zshrc修正

以下を~/.zshrcに追記。

```
eval "$(anyenv init -)"
```

## シェルを再起動

```
exec $SHELL -l
```

## インストール可能なenvを確認

```
anyenv install -l
```



