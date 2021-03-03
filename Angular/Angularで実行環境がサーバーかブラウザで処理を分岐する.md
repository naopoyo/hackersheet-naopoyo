---
name: "Angularで実行環境がサーバーかブラウザで処理を分岐する"
slug: "mqsgzrh"
---

# Angularで実行環境がサーバーかブラウザで処理を分岐する

## import

```typescript
import { Inject, PLATFORM_ID } from '@angular/core'
import { isPlatformServer, isPlatformBrowser } from '@angular/common'
```

## constructor

```typescript
constructor(
  @Inject(PLATFORM_ID) private platformId: Object
) {}
```

## サーバー（SSR)

```typescript
isPlatformServer(this.platformId)
```

## ブラウザ

```typescript
isPlatformBrowser(this.platformId)
```
