---
name: "Kubernetesコマンド"
slug: "yghmmdg"
tags: ["Kubernetes"]
---


## Pod関連

```
kubectl get pod
```

Pod一覧

```
kubectl delete pod [POD_NAME]
```

Pod削除

```
kubectl delete pod [POD_NAME] --grace-period=0 --force
```

Unknown な Pod を削除


## その他

```
kubectl apply -f [DIR_NAME] -R
```

[DIR_NAME]以下のマニフェストファイルをすべて適用

```
kubectl exec -it [POD_NAME] --container [CONTAINER_NAME] /bin/sh
```

コンテナにログイン

