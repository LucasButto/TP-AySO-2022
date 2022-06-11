# TP-AySO-2022
Requirements:
-------------

	>Crear k8s cluster con minikube k3s o kind.
	>Crear dockerfile con nginx y donde copie un index.html diga “Hola mundo, somos el grupo 4 de la UTN”.
	>Buildear y pushear dicha imagen con el tag v1 a hub.docker.com
	>Crear namespace que se llame grupo4
	>Crear un Replicaset in kubernetes en el ns que se creo anteriormente: Requisitos, debe tener 2 replicas, y debe levantar la imagen de nginx previa.
	>Subir todo el codigo a github.
	>Crear README.

Tips:
-----
	>No olvidar .gitignore y .dockerignore files .
	>Usar imagenes alpine o stables.
	>Probar todo local antes de pushear a git.


INTRODUCTION

0) ONCE WE ENTER THE CONSOLE, WE GO TO THE FOLDER TO WORK WITH

pwd 
/home/juani
cd nginx

1) CREATE INDEX.HTML
sudo vim index.html

2) CREATE DOCKERFILE
sudo vim.Dockerfile
A partir de este archivo buildeamos una imagen con el tag "v1"
docker build --tag v1 .

3) CREATE A CONTAINER TO TEST TE IMAGE
docker run -d -p 8080:80 --name grupo4 v1

4) ONCE THE CONTAINER IS CREATED, WE CAN TEST THE IMAGE WITH THE PORT IN THE POINT 3 INTO YOUR FAVOURITE

5) ONCE THE DOCKERHUB USER IS CREATED 
docker tag v1:latest juanig99/grupo4-tup:v1

6) PUSH THE IMAGE ON DOCKERHUB, WE CAN NOW DEFINE THE TAG
docker push juanig99/grupo4-tup:v1

7) CREATE .YAML FILE
vim docker-prueba.yaml

8) CREATE THE K8S CLUSTER
minikube start --driver=docker

9) CREATE THE ALIAS OF KUBECTL, NOW MINIKUBE RECOGNIZE THE KUBECTL COMMAND
alias kubectl="minikube kubectl --"

10) CREATE NAMESPACE
kubectl create ns grupo4

11) APPLY CHANGES 
kubectl apply -f docker-prueba.yaml

12) CHECK THE STATUS OF THE REPLICASET BY OPENING THE DASHBOARD
minikube dashboard


#=============== Collaborators: ===============
-Bortoli Gastón        | https://github.com/juaanig 
-Butto Lucas           | https://github.com/LucasButto
-Garnero Juan Ignacio  | https://github.com/Bortoli94
-Mule Francisco	       | https://github.com/franmux01
-Kraus Herman          | https://github.com/hermankraus
#==============================================
