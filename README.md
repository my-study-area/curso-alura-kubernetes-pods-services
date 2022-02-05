# curso-alura-kubernetes-pods-services
Curso de Kubernetes: Pods, Services e ConfigMaps

## Inicializa aplicação
```bash
# inicializa o node
minikube start --vm-driver=virtualbox

# removes os pods, configmaps e svc
kubectl delete pod --all
kubectl delete configmap --all
kubectl delete svc --all

# inicializa a aplicação
kubectl apply -f db-configmap.yaml
kubectl apply -f portal-configmap.yaml
kubectl apply -f sistema-configmap.yaml

kubectl apply -f portal-noticias.yaml
kubectl apply -f sistema-noticias.yaml
kubectl apply -f db-noticias.yaml

kubectl apply -f svc-db-noticias.yaml
kubectl apply -f svc-portal-noticias.yaml
kubectl apply -f svc-sistema-noticias.yaml
```

## Anotações
```
# inicia um cluster kubernetes
minikube start --vm-driver=virtualbox

# exibe a versão do client
kubectl version --client

# exibe os nodes
kubectl get nodes

# cria um pod
kubectl run nginx-pod --image=nginx:latest

# lista os pods
kubectl get pods

# lista os pods assistindo as modificações
kubectl get pods --watch

# mostra os detalhes do pod nginx-pod
kubectl describe pod nginx-pod

# edita as propriedade de um pod
kubectl edit pod nginx-pod

# cria um pod declarativo
kubectl apply -f ./primeiro-pod.yaml

# deleta pod nginx-pod
kubectl delete pod nginx-pod

# deleta pod declarativamente
kubectl delete -f ./primeiro-pod.yaml

#
kubectl apply -f ./portal-noticias.yaml

# acessa terminal
kubectl exec -it portal-noticias -- bash

# lista os pods no formato wide
kubectl get pods -o wide

# lista os services
kubectl get svc

# removes todos os pods
kubectl delete pods --all

# removes todos os services
kubectl delete services --all

# instala ping dentro do container
apt-get update && apt-get install -y iputils-ping

# instala mysqlclient no container
apt-get install -y default-mysql-client
```

Exemplo de arquivo declarativo de um pod:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: primeiro-pod-declarativo
spec:
  containers:
    - name: nginx-container
      image: nginx:stable

```
- [referência para pods](https://kubernetes.io/docs/reference/kubernetes-api/workload-resources/pod-v1/)

- [referência para services](https://kubernetes.io/docs/reference/kubernetes-api/service-resources/)
