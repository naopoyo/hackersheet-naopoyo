---
name: "VSCode Ruby Extension"
slug: "eeitltd"
---

# VSCode Ruby Extension
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

db/schema.rbが除外されない時は`"forceExclusion": true`