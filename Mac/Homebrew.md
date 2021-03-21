---
name: "Homebrewのはじめかた"
slug: "kyqkdgj"
tags: ["Mac"]
---

# Homebrewのはじめかた

## 公式

- [The Missing Package Manager for macOS (or Linux) — Homebrew](https://brew.sh/)
- [Homebrew Formulae](https://formulae.brew.sh/)

## インストール

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### .zshrc修正

```
export PATH="/opt/homebrew/bin:$PATH"
```

上記を追記。

## コマンド

### Homebrewの問題を確認

```
brew doctor
```

### アップデート

```
brew update
```

### インストール済の一覧

```
brew list
```



