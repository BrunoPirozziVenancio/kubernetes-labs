# 03 - Service

Um Service expoe os Pods para acesso interno ou externo ao cluster.

## Arquivo

- **service.yaml** — Service NodePort expondo o Nginx na porta 30080

## Tipos de Service

- ClusterIP: acesso apenas interno ao cluster (padrao)
- NodePort: expoe em uma porta do node, acessivel externamente
- LoadBalancer: cria um load balancer externo (usado em cloud)

## Como aplicar

### Aplicar o Deployment primeiro
kubectl apply -f ../02-deployment/deployment.yaml

### Criar o Service
kubectl apply -f service.yaml

### Verificar o Service
kubectl get services

### Acessar no navegador
http://localhost:30080

### Deletar o Service
kubectl delete -f service.yaml
