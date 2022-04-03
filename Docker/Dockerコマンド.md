---
name: "Dockerコマンド"
slug: "mfndeef"
tags: ["Docker"]
---

# Dockerコマンド

## レジストリ操作

### Docker Hub のイメージを検索

```
docker search
```

### レジストリからイメージやリポジトリを取得

```
docker pull
```

## コンテナ操作

### すべてのコンテナを削除

```
docker rm `docker ps -a -q`
```

### コンテナを削除

```
docker rm
```

### コンテナをすべて停止して削除

```
docker ps -aq | xargs docker stop | xargs docker rm
```

### コンテナにログイン

```
docker exec -it [CONTAINER_ID] /bin/sh
```

### コンテナを起動

```
docker run -itd [IMAGE_ID]
```

### 起動中のコンテナ一覧

```
docker ps
```

### 起動してログイン

```
docker run --rm -it [CONTAINER_ID] sh 
```

## イメージ操作

### イメージ一覧

```
docker images
```

### イメージの作成

```
docker build
```

### イメージ削除

```
docker rmi [IMAGE_ID]
```

### 全てのイメージを削除

```
docker rmi $(docker images -q)
```

### <none>なイメージを削除

```
docker rmi $(docker images -f "dangling=true" -q)
```
