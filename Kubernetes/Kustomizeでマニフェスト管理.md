---
name: "Kustomizeでマニフェスト管理"
slug: "aiesewk"
tags: ["Kubernetes"]
---

# Kustomizeでマニフェスト管理

## ディレクトリ構成

```
.
├── base
│   └── kustomization.yaml
└── overlays
    ├── dev
    │   └── kustomization.yaml
    └── prod
        └── kustomization.yaml
```

## リンク

- [Kustomize - Kubernetes native configuration management](https://kustomize.io/)