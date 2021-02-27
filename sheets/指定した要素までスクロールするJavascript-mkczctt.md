---
name: "指定した要素までスクロールするJavascript"
slug: "mkczctt"
tags: ["Javascript"]
---

```javascript
element.scrollIntoView(options)
```

要素が（ブラウザのウィンドウ上の）表示範囲に入るまでページをスクロール


## オプション

```javascript
options = {
    behavior: "auto" | "instant" | "smooth",
    block: "start" | "center" | "end" | "nearest",
    inline: "start" | "center" | "end" | "nearest"
}
```

| behavior | スクロールの動作 |
| block | 垂直方向のスクロール位置 |
| inline | 水平方向のスクロール位置 |
