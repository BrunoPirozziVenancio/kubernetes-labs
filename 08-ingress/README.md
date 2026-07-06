# 08 - Ingress

Ingress e um recurso que gerencia o acesso externo aos servicos do cluster, permitindo roteamento HTTP baseado em host e path.

## Arquivo

- ingress.yaml: Ingress roteando trafego para dois servicos diferentes por path

## Regras de roteamento

- app.local/ : redireciona para o nginx-service na porta 80
- app.local/api : redireciona para o backend-service na porta 3000

## Pre-requisito

O Ingress Controller do Nginx precisa estar instalado no cluster.
Para instalar no Docker Desktop:

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml

## Como aplicar

kubectl apply -f ingress.yaml

## Verificar o Ingress

kubectl get ingress
kubectl describe ingress app-ingress

## Deletar

kubectl delete -f ingress.yaml
