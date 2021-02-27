---
name: "MacでVisual Studio Codeを使うときのメモ"
slug: "klivycc"
tags: ["開発環境"]
---

# MacでVisual Studio Codeを使うときのメモ

## Homebrew でインストール

```
brew cask install visual-studio-code
```

## 拡張機能

- **vscode-icons**  
  ファイルツリーにアイコンを表示
- **Prettier**  
  コードフォーマット
- **Markdown All in One**  
  Markdownを便利に
- **Text Tables**  
  Markdownの表を便利に

## ショートカット

| キー                        | 説明               |
| ------------------------- | ---------------- |
| Control + `               | ターミナルを開く         |
| option + shift + F        | コードフォーマット        |
| ⌘ + K → V                 | Markdown Preview |
| Control + Q → Control + Q | Table Mode切り替え   |
| ⌘ + P                     | クイックオープン         |

## 設定

### 空白を表示する

```
"editor.renderWhitespace": "all",
```
