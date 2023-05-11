---
name: "TypeScriptで連想配列をクエリパラメータにする"
slug: "vjmmbys"
tags: ["TypeScript"]
---

# TypeScriptで連想配列をクエリパラメータにする

```typescript
const data = { query: 'xxxx', page: 1 }
let result = []
for (let d in data)
  result.push(encodeURIComponent(d) + '=' + encodeURIComponent(data[d]))
result.join('&')
```