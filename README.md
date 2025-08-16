# Infra (Argo CD + App of Apps)

## Requisitos

- Kubernetes com Ingress Controller
- kubectl e argocd-cli
- Acesso ao registry/helm repo (Nexus) se privado
- (Opcional) SealedSecrets/External Secrets/SOPS para gerenciar segredos

## Bootstrap

```bash
kubectl apply -f bootstrap/00-namespace.yaml
kubectl apply -f bootstrap/20-appproject-platform.yaml
kubectl apply -f bootstrap/10-app-argocd.yaml
```
