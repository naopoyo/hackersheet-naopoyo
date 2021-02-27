---
name: "Kubernetesコマンド"
slug: "yghmmdg"
tags: ["Kubernetes"]
---

# Kubernetesコマンド

## Pod一覧

```
kubectl get pod
```

## Pod削除

```
kubectl delete pod [POD_NAME]
```

## UnknownなPodを削除

```
kubectl delete pod [POD_NAME] --grace-period=0 --force
```

## [DIR_NAME]以下のマニフェストファイルをすべて適用

```
kubectl apply -f [DIR_NAME] -R
```

## コンテナにログイン

```
kubectl exec -it [POD_NAME] --container [CONTAINER_NAME] /bin/sh
```


