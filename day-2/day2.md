<h1> Hands-on Kubernetes ☸️ </h1> 

- Execução dos comandos kubectl get pods/kubectl describe pods 
- Criação e execução de um Pod (arquivo manifesto yaml) 
- Execução do comando kubectl logs para monitorar pods
- Criação e execução de um Pod multicontainer (arquivo manifesto yaml) 
- Execução dos comandos kubectl attach/kubectl exec
- Limitando o uso de CPU e Memória do Pod
- Configurando um volume EmptyDir

## kubectl get pods/kubectl describe pods 

~~~
kubectl get pods

kubectl describe pods pod-nginx
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/a0b7ae17-aaa1-4d8c-9b09-1af54ef6faa2" width="800" height="500"> </p>

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/73b4205a-c90b-4ad6-bb04-a30a0ab985d8" width="800" height="500"> </p>

## Criação e execução de um Pod (arquivo manifesto yaml) 

~~~
vi pod-nginx.yaml

kubectl apply -f pod-nginx.yaml

kubectl get pods
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/c73b606f-3bb7-4869-8532-2f7e252c67ae" width="800" height="500"> </p>

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/92c88464-40c1-4e8e-a82d-87a9d575816a" width="800" height="500"> </p>

## kubectl logs 

~~~
kubectl logs podnginx

kubectl logs -f podnginx (logs em tempo real)
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/02c6e9f8-d618-4403-ac07-b69f79752b26" width="800" height="500"> </p>

## Criação e execução de um Pod multicontainer (arquivo manifesto yaml)

~~~
vi pod-multicontainer.yaml

kubectl apply -f pod-multicontainer.yaml

kubectl get pods

kubectl describe pods podnginx
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/a7203857-8470-436d-9f1b-c066c5eae8ef" width="800" height="500"> </p> 

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/4f0cbedd-b076-468d-9d0b-8af121acbb5b" width="800" height="500"> </p> 

- Execução dos comandos kubectl attach/kubectl exec

~~~
kubectl attach podnginx -c podnginx

kubectl attach podnginx -c podprometheus

kubectl exec podnginx -c podnginx -- ls

kubectl exec podnginx -c podprometheus -it sh
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/b479bae3-47af-4d9f-9177-81f5bc063354" width="800" height="500"> </p> 

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/f466ec14-e519-49aa-bd71-b2f81dc8ab3b" width="800" height="500"> </p> 

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/3c092c9b-7547-4b08-a3d9-8a0cbb5ad22a" width="800" height="500"> </p> 

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/9b60bbaa-8d31-499b-a370-8123a7153809" width="800" height="500"> </p> 

## Limitando o uso de CPU e Memória de um Pod

~~~
vu pod-recursolimitado.yaml

kubectl apply -f podrecursolimitado.yaml

kubectl exec podnginx -c podnginx -- ls

kubectl exec podnginx -c podprometheus -it sh
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/73c57cd0-84bc-4866-ab3a-2ab844cdd953" width="800" height="500"> </p> 



  
## Resultado esperado
Até aqui é esperado que o conhecimento esteja mais fixado na criação de pods, interpretação de arquivos manifestaos(yaml) para criar pods com limitações de recursos, pods multicontainers e pods com volumes nos containers dentro do Cluster.
