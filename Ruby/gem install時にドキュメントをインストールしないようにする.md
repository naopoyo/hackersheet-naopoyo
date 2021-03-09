---
name: "gem install時にドキュメントをインストールしないようにする"
slug: "okzrzyf"
tags: ["Ruby"]
---

# gem install時にドキュメントをインストールしないようにする

## ~/.gemrcを修正

```
install: --no-document
update: --no-document
```

## 補足

`–no-ri` `–no-rdoc` はRubyGems 3.0.1から廃止