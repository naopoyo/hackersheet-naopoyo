---
name: "Rails DBマイグレーション"
slug: "gctviwd"
tags: ["Ruby"]
---


## 基本

```ruby
drop_table :table
```

テーブル削除

```ruby
rename_table :from :to
```

テーブル名の変更


## カラム操作

```ruby
add_column :users, :email, :string, after: :username
```

カラム追加。ユーザー名のうしろにメールアドレスを追加

```ruby
rename_column :table, :from, :to
```

カラム名を変更

```ruby
change_column_default :table, :column, 'Default Value'
```

カラムのデフォルトを変更


## belongs_to

```ruby
t.belongs_to :user, null: false, foreign_key: true
```

```ruby
t.belongs_to :owner, null: false, foreign_key: { to_table: :users }
```

[Ruby](https://hackersheet.com/lbbxcpx/sheets/putgewh)

