# curso-alura-kubernetes-pods-services
Curso de Kubernetes: Pods, Services e ConfigMaps

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

```
