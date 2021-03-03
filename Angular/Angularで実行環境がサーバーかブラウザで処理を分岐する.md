---
name: "Angularで実行環境がサーバーかブラウザで処理を分岐する"
slug: "mqsgzrh"
tags: ["Angular"]
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

## サーバー(SSR)の場合にtrue

```typescript
isPlatformServer(this.platformId)
```

## ブラウザの場合にtrue

```typescript
isPlatformBrowser(this.platformId)
```
