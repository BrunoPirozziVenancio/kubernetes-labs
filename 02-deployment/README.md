# 02 - Deployment

Um Deployment gerencia um conjunto de Pods identicos, garantindo que o numero desejado de replicas esteja sempre rodando.

## Arquivo

- **deployment.yaml** — Deployment com 3 replicas do Nginx

## Como aplicar

### Criar o Deployment
kubectl apply -f deployment.yaml

### Verificar os Pods criados
kubectl get pods

### Verificar o Deployment
kubectl get deployments

### Escalar para 5 replicas
kubectl scale deployment nginx-deployment --replicas=5

### Ver historico de rollout
kubectl rollout history deployment/nginx-deployment

### Deletar o Deployment
kubectl delete -f deployment.yaml
