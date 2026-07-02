# 06 - Liveness e Readiness Probes

Probes sao verificacoes de saude que o Kubernetes faz nos containers para saber se estao funcionando corretamente.

## Tipos de Probe

Liveness Probe: verifica se o container esta vivo. Se falhar, o Kubernetes reinicia o container.

Readiness Probe: verifica se o container esta pronto para receber trafego. Se falhar, o Kubernetes remove o Pod do balanceamento de carga sem reinicia-lo.

## Arquivo

- deployment-probes.yaml: Deployment com Liveness e Readiness Probes configurados

## Como aplicar

kubectl apply -f deployment-probes.yaml

## Verificar status das probes

kubectl get pods
kubectl describe pod NOME_DO_POD

## Ver eventos do Pod

kubectl describe pod NOME_DO_POD | grep -A 10 Events

## Deletar

kubectl delete -f deployment-probes.yaml
