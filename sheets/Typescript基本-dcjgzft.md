---
name: "Typescript基本"
slug: "dcjgzft"
tags: ["Typescript"]
---


## イベント中断

```typescript
$event.stopImmediatePropagation();
```

他のリスナーを実行しない

```typescript
$event.preventDefault();
```

デフォルトのキャンセル


## 配列操作

```typescript
[].filter((x, i, self) => self.indexOf(x) === i)
```

重複したものを削除

```typescript
[].edges.slice(-1)[0]
```

配列の最後を取得

```typescript
[].filter(value => value !== target)
```

配列からtargetを削除

```typescript
let a = [1, 4, 9, 16];

const b = a.map((x:number) => x * 2);

console.log(b); // [2, 8, 18, 32]
```


## 固定の文字列の型を定義

```typescript
role: "admin" | "member" | "guesr";
```


## 関連シート

[Typescript Base64のエンコードとデコード](https://hackersheet.com/lbbxcpx/sheets/bvtrkwt)

[Typescript 特定の文字列だけを許可する型を作る](https://hackersheet.com/lbbxcpx/sheets/rvwtqcm)

