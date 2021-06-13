---
name: "bundle install mysql2が失敗するとき"
slug: "mgqjzzu"
tags: ["Ruby"]
---

# bundle install mysql2が失敗するときのコマンド

## 今までの方法

```
bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib"
```

## M1 Macの場合

```
bundle config --local build.mysql2 --with-ldflags=-L/opt/homebrew/Cellar/zstd/1.5.0/lib --with-opt-dir=/opt/homebrew/opt/openssl@1.1
```