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

Angularのビルド時に上記のようなWarningが出る場合はangular.jsonの**allowedCommonJsDependencies**を次のように修正する。

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

## 解説

- CommonJS形式のモジュールを読み込むと表示される警告