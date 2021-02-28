---
name: "Railsコマンド"
slug: "yyaggdw"
tags: ["Ruby"]
---

# Railsコマンド

## サーバー起動

```
bundle exec rails s -b 0.0.0.0
```

## モデル作成

```
bundle exec rails g model [MODEL_NAME]
```

## タスク一覧

```
bundle exec rails -T
```

## DBマイグレーション

```
bundle exec rails db:migrate
```

## マイグレーションロールバック

```
bundle exec rails db:rollback
```

## マイグレーションリセット

```
rails db:migrate:reset
```

## 新規プロジェクト作成

```
rails new [APP_NAME] -d mysql
```

## Railsバージョンアップ

```
rails app:update
```


