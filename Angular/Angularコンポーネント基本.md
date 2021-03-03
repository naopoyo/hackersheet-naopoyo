---
name: "Angularコンポーネント基本"
slug: "xtrayra"
tags: ["Angular"]
---

# Angularコンポーネント基本

## classを動的に設定

```html
<div [ngClass]="{ 'class-name': true, 'hoge-class': true }">
</div>
```

trueの場合、有効化。

[ngClass]で出力されるHTMLは以下。

```html
<div class="class-name hoge-class">
</div>
```

## 条件分岐 (ngIf)

```html
<ng-container *ngIf="true">
</ng-container>
```


## 条件分岐 (ngSwitch)

```html
<ng-container [ngSwitch]="val">
    <div *ngSwitchCase="case">
        hoge
    </div>
    <div *ngSwitchDefault>
        fuga
    </div>
</ng-container>
```


## 繰り返し

```html
<ng-container *ngFor="let item of items; let i = index">
</ng-container>
```
