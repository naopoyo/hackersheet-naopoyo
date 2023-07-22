---
name: "RailsのVSCodeでの開発時にコード自動補完する"
slug: "qlqauys"
---

# RailsのVSCodeでの開発時にコード自動補完する

Railsのプロジェクトの開発にVSCodeを使っている場合、Solargraphを使って、コード自動補完やコードの定義元へのジャンプができるようになります。

VSCodeの拡張とGemのインストールが必要です。

## VSCode拡張のインストール

[Ruby Solargraph - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=castwide.solargraph)

上記の拡張機能をインストールします。

### VSCode拡張の設定

`solargraph.useBundler` の設定を有効にします。

```json
{
  "solargraph.useBundler": true
}
```

##  Solargraphをインストール

```ruby
group :development do
  gem 'solargraph'
  gem 'solargraph-rails'
end
```

Gemfileに上記のように追加して `bundle` でインストールしてください。`gem install` でグローバルにインストールした場合、サードパーティ製のライブラリのコード自動補完やコードの定義元へのジャンプができません。

インストールが正しく行えたかどうかは以下のように確認できます。

```
bundle exec solargraph --version
0.49.0
```

## solargraphの設定

プロジェクトルートに以下のような内容の `.solargraph.yml` を作成してください。`plugins` に `solargraph-rails` を追加します。

`bundle exec solargraph config` コマンドで作成することも可能です。

```yaml
---
include:
- "**/*.rb"
exclude:
- spec/**/*
- test/**/*
- vendor/**/*
- ".bundle/**/*"
- Gemfile
require:
- actioncable
- actionmailer
- actionpack
- actionview
- activejob
- activemodel
- activerecord
- activestorage
- activesupport
domains: []
reporters:
- rubocop
- require_not_found
formatter:
  rubocop:
    cops: safe
    except: []
    only: []
    extra_args: []
require_paths: []
plugins:
  - solargraph-rails
max_files: 5000
```

## サードパーティ製のライブラリのYARDドキュメント生成

```
bundle exec yard gems
```

上記のコマンドでサードパーティ製のライブラリのYARDドキュメント生成を行います。`/vendor/bundle/ruby/3.2.0/doc` のようなディレクトリにドキュメントが生成されます。

## Solargraphを再起動

`Command` + `Shift` + `P` でVSCodeのコマンドパレットを表示して `Restart Solargraph` と入力してSolargraphを再起動してください。

## 完了

完了です。
