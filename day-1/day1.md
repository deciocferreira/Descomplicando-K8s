<h1> Hands-on Kubernetes ☸️ </h1> 

- Instalação Kubectl (API de conexão ao Kubernetes)
- Instalação Kind(kubernetes in Docker) no GNU/Linux
- Criação de um Cluster com 1 Control-plane e 2 Workers
- Criação de um Pod com imagem do Nginx (manifesto arquivo yaml)
- Exposição do Pod
- Execução de comandos padrão do Kubectl referentes a administração do Cluster K8s
- Deleção dos recursos criados

## Instalação Kubectl

~~~~
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version --client
~~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/c58a28d5-a752-43a1-a792-caeb33ea3e9b" width="900" height="120"> </p>

## Instalação do Kind no Linux (Ubuntu 20.04)

Execução dos seguintes comandos:
~~~
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64

chmod +x ./kind

sudo mv ./kind /usr/local/bin/kind
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/aa2e59d8-0824-4a5e-9db6-7ea40f40a30d" width="500" height="90"> </p>

## Criação de um Cluster personalizado com múltiplos nós locais (arquivo manifesto yaml)

Execução dos seguintes comandos:

- Criar arquivo .yaml com definições do Cluster dentro do diretório correspondente

~~~~
vim k8s-cluster
~~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/c749b447-ccf6-4724-8b2f-66e9fda6ad2a" width="500" height="250"> </p>

- Criação do Cluster
~~~
Kind create Cluster --name main --config k8s-cluster.yaml
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/3b21bc86-7861-4e5e-b814-483ea033a1c5" width="850" height="400"> </p>

## Criação e execução de um Pod com imagem do Nginx (manifesto arquivo yaml)

~~~
kubectl run pod-nginx --image deciocferreira/nginx --dry-run=client -o yaml > pod-template.yaml
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/e09bc690-4db5-425b-8824-9d2d8ae526c5" width="850" height="400"> </p>

~~~
kubectl apply -f pod-template.yaml
~~~

<p align="left"> <image src="https://github.com/deciocferreira/Descomplicando-K8s/assets/12403699/50ca62fc-9120-492f-9984-1780e7a64628" width="800" height="200"> </p>

## Expor o pod



## Resultado esperado
Até aqui é esperado que o conhecimento esteja mais fixado em como é composta a aquitetura do K8s e como é utilizada a API do K8s *Kubectl* para criação e manipulação de recursos dentro do Cluster.
