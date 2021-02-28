---
name: "VSCodeのRubyカスタマイズ"
slug: "euehqul"
tags: ["開発環境"]
---

# VSCodeのRubyカスタマイズ

Visual Studio CodeをRuby, Rails用にカスタマイズ

## Ruby Solargraph

コード補完と定義元ジャンプ

### インストール

Solargraphをインストール

```
gem install solargraph
```

### 関連記事

- [VSCodeでRuby Solargraph拡張機能を使ってみた話 - Qiita](https://qiita.com/hideki0145/items/d6a18095f95d57eebe96)


## ruby-rubocop

コードフォーマット

### インストール

rubocopをインストール

```
gem install rubocop
```

### 設定

```json
{
  "editor.defaultFormatter": "misogi.ruby-rubocop"
}
```
