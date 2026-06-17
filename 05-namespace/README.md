# 05 - Namespace

Namespaces dividem o cluster em ambientes isolados, como dev, staging e prod.

## Arquivo

- **namespace.yaml** — Cria os namespaces dev e prod

## Como aplicar

### Criar os namespaces
kubectl apply -f namespace.yaml

### Listar namespaces
kubectl get namespaces

### Criar um Pod em um namespace especifico
kubectl run nginx --image=nginx:alpine -n dev

### Listar Pods de um namespace
kubectl get pods -n dev

### Deletar os namespaces
kubectl delete -f namespace.yaml
