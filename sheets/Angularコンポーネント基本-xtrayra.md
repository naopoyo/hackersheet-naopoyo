---
name: "Angularコンポーネント基本"
slug: "xtrayra"
tags: ["Angular"]
---


## classを動的に設定

```xml
<div [ngClass]="{ 'class-name': true, 'hoge-class': true }">
</div>
```

trueの場合、有効化

```xml
<div class="class-name hoge-class">
</div>
```

実際のHTML


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

[Angular](https://hackersheet.com/lbbxcpx/sheets/yezfvlo)

