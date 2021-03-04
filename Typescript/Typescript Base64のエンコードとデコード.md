---
name: "TypescriptのBase64のエンコードとデコード"
slug: "bvtrkwt"
tags: ["Typescript", "Javascript"]
---

# TypescriptのBase64のエンコードとデコード

Tytpescript/JavascriptでBase64のエンコードとデコードの方法。


----------


## Buffer

Node.jsの場合は、Bufferを使える。

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


----------


## btoa / atob

Javascriptだけで行う場合は以下。

### エンコード

```typescript
var encodedData = window.btoa('Hello, world')
```

### デコード

```typescript
var decodedData = window.atob(encodedData)
```

### ユニコードの文字列を扱う場合

btoaとatobはASCII文字列しか対応していないので、ユニコードの文字列を扱う場合は以下のように。**unescapeとescapeは非推奨**。

#### エンコード

```typescript
var encodedData = window.btoa(unescape(encodeURIComponent('こんにちは')))
```

#### デコード

```typescript
var decodedData = decodeURIComponent(escape(window.atob(encodedData)))
```


