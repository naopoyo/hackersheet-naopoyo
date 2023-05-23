---
name: "GitHubのIssuesのラベルのようなReactコンポーネントを作る"
slug: "nnvnqsr"
emoji: "🎨"
tags: ["React"]
---

# GitHubのIssuesのラベルのようなReactコンポーネントを作る

カラーコードを指定すると、自動的に見やすいテキストカラーになるラベルの作り方。

## 使用しているライブラリ

- [tinycolor2](https://bgrins.github.io/TinyColor/)  
  hexのカラーコードからRGBとHSLの数値を計算する
- [MUI](https://mui.com/)  
  sxでCSSを指定しているだけなので、他のライブラリでも良い

## コンポーネントのコード

```typescript
import { Box } from '@mui/material'
import { ReactNode } from 'react'
import tinycolor from 'tinycolor2'

interface Props {
  color: string
  children?: ReactNode
}

const Label: React.FC<Props> = (props) => {
  const color = tinycolor(props.color)
  const rgb = color.toRgb()
  const hsl = color.toHsl()

  const style = {
    '--label-r': rgb.r,
    '--label-g': rgb.g,
    '--label-b': rgb.b,
    '--label-h': hsl.h * 100,
    '--label-s': hsl.s * 100,
    '--label-l': hsl.l * 100,
    '--lightness-threshold': 0.453,
    '--border-threshold': 0.96,
    '--perceived-lightness':
      'calc( ((var(--label-r) * 0.2126) + (var(--label-g) * 0.7152) + (var(--label-b) * 0.0722)) / 255 )',
    '--lightness-switch':
      'max(0, min(calc((1/(var(--lightness-threshold) - var(--perceived-lightness)))), 1))',
    '--border-alpha':
      'max(0, min(calc((var(--perceived-lightness) - var(--border-threshold)) * 100), 1))',
    color: 'hsl(0deg, 0%, calc(var(--lightness-switch) * 100%))',
    background: 'rgb(var(--label-r), var(--label-g), var(--label-b))',
    borderColor:
      'hsla(var(--label-h), calc(var(--label-s) * 1%), calc((var(--label-l) - 25) * 1%), var(--border-alpha))',
    borderWidth: '1px',
    borderStyle: 'solid',
    borderRadius: '24px',
    paddingX: '10px',
    fontSize: '0.75rem',
  }

  return <Box sx={style}>{props.children}</Box>
}

export default Label
```

## 使用例

```typescript
<Label color='#d73a4a'>bug</Label>
```

表示例:

![](GitHub%E3%81%AEIssues%E3%81%AE%E3%83%A9%E3%83%99%E3%83%AB%E3%81%AE%E3%82%88%E3%81%86%E3%81%AAReact%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%82%92%E4%BD%9C%E3%82%8B01.jpg)

## 関連

- [Typescriptで背景色から読みやすいテキスト色を選択する方法](../TypeScript/Typescript%E3%81%A7%E8%83%8C%E6%99%AF%E8%89%B2%E3%81%8B%E3%82%89%E8%AA%AD%E3%81%BF%E3%82%84%E3%81%99%E3%81%84%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88%E8%89%B2%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95.md)
