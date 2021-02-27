---
name: "VSCode の ruby カスタマイズ"
slug: "euehqul"
---

# VSCodeのRubyカスタマイズ

Visual Studio CodeをRuby, Rails用にカスタマイズ

## Ruby Solargraph

コード補完と定義元ジャンプ

```
gem install solargraph
```

[VSCodeでRuby Solargraph拡張機能を使ってみた話 - Qiita](https://qiita.com/hideki0145/items/d6a18095f95d57eebe96)


## ruby-rubocop

コードフォーマット

```
gem install rubocop
```

```json
{
  "editor.defaultFormatter": "misogi.ruby-rubocop"
}
```
