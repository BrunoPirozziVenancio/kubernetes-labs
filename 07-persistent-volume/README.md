# 07 - PersistentVolume e PersistentVolumeClaim

PersistentVolume (PV) e um recurso de armazenamento no cluster. PersistentVolumeClaim (PVC) e uma requisicao de armazenamento feita por um Pod.

## Arquivos

- pv.yaml: PersistentVolume de 1Gi usando hostPath
- pvc.yaml: PersistentVolumeClaim que solicita 1Gi do PV
- deployment-pvc.yaml: Deployment que monta o PVC no container

## Como aplicar

### Criar o PV
kubectl apply -f pv.yaml

### Criar o PVC
kubectl apply -f pvc.yaml

### Verificar se o PVC foi vinculado ao PV
kubectl get pv
kubectl get pvc

### Criar o Deployment
kubectl apply -f deployment-pvc.yaml

### Verificar os Pods
kubectl get pods

### Deletar
kubectl delete -f deployment-pvc.yaml
kubectl delete -f pvc.yaml
kubectl delete -f pv.yaml
