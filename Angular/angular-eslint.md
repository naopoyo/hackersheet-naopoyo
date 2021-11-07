---
name: "angular-eslint"
slug: "cpywyhs"
tags: ["Angular"]
---

# angular-eslint

## @angular-eslint/schematicsを追加

```
ng add @angular-eslint/schematics
```

## angular.jsonに設定追加

```
ng config cli.defaultCollection @angular-eslint/schematics
```

## プロジェクトにESLintを追加

```
ng g @angular-eslint/schematics:add-eslint-to-project <project-name>
```