---
name: "TypeScriptで背景色から読みやすいテキスト色を選択する方法"
slug: "bltootb"
emoji: "🎨"
tags: ["TypeScript"]
---

# TypeScriptで背景色から読みやすいテキスト色を選択する方法

## wcag-contrastをインストール

```
npm i --save wcag-contrast @types/wcag-contrast  
```

## サンプルコード

```typescript
import { hex } from 'wcag-contrast'

export function chooseTextColor(backgroundColor: string) {
  return hex(backgroundColor, '#ffffff') < hex(backgroundColor, '#000000')
    ? '#000000'
    : '#ffffff'
}

// 例
chooseTextColor('#ff0000') // #000000
chooseTextColor('#111111') // #ffffff
```
