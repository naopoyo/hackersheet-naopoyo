---
name: "Prezto"
slug: "dlxdoaq"
tags: ["Linux"]
---

# Prezto
zshの環境設定フレームワーク。


## インストール

```
git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
```

```
setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
```

設定ファイル作成

この後ターミナル再起動。


## アップデート

```
cd $ZPREZTODIR
```

```
git pull
```

```
git submodule update --init --recursive
```


## テーマ関連コマンド

```
prompt -c
```

適用しているテーマを確認

```
prompt -l
```

使えるテーマ一覧

```
prompt -p
```

テーマのプレビュー

```
prompt -s <theme>
```

テーマを設定


## git plugin追加

```
vi .zpreztorc
```

```bash
# Set the Prezto modules to load (browse modules).
# The order matters.
zstyle ':prezto:load' pmodule \
  'git' \ # 追記
  'environment' \
  # ... 中略 ... #
  'completion' \
  'prompt'
```

'git' \を追記

