---
name: "bundle install mysql2が失敗するとき"
slug: "mgqjzzu"
tags: ["Ruby"]
---

```
bundle config --local build.mysql2 "--with-ldflags=-L/usr/local/opt/openssl/lib"
```

