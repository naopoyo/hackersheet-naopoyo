---
name: "M1 MacでMinikubeを使ってみる"
slug: "ryfmggz"
tags: ["Kubernetes"]
---

# M1 MacでMinikubeを使ってみる

## Minikubeをインストール

```
brew install minikube
```

## Minikubeを起動

```
minikube start
```

## Deploymentを作成

```
kubectl create deployment hello-minikube --image=arm64v8/nginx
```

※[Minikubeを使用してローカル環境でKubernetesを動かす | Kubernetes](https://kubernetes.io/ja/docs/setup/learning-environment/minikube/)に書いてある `--image=k8s.gcr.io/echoserver:1.10` だとM1 Macでは動かない

## Serviceを作成

```
kubectl expose deployment hello-minikube --type=NodePort --port=80
```

## ブラウザで開いてみる

```
minikube service hello-minikube
```

nginxのデフォルトページが開いたら成功🎉

## DeploymentとServiceを削除

```
kubectl delete service hello-minikube
```

```
kubectl delete deployment hello-minikube
```

## Minikubeを停止

```
minikube stop
```
