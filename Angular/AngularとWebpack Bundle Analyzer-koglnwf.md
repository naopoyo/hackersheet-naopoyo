---
name: "AngularとWebpack Bundle Analyzer"
slug: "koglnwf"
tags: ["Angular"]
---

# AngularとWebpack Bundle Analyzer

バンドルファイルの容量を可視化するWebpack Bundle AnalyzerをAngularでつかう。

## インストール

```
npm install --save-dev webpack-bundle-analyzer
```

## package.jsonを修正

scriptsに追加。

```json
{
  "scripts": {
    "analyze": "ng build --stats-json && webpack-bundle-analyzer dist/browser/stats.json",
  },
}
```

## 実行

```
npm run analyze
```