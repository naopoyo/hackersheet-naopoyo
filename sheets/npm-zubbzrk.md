---
name: "npm"
slug: "zubbzrk"
tags: ["npm"]
---


## パッケージの確認

```
npm list -g --depth=0
```

グローバル環境にインストールされているパッケージを確認

```
npm ls
```

インストールされているパッケージ一覧


## npm のアップデート

```
npm install -g npm@latest
```

最新版をグローバル環境にインストール・アップデート


## パッケージのインストール

```
npm install
```

package.jsonの内容でパッケージをインストール

```
npm ci
```

package-lock.jsonからパッケージをインストール

```
npm i —save [PACKAGE]
```

パッケージのインストール。package.jsonに追記

```
npm i —save-dev [PACKAGE]
```

パッケージのインストール。devDependenciesに追記


## パッケージのアップデート

```
npm update
```


## パッケージのアンインストール

```
npm uninstall —save [PACKAGE]
```

パッケージをアンインストール


## キャッシュ関連

```
npm cache verify
```

キャッシュの確認

```
npm cache clean --force
```

キャッシュクリア(非推奨)


## 脆弱性修正

```
npm audit
```

確認

```
npm audit fix
```

修正


## 関連シート

[npm バージョン表記](https://hackersheet.com/lbbxcpx/sheets/qkpebrd)

[npm キャッシュクリア](https://hackersheet.com/lbbxcpx/sheets/xbnfttt)

[ncu](https://hackersheet.com/lbbxcpx/sheets/stcecoq)

