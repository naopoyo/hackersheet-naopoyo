---
name: "Angularでfavicon.icoをassetsディレクトリで管理する"
slug: "pjzlguv"
tags: ["Angluar"]
---

# Angularでfavicon.icoをassetsディレクトリで管理する

favicon.ico、apple-touch-icon.pngなどをルートで公開したい場合（ https://example.com/favicon.ico のように）、src直下に置いていくと邪魔なのでassetsディレクトリ以下で管理する方法。

----------

src/assets/root/を作成し、ここにfavicon.icoを置く。

次に、angular.jsonのassetsセクションを以下のように。

```json
{
  "build": {
    "options": {
      "assets": [
        {
          "glob": "**/*",
          "input": "src/assets/",
          "output": "/assets/",
          "ignore": [
            "root"
          ]
        },
        {
          "glob": "**/*",
          "input": "src/assets/root/",
          "output": "/"
        }
      ]
    }
  }
}
```

これでビルド後はfavicon.icoがルートに置かれるので https://example.com/favicon.ico のようにアクセス可能になる。
