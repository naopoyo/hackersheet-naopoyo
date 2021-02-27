---
name: "Typescript Base64のエンコードとデコード"
slug: "bvtrkwt"
---

# TypescriptのBase64のエンコードとデコード

## エンコード

```typescript
var encodedData = window.btoa("Hello, world");
```

## デコード

```typescript
var decodedData = window.atob(encodedData);
```

## ユニコードの文字列を扱う場合

escapeとunescapeは非推奨

### エンコード

```typescript
function utf8_to_b64(str) {
  return window.btoa( unescape(encodeURIComponent( str )) );
}
```

### デコード

```typescript
function b64_to_utf8(str) {
  return decodeURIComponent( escape(window.atob( str )) );
}
```


