---
name: "Ruby 基本"
slug: "nsrbuyk"
---

# Ruby基本

## 繰り返し

```ruby
objects.each do |object|
  puts object
end
```

```ruby
5.times do
  puts '5回繰り返す'
end
```


## 文字列操作

```ruby
str.gsub(/\r\n|\r|\n|\t/, '')
```

改行とタブを削除


## 配列操作

```ruby
array.uniq
```

重複を削除

```ruby
array.slice(0..9)
```

先頭から10件削除。削除したものを返す

```ruby
array.flatten
```

平坦化

```ruby
array.include?(value)
```

valueを含む


## ファイル

```ruby
File.exist?('/hoge/fuga/file')
```

ファイルの存在確認


