---
name: "YAML記法"
slug: "kpeunnj"
---

# YAML記法

## 配列

```yaml
list:
  - item1
    - item1.2
  - item2
```

```yaml
list:
  - name: taro
    email: aaa@example.com
  - name: jiro
    email: bbb@example.com
```


## ハッシュ

```yaml
key: value
```

```yaml
key:
  a: value
  b: value2
```


## 複数行の文字列

```yaml
## 各行の改行を維持
text: |
  aaaaa
  bbbbb
  ccccc
```

```yaml
# 空白行を改行
text: >
  aaaaa
  bbbbb

  ccccc
```


## データの区切り

```
---
```

```yaml
---
name: taro
email: aaa@example.com
---
name: jiro
email: bbb@example.com
```

