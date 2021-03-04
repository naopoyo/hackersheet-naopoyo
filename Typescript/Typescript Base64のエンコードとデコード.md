---
name: "TypescriptのBase64のエンコードとデコード"
slug: "bvtrkwt"
tags: ["Typescript"]
---

# TypescriptのBase64のエンコードとデコード

Tytpescript/JavascriptでBase64のエンコードとデコードの方法。

## Buffer

Node.jsの場合は、Bufferを使える

### import

```typescript
import { Buffer } from 'buffer'
```

### エンコード

```typescript
const encodedData = Buffer.from('Hello, world').toString('base64')
```

### デコード

```typescript
const decodedData = Buffer.from(encodedData, 'base64').toString()
```


***

## btoa / atob

Javascriptだけで行う場合は以下。

### エンコード

```typescript
var encodedData = window.btoa("Hello, world");
```

### デコード

```typescript
var decodedData = window.atob(encodedData);
```

### ユニコードの文字列を扱う場合

escapeとunescapeは非推奨

#### エンコード

```typescript
function utf8_to_b64(str) {
  return window.btoa(unescape(encodeURIComponent(str)))
}
```

#### デコード

```typescript
function b64_to_utf8(str) {
  return decodeURIComponent(escape(window.atob(str)));
}
```


