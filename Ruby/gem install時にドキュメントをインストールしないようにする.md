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
