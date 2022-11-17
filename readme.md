# Atividade - Aula 5

Subir dois pods, nginx e mysql, mapeando a porta 80 do nginx para acesso externo ao cluster e permitir que o contêiner do nginx tenha comunicação de rede no contêiner mysql pela porta 3306.
A atividade pode ser feita localmente (minikube/Docker Desktop), AKS (Azure), EKS (AWS) ou no GKE (GCP).

Se quiser criar o cluster Kubernetes com Terraform é opcional.
Enviar os arquivos yaml pelo GitHub.
O código enviado deve satisfazer exatamente o que foi pedido no enunciado, caso haja código faltando ou sobrando terá desconto de nota.

## Lista de comandos a serem executado para obter o resultado:

**Observação:** Estou utilizando um cluster instalado localmente(minikube).

```sh
kubectl create -f deployments/mysql-dp.yml --save-config
kubectl create -f services/mysql-svc.yaml --save-config

kubectl create -f deployments/frontend-dp.yml --save-config
kubectl create -f services/frontend-svc.yaml --save-config


kubectl get all -n development

minikube tunnel
minikube service frontend-svc
```
