<h1> Prática Day-1 no Kubernetes</h1> 

- Instalação Kind(kubernetes in Docker) no GNU/Linux
- Criação de um Cluster com 1 Control-plane e dois Workers
- Criação de um Pod com imagem do Nginx
- Criação de um template de um Pod
- Exposição do Pod 
- Deleção dos recursos criado

## Instalação do Kind no Linux (Ubuntu 20.04)

Execute os seguintes comandos:
~~~
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64

chmod +x ./kind

sudo mv ./kind /usr/local/bin/kind
~~~

## Criação de um Cluster com Kind

Execute os seguintes comandos:

~~~
Kind create Cluster
~~~

## Resultado esperado
Até aqui é esperado que o conhecimento esteja mais fixado em como é composta a aquitetura do K8s e como é utilizada a API do K8s *Kubectl* para criação e manipulação de recursos dentro do Cluster.
