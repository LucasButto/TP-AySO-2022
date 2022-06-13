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

ONCE WE ENTER THE CONSOLE, WE CREATE THE FOLDER "nginx" TO WORK WITH IT <br>
<br>
---REMINDER--- <br>
TO CREATE A FOLDER YOU NEED TO USE THE COMMAND * mkdir "FolderName" * <br>

WE ARE ABLE TO FIND THE FOLDER FOLLOWING THE NEXT COMMANDS TO SEE THE PATH IN OUR SYSTEM <br>
pwd <br>
/home/juani <br>
cd nginx 

1) CREATE INDEX.HTML <br>
sudo vim index.html

2) CREATE DOCKERFILE <br>
sudo vim Dockerfile

3) ONCE WE HAVE THIS FILE, WE ARE ABLE TO BUILD AN IMAGE WITH THE TAG "V1" <br>
docker build --tag v1 .

4) CREATE A CONTAINER TO TEST TE IMAGE <br>
docker run -d -p 8080:80 --name grupo4 v1

5) ONCE THE CONTAINER IS CREATED, WE CAN TEST THE IMAGE WITH THE PORT IN THE POINT 3 INTO YOUR FAVOURITE <br>

6) ONCE THE DOCKERHUB USER IS CREATED <br>
docker tag v1:latest juanig99/grupo4-tup:v1

7) PUSH THE IMAGE ON DOCKERHUB, WE CAN NOW DEFINE THE TAG <br>
docker push juanig99/grupo4-tup:v1

8) CREATE .YAML FILE <br>
vim docker-prueba.yaml

9) CREATE THE K8S CLUSTER <br>
minikube start --driver=docker

10) CREATE THE ALIAS OF KUBECTL, NOW MINIKUBE RECOGNIZE THE KUBECTL COMMAND <br>
alias kubectl="minikube kubectl --"

11) CREATE NAMESPACE <br>
kubectl create ns grupo4

12) APPLY CHANGES <br>
kubectl apply -f docker-prueba.yaml

13) CHECK THE STATUS OF THE REPLICASET BY OPENING THE DASHBOARD <br>
minikube dashboard


#=============== Collaborators: =============== <br>
-Garnero Juan Ignacio  | https://github.com/juaanig  <br>
-Butto Lucas           | https://github.com/LucasButto <br>
-Bórtoli Gastón	       | https://github.com/Bortoli94 <br>
-Mule Francisco	       | https://github.com/franmux01 <br>
-Kraus Herman          | https://github.com/hermankraus <br>
#==============================================
