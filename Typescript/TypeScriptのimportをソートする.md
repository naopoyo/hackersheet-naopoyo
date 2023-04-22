---
name: "Typescriptのimportをソートする"
slug: "bsphcmu"
tags: ["Typescript", "VSCode"]
---

# TypeScriptのimportをソートする


## TypeScript Import Sorter

VS Codeの場合、拡張機能の[TypeScript Import Sorter](https://marketplace.visualstudio.com/items?itemName=mike-co.import-sorter) (mike-co.import-sorter)をインストールする。

### TypeScript Import Sorterの設定

#### 保存時にソートする

```json
"importSorter.generalConfiguration.sortOnBeforeSave": true,
```

#### セミコロンをつけない

```json
"importSorter.importStringConfiguration.hasSemicolon": false,
```

#### タブのスペースを2個にする

```json
"importSorter.importStringConfiguration.tabSize": 2,
```
