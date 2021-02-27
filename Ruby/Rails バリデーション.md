---
name: "Rails バリデーション"
slug: "rwoyudi"
tags: ["Ruby"]
---

# Rails バリデーション

## admin member guest のいずれかを含む

```ruby
validates :role, inclusion: { in: %w(admin member guest) }
```

## 空でない

```ruby
validates :username, presence: true
```

## ユニークな

```ruby
validates :username, uniqueness: true
```

## 16文字まで

```ruby
validates :username, length: { maximum: 16 }
```

## 半角英数

```ruby
validates :username, format: { with: /\A[a-zA-Z0-9]+\z/i }
```
