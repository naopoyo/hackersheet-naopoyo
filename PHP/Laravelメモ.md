---
name: "Laravelメモ"
slug: "lpugtvz"
tags: ["PHP", "Laravel"]
---

# Laravelメモ

## プロジェクト作成

```
composer create-project laravel/laravel laratest
```

## ビルトインサーバ起動

```
php artisan serve --host 0.0.0.0 --port=8080
```

## composerでphp-cs-fixerをインストール

```
composer global require friendsofphp/php-cs-fixer
```

## mbstring

- docker-php-ext-install mbstring
- libonig-dev
  - https://github.com/docker-library/php/issues/880
- oniguruma-dev
