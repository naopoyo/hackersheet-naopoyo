---
name: "CommonJS or AMD dependencies can cause optimization bailouts."
slug: "nlybkxh"
tags: ["Angular"]
---

# CommonJS or AMD dependencies can cause optimization bailouts.

```
Warning: /path/to depends on 'XXX'. CommonJS or AMD dependencies can cause optimization bailouts.
For more info see: https://angular.io/guide/build#configuring-commonjs-dependencies
```

Angularでビルド時に上記のようなWarningが出る場合はangular.jsonを次のように修正すr。

```json
{
  "build": {
    "options": {
      "allowedCommonJsDependencies": [
        "XXX"
      ]
    }
  }
}
```