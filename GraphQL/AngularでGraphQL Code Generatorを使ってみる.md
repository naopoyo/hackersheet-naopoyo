---
name: "AngularでGraphQL Code Generatorを使ってみる"
slug: "jdkocjs"
tags: ["GraphQL", "Angular"]
---

# AngularでGraphQL Code Generatorを使ってみる

## インストール

```
npm i --save graphql
```

```
npm i --save-dev @graphql-codegen/cli
```

```
npm i --save-dev @graphql-codegen/typescript
```

### 初期設定

```
npx graphql-codegen init
```

```
    Welcome to GraphQL Code Generator!
    Answer few questions and we will setup everything for you.
  
? What type of application are you building? Application built with Angular
? Where is your schema?: (path or url) http://localhost:3000/graphql
? Where are your operations and fragments?: src/**/*.gql
? Pick plugins: TypeScript (required by other typescript plugins), TypeScript Operations (operations and fragments), TypeScript Apollo Angular (typed GQL services)
? Where to write the output: src/generated/graphql.ts
? Do you want to generate an introspection file? No
? How to name the config file? codegen.yaml
? What script in package.json should run the codegen? generate
Fetching latest versions of selected plugins...

    Config file generated at codegen.yaml
    
      $ npm install

    To install the plugins.

      $ npm run generate

    To run GraphQL Code Generator.
```

設定後に `npm i` でプラグインがインストールされる。

### 補足1: What script in package.json should run the codegen?

「What script in package.json should run the codegen?」を「generate」にすると、package.jsonに以下が追加される。

```
{
  "scripts": {
    "generate": "graphql-codegen --config codegen.yml"
  }
}
```

### 補足2: schemaにアクセスする時のリクエストヘッダーを設定する

codegen.ymlを以下のように修正。

```yaml
schema:
  - http://localhost:3000/graphql:
      headers:
        X-Requested-With: "XMLHttpRequest"
```

## 使ってみる

```
npm run generate
```

※ `src/**/*.graphql` が無いとエラーになる。

## リンク

- [GraphQL Code Generator | GraphQL Code Generator](https://www.graphql-code-generator.com/)