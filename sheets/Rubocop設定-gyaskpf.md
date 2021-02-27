---
name: "Rubocop設定"
slug: "gyaskpf"
---

# Rubocop設定
プロジェクトルートに .rubocp.yml を作る。

## AllCops

```yaml
AllCops:
  DisplayStyleGuide: true
  ExtraDetails: true
  TargetRubyVersion: 2.6
  NewCops: enable
```

## Exclude

```yaml
AllCops:
  Exclude:
    - bin/**/*
    - db/schema.rb
    - db/migrate/*.rb
    - node_modules/**/*
    - tmp/**/*
    - vendor/**/*
```

## コメントの無いクラスを許可する

```yaml
Style/Documentation:
  Enabled: false
```

## Missing frozen string literal comment.対策

```yaml
Style/FrozenStringLiteralComment:
  Enabled: false
```


## 関連シート

[Ruby](https://hackersheet.com/lbbxcpx/sheets/putgewh)

