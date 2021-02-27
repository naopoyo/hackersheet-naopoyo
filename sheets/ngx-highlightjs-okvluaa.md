---
name: "ngx-highlightjs"
slug: "okvluaa"
tags: ["Angular"]
---


## 概要

Angularでシンタックスハイライト


## インストール

```
npm install -S ngx-highlightjs highlight.js
```

```
npm install --save-dev @types/highlight.js
```

@typesインストール

```scss
// style.scss
@import '~highlight.js/scss/atom-one-dark.scss';
```

scssをインポート


## directiveの使い方

```xml
<pre><code [highlight]="someCode"></code></pre>
```


## 全ての言語をインポート

```typescript
export function hljsLangs() {
  const langs = hljs.listLanguages()

  return langs.map((n: string) => {
    return {name: n, func: function () { return hljs.getLanguage(n) }}
  });
}
```

```typescript
@NgModule({
  imports: [
    // ...
    HighlightModule.forRoot({
      languages: hljsLangs
    })
  ]
})
export class AppModule { }
```

@NgModuleのインポート

[Angular](https://hackersheet.com/lbbxcpx/sheets/yezfvlo)

