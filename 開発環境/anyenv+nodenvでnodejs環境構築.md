---
name: "anyenv+nodenvでnodejs環境構築"
slug: "grbwfmj"
---

# anyenv+nodenvでnodejs環境構築

## インストール

```
anyenv install nodenv
```

```
exec $SHELL -l
```

シェルを再起動


## 使う

```
nodenv install --list
```

```
nodenv install [VERSION]
```

```
nodenv rehash
```

```
nodenv global [VERSION]
```


## アップデート

```
mkdir -p "$(nodenv root)"/plugins
```

```
git clone https://github.com/nodenv/nodenv-update.git "$(nodenv root)"/plugins/nodenv-update
```

```
nodenv update
```

