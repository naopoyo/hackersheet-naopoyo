# TypeScriptのimportをソートする

VS Codeの場合、拡張昨日の[TypeScript Import Sorter](https://marketplace.visualstudio.com/items?itemName=mike-co.import-sorter) (mike-co.import-sorter)をインストールする。

## 設定

### 保存時にソート

```json
"importSorter.generalConfiguration.sortOnBeforeSave": true,
```

### セミコロンをつけない

```json
"importSorter.importStringConfiguration.hasSemicolon": false,
```
