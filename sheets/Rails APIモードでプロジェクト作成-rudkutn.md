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

```
vi Gemfile
```

```ruby
gem 'rails'
```

Gemfileのコメントをはずす

## bundle install

```
bundle install --path vendor/bundle --jobs=4
```

```
bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib"
```

bundle install mysql2 のために

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


