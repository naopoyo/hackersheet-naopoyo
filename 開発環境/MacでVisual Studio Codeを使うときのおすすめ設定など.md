---
name: "MacでVisual Studio Codeを使うときのおすすめ設定など"
slug: "klivycc"
emoji: "🔵"
tags: ["開発環境", "VSCode"]
---

# MacでVisual Studio Codeを使うときのおすすめ設定など

## Homebrew でインストール

```
brew install --cask visual-studio-code
```

## 拡張機能

- **[GitHub Theme](https://marketplace.visualstudio.com/items?itemName=GitHub.github-vscode-theme)** (GitHub.github-vscode-theme)  
  GitHubのテーマ。`GitHub Dark Dimmed` がおすすめ。
- **vscode-icons** (vscode-icons-team.vscode-icons)  
  ファイルツリーにアイコンを表示。
- **Prettier** (esbenp.prettier-vscode)  
  コードフォーマット。
- **Markdown All in One** (yzhang.markdown-all-in-one)  
  Markdownを便利に使える機能が多数。
- **[Markdown Table](https://marketplace.visualstudio.com/items?itemName=TakumiI.markdowntable)** (TakumiI.markdowntable)  
  Markdownの表を整形してくれるなど。
- **[Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)** (ms-vscode-remote.remote-containers)  
  VS CodeからDockerコンテナを開発環境にできる。
- **[Peacock](https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock)** (johnpapa.vscode-peacock)  
  ワークスペースの色を変更できる。
- **[Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)** (donjayamanne.githistory)  
  Gitの履歴閲覧。

## ショートカット

### VS Code

| キー                       | 説明                     |
| -------------------------- | ------------------------ |
| `control` + `` ` ``        | ターミナルを開く         |
| `option` + `shift` + `F`   | コードフォーマット       |
| `command` + `option` + `F` | 検索・置換               |
| `command` + `K` -> `V`     | Markdown Preview         |
| `command` + `P`            | クイックオープン         |
| `command` + `shift` + `P`  | コマンドパレット         |
| `control` + `R`            | 最近開いたフォルダを表示 |
| `command` + `shift` + `N`  | 新しいウィンドウを開く   |

### Markdown All in One

| キー                      | 説明                 |
| ------------------------- | -------------------- |
| `control` + `shift` + `]` | 見出しレベルを上げる |
| `control` + `shift` + `[` | 見出しレベルを下げる |
| `control` + `B`           | 太字                 |

## 設定

### 空白を表示する

```
"editor.renderWhitespace": "all",
```

### 括弧に色を付ける

```
"editor.bracketPairColorization.enabled": true,
```

### 等幅フォント

`Osaka-Mono` を追加。

```
"editor.fontFamily": "'Osaka-Mono', Menlo, Monaco, 'Courier New', monospace",
```

### 保存時にフォーマット

```
"editor.formatOnSave": true,
```
