---
name: "Angular CDKでクリップボードにコピー"
tags: ["Angular"]
---

# Angular CDKでクリップボードにコピー

## モジュールをインポート

```typescript
import { ClipboardModule } from '@angular/cdk/clipboard'
```

```typescript
@NgModule({
  imports: [
    ClipboardModule,
  ]})
```

## クリップボードサービス

```typescript
import { Clipboard } from '@angular/cdk/clipboard'
```

```typescript
constructor(private clipboard: Clipboard) {}

this.clipboard.copy(value)
```
