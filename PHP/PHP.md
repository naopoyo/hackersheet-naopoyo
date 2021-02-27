---
name: "PHP"
slug: "ebxdsmu"
tags: ["PHP"]
---

# PHP

## ヒアドキュメント

```php
$var = <<< EOM
hoge
fuga
EOM;
```


## 配列

```php
array_shift ( array &$array ) : mixed
```

配列の先頭から要素を一つ取り出す

```php
array_pop ( array &$array ) : mixed
```

配列の末尾から要素を取り除く

```php
in_array ( mixed $needle , array $haystack [, bool $strict = FALSE ] ) : bool
```

配列に $needle が含まれていれば true


## 配列⇔文字列

```php
implode ( string $glue , array $pieces ) : string
```

配列→文字列

```php
implode ( array $pieces ) : string
```

配列→文字列

```php
explode ( string $delimiter , string $string [, int $limit = PHP_INT_MAX ] ) : array
```

文字列→配列

