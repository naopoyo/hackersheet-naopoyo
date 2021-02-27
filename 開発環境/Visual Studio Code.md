---
name: "Visual Studio Code"
slug: "klivycc"
tags: ["開発環境"]
---

# Visual Studio Code

MacでVisual Studio Codeを使うときのいろいろなメモ。

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
| ⌘ + k → v                 | Markdown Preview |
| Control + q → Control + q | Table Mode切り替え   |
| ⌘ + p                     | クイックオープン         |

## 設定

### 空白を表示する

```
"editor.renderWhitespace": "all",
```
