---
name: "Rails モデル関連のよく使うやつ"
slug: "pcqoyfy"
---

#  Rails モデル関連のよく使うやつ

## 他のモデルと結合して検索

```ruby
User.joins(:posts)
```

INNER JOIN

```ruby
User.left_joins(:posts)
```

LEFT OUTER JOIN


## update_atだけを更新

```ruby
model.touch
```


## has_manyなモデル作成

```ruby
user.posts.create
```

保存する

```ruby
user.posts.build
```

保存しない


## has_manyなモデルの削除

```ruby
user.posts.where(title: 'hoge').delete_all
```


## has_many through

```ruby
has_many :post_tags, dependent: :destroy
has_many :tags, through: :post_tags
```


## 指定したカラムを配列で取得

```ruby
user.posts.pluck(:title)
```

titleを配列で取得


## 大量のレコードに順番に処理する

```ruby
User.find_each do |user|
  p user
end
```

