---
name: "Rails バリデーション"
slug: "rwoyudi"
tags: ["Ruby"]
---

```ruby
validates :role, inclusion: { in: %w(admin member guest) }
```

admin member guest のいずれかを含む

```ruby
validates :username, presence: true
```

空でない

```ruby
validates :username, uniqueness: true
```

ユニークな

```ruby
validates :username, length: { maximum: 16 }
```

16文字まで

```ruby
validates :username, format: { with: /\A[a-zA-Z0-9]+\z/i }
```

半角英数

