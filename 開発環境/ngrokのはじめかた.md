---
name: "ngrokのはじめかた"
slug: "risbfjc"
tags: ["開発環境"]
---

# ngrokのはじめかた

## ngrokとは

ローカル環境を外部公開できるサービス。

## 公式

[ngrok - secure introspectable tunnels to localhost](https://ngrok.com/)


## はじめに

公式サイトでアカウント作成する。

## インストール

```
brew install --cask ngrok
```

## Authtokenを設定

1. [ダッシュボードのYour Authtoken](https://dashboard.ngrok.com/get-started/your-authtoken)でAuthtokenを取得
2. 次のコマンドを実行して設定

```
ngrok authtoken [Authtoken]
```

💡 この設定は `~/.ngrok2/ngrok.yml` に保存されている

## 使い方

```
ngrok http 80
```
