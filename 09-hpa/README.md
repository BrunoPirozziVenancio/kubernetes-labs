# 09 - HorizontalPodAutoscaler

O HorizontalPodAutoscaler (HPA) escala automaticamente o numero de replicas de um Deployment com base no uso de recursos como CPU e memoria.

## Arquivos

- deployment-hpa.yaml: Deployment com requests e limits de CPU e memoria definidos
- hpa.yaml: HPA configurado para escalar entre 1 e 5 replicas

## Como funciona

Quando o uso medio de CPU ultrapassar 70% ou o uso de memoria ultrapassar 80%, o HPA aumenta o numero de replicas automaticamente. Quando o uso cair, o HPA reduz as replicas ate o minimo de 1.

## Pre-requisito

O Metrics Server precisa estar instalado no cluster.
Para instalar no Docker Desktop:

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

## Como aplicar

### Criar o Deployment
kubectl apply -f deployment-hpa.yaml

### Criar o HPA
kubectl apply -f hpa.yaml

### Verificar o HPA
kubectl get hpa

### Ver detalhes do HPA
kubectl describe hpa app-hpa

### Simular carga para testar o escalonamento
kubectl run load-test --image=busybox --restart=Never -- sh -c "while true; do wget -q -O- http://app-hpa; done"

### Deletar
kubectl delete -f hpa.yaml
kubectl delete -f deployment-hpa.yaml
