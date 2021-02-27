---
name: "Angularのimport fromの短縮"
slug: "fiwnzbq"
tags: ["Angular"]
---

tsconfig.json に以下を追記。

```json
{
  "compilerOptions": {
    "baseUrl": "src",
    "paths": {
      "@app/*": ["app/*"]
    }
  }
}
```

すると、以下のように import できる。

```typescript
import { Hoge } from '@app/hoge'
```

[Angular](https://hackersheet.com/lbbxcpx/sheets/yezfvlo)

