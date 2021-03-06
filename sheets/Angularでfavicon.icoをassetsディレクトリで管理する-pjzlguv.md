---
name: "Angularでfavicon.icoをassetsディレクトリで管理する"
slug: "pjzlguv"
---

# Angularでfavicon.icoをassetsディレクトリで管理する

favicon.ico、apple-touch-icon.pngなどをルートに置きたい場合、src直下に置いていくと邪魔なのでassetsディレクトリに置いていきたい場合。

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

これでビルド後はfavicon.icoがルートに置かれる。https://example.com/favicon.ico のようにアクセス可能になる。
