---
name: "Rails APIモードでプロジェクト作成"
slug: "rudkutn"
tags: ["Ruby"]
---

# Rails APIモードでプロジェクト作成

## プロジェクト作成

```
bundle init
```

Gemfileが作られる

## Gemfileを修正

```ruby
gem 'rails'
```

Gemfileの上記のコメントをはずす

## bundle install

```
bundle install --path vendor/bundle --jobs=4
```

bundle install mysql2 のために以下を実行

```
bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib"
```

## rails new

```
bundle exec rails new . -B --api -d mysql --skip-test
```


### rails new のオプション

| オプション | 説明 |
| --- | --- |
| --skip-test | minitestのスキップ |
| -B | bundle install のスキップ |
| -d mysql | mysql を使用する |

## .gitignore修正

.gitignore に以下を追記する。

```
vendor/bundle
```

## DBセットアップ

```
bundle exec rails db:setup
```


