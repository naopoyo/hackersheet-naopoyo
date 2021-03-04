---
name: "VSCode Ruby Extension"
slug: "eeitltd"
tags: ["開発環境", "Ruby"]
---

# VSCode Ruby Extension

## 公式

[Ruby - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=rebornix.Ruby)

## settings.json

```json
{
  "ruby.format": "rubocop",
  "ruby.lintDebounceTime": 5000,
  "ruby.lint": {
    "rubocop": {
      "useBundler": false,
      "forceExclusion": true
    }
  },
  "ruby.useBundler": false,
  "ruby.useLanguageServer": false,
}
```

`"forceExclusion": true` を指定しないとlintでdb/schema.rbが除外されない。