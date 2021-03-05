---
name: "GKE BackendConfig メモ"
slug: "usuftrk"
tags: ["GCP", "Kubernetes"]
---

# GKE BackendConfig メモ

## BackendConfig

```yaml
apiVersion: cloud.google.com/v1
kind: BackendConfig
metadata:
  name: my-backend-config
spec:
  healthCheck:
    checkIntervalSec: 60
    timeoutSec: 60
    type: HTTP
    requestPath: /healthz
  securityPolicy:
    name: "my-cloud-armor-policy"
```

## Service

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
  annotations:
    cloud.google.com/backend-config: '{"default": "my-backend-config"}'
```

## 確認

```
kubectl get backendconfig
```