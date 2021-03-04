---
name: "zsh"
slug: "zgyprvp"
tags: ["開発環境"]
---

# zsh

## Homebrew でインストール

```
brew install zsh
```


## /etc/shells を編集

ログインシェルにできるプログラムをフルパスで記述するファイル。

/usr/local/bin/zshを追記。

```bash
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

# ...(中略)... #

/bin/sh
/bin/tcsh
/bin/zsh
/usr/local/bin/zsh # 追記
```


## 起動時のシェルを変更

```
chsh -s /usr/local/bin/zsh
```


## .zshrc の設定

```
autoload -U compinit
compinit
```

補完

```
setopt auto_pushd
```

```
setopt auto_cd
```


## その他

```
exec $SHELL -l
```

シェルの再起動

