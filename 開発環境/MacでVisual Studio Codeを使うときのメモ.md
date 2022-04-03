---
name: "MacでVisual Studio Codeを使うときのメモ"
slug: "klivycc"
tags: ["開発環境", "VSCode"]
---

# MacでVisual Studio Codeを使うときのメモ

## Homebrew でインストール

```
brew install --cask visual-studio-code
```

## 拡張機能

- **vscode-icons** (vscode-icons-team.vscode-icons)  
  ファイルツリーにアイコンを表示
- **Prettier** (esbenp.prettier-vscode)  
  コードフォーマット
- **Markdown All in One** (yzhang.markdown-all-in-one)  
  Markdownを便利に
- **Text Tables** (RomanPeshkov.vscode-text-tables)  
  Markdownの表を便利に
- **Remote - Containers** (ms-vscode-remote.remote-containers)  
  Dockerのコンテナ内でVSCodeを開いて開発可能に

## ショートカット

| キー                                      | 説明               |
| --------------------------------------- | ---------------- |
| `⌃(control)` + `` ` ``                  | ターミナルを開く         |
| `⌥(option)` + `⇧(shift)` + `F`          | コードフォーマット        |
| `⌘(command)` + `K` → `V`                | Markdown Preview |
| `⌃(control)` + `Q` → `⌃(control)` + `Q` | Table Mode切り替え   |
| `⌘(command)` + `P`                      | クイックオープン         |
| `⌘(command)` + `⇧(shift)` + `P`         | コマンドパレット         |
| `⌃(control)` + `R`                      | 最近開いたフォルダを表示     |
| `⌘(command)` + `⇧(shift)` + `N`         | 新しいウィンドウを開く      |

## 設定

### 空白を表示する

```
"editor.renderWhitespace": "all",
```

### 括弧に色を付ける

```
"editor.bracketPairColorization.enabled": true,
```
