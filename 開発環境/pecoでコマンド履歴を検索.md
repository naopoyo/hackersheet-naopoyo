---
name: "pecoでコマンド履歴を検索"
slug: "jbpwqdv"
tags: ["開発環境"]
---

# pecoでコマンド履歴を検索

zshを使っている場合。

## インストール

```
brew install peco
```

## .zshrc

.zshrcに以下を追記する。

```sh
function peco-history-selection() {
    BUFFER=`history -n 1 | tail -r  | awk '!a[$0]++' | peco`
    CURSOR=$#BUFFER
    zle reset-prompt
}

zle -N peco-history-selection
bindkey '^R' peco-history-selection
```

## ショートカット

`⌃` + `R`

## リンク

- [iTerm + zsh + prezto + pecoの組合せ | 公開懺悔日記](https://www.barasu.org/pc/mac/13705.html)
- [peco/peco: Simplistic interactive filtering tool](https://github.com/peco/peco)
