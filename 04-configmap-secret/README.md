# 04 - ConfigMap e Secret

ConfigMap armazena configuracoes nao sensiveis. Secret armazena dados sensiveis como senhas e tokens, em base64.

## Arquivos

- **configmap.yaml** — Variaveis de configuracao da aplicacao
- **secret.yaml** — Credenciais do banco de dados em base64

## Como codificar em base64

echo -n "minha-senha" | base64

## Como aplicar

### Criar o ConfigMap
kubectl apply -f configmap.yaml

### Criar o Secret
kubectl apply -f secret.yaml

### Verificar o ConfigMap
kubectl get configmap app-config

### Ver os dados do ConfigMap
kubectl describe configmap app-config

### Verificar o Secret
kubectl get secret app-secret

### Deletar
kubectl delete -f configmap.yaml
kubectl delete -f secret.yaml
