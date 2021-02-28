---
name: "Angular CDKでクリップボードにコピー"
slug: "idzoxhm"
tags: ["Angular"]
---

# Angular CDKでクリップボードにコピー

Angular CDKのモジュールを使って、クリップボードにコピーする機能をつくる。

## モジュールをインポート

app.module.tsなどで、以下のようにインポート。

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
