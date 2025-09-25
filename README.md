# Репозиторий с манифестами Kubernetes

Примерная структура репозитория

```
k8s-config/
├── apps/                           # Манифесты конкретных приложений
│   ├── frontend/
│   │   ├── base/
│   │   └── overlays/
│   │       ├── staging/
│   │       └── production/
│   └── backend/
├── infrastructure/                 # Системные компоненты кластера
│   ├── monitoring/                 # (Prometheus, Grafana)
│   ├── logging/                    # (Fluentd, Loki)
│   ├── cert-manager/
│   └── ingress-nginx/
├── clusters/
│   ├── production/                 # Конфигурация для prod-кластера
│   │   ├── kustomization.yaml     # <- На него указывает корневое приложение ArgoCD
│   │   └── app-of-apps.yaml       # Список всех приложений для этого кластера
│   └── staging/
└── namespaces/                     # Пространства имён и RBAC
    ├── frontend-ns.yaml
    └── backend-ns.yaml
```
