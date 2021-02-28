---
name: "Ruby Solargraph"
slug: "bxiakls"
tags: ["開発環境", "Ruby"]
---

# Ruby Solargraph

VSCodeの拡張機能「Ruby Solargraph」を使う。コード補完や定義元ジャンプなどができるようになる。

## gemインストール

```
gem install solargraph
```

## 設定ファイル作成

プロジェクトルートで以下を実行すると.solargraph.ymlが作成される。

```
solargraph config
```

## Rails対応

Rails用に.solargraph.ymlを以下のように修正する。（詳しくはリンクを参照）

```yaml
---
include:
- "**/*.rb"
exclude:
- spec/**/*
- test/**/*
- vendor/**/*
- ".bundle/**/*"
require:
- actioncable
- actionmailer
- actionpack
- actionview
- activejob
- activemodel
- activerecord
- activestorage
- activesupport
domains: []
reporters:
- rubocop
- require_not_found
formatter:
  rubocop:
    cops: safe
    except: []
    only: []
    extra_args: []
require_paths: []
plugins: []
max_files: 5000
```

## リンク

- [VSCodeでRuby Solargraph拡張機能を使ってみた話 - Qiita](https://qiita.com/hideki0145/items/d6a18095f95d57eebe96)