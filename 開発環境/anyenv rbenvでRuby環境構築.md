---
name: "anyenvとrbenvでRuby環境構築"
slug: "apvlalc"
tags: ["開発環境"]
---

# anyenvとrbenvでRuby環境構築

## rbenvをインストール

```
anyenv install rbenv
```

## シェルを再起動

```
exec $SHELL -l
```

## インストール可能なバージョンを確認

```
rbenv install -l
```

## 指定したバージョンをインストール

```
rbenv install [VERSION]
```

## グローバル環境に設定

```
rbenv global [VERSION]
```

## rehash

```
rbenv rehash
```

