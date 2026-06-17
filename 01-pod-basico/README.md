# 01 - Pod Básico

Um Pod é a menor unidade do Kubernetes. Ele contém um ou mais containers que compartilham rede e armazenamento.

## Arquivo

- **pod.yaml** — Pod com Nginx rodando na porta 80

## Como aplicar

### Criar o Pod
kubectl apply -f pod.yaml

### Verificar se está rodando
kubectl get pods

### Ver detalhes do Pod
kubectl describe pod nginx-pod

### Acessar o Pod localmente
kubectl port-forward pod/nginx-pod 8080:80

### Deletar o Pod
kubectl delete -f pod.yaml
