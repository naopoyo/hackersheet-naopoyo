---
name: "Shell"
slug: "ganzwyd"
tags: ["Linux"]
---

# Shell

## 変数

```
VAR=hoge
```

```
VAR=`date`
```

 コマンドの結果を変数に

```
echo $(date)
```

コマンドの結果を変数に2


## base64

```
echo -n [value] | base64
```

[value]をbase64エンコード(改行しない)

```
base64 -D
```

デコード

