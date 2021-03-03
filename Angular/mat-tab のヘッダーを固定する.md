---
name: "mat-tab のヘッダーを固定する"
slug: "ljyexir"
tags: ["Angular"]
---

# mat-tab のヘッダーを固定する

Angular Materialのタブコンポーネントのヘッダー部分を固定するためのCSS。

```css
::ng-deep .mat-tab-header {
  z-index: 1001;
  width: 100vw;
  position: fixed !important;
  background-color: #ffffff !important;
}
```

```css
::ng-deep .mat-tab-body-wrapper {
  position: relative !important;
  margin-top: 48px;
}
```
