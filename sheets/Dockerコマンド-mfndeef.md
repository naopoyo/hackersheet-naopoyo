---
name: "Dockerコマンド"
slug: "mfndeef"
tags: ["Docker"]
---


## レジストリ操作

```
docker search
```

Docker Hub のイメージを検索

```
docker pull
```

レジストリからイメージやリポジトリを取得


## コンテナ操作

```
docker rm `docker ps -a -q`
```

すべてのコンテナを削除

```
docker rm
```

コンテナを削除

```
docker ps -aq | xargs docker stop | xargs docker rm
```

コンテナをすべて停止して削除

```
docker exec -it [CONTAINER_ID] /bin/sh
```

コンテナにログイン

```
docker run -itd [IMAGE_ID]
```

コンテナを起動

```
docker ps
```

起動中のコンテナ一覧


## イメージ操作

```
docker images
```

イメージ一覧

```
docker build
```

イメージの作成

```
docker rmi [IMAGE_ID]
```

イメージ削除

```
docker rmi $(docker images -q)
```

全てのイメージを削除

