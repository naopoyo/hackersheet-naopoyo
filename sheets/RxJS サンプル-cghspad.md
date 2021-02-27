---
name: "RxJS サンプル"
slug: "cghspad"
---

# RxJSサンプル

## of

```typescript
of(1, 2).subscribe(x => console.log(x));
// 1
// 2
```


## map

```typescript
of(1, 2).pipe(map(x => x+100))
        .subscribe(x => console.log(x));
// 101
// 102
```
