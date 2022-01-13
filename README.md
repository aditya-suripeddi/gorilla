# Deploy a Spring Boot App on Minikube Locally 

The aim of this repository is to get started with kubernetes
by deploying a hello world spring boot app named gorilla


### Result

Kubectl commands were used to create a service on minikube


### Next: 

Understand and use [kubernetes yaml files](https://www.youtube.com/watch?v=7o7e8OAAWyg) for deployment


### Steps:

1.  Install minikube 

    [curl script](https://minikube.sigs.k8s.io/docs/start/) 

    minikube has its own docker daemon / engine 
    you have to use THIS to create container images 
    and make services out of them. You do that by

    ```bash
      $ minikube start

      $ eval $( minikube docker-env )
    ```

     in this shell environment docker refers minikube's docker engine
     and not the docker engine that you may have installed


3. Create image from root folder of project

   ```bash
   /path/to/gorilla$ docker build -t image-name . 
   $ kubectl create deployment deploy-name --image=image-name
   $ kubect get edit deployment deploy-name # set imagePullPolicy: Never  
   $ kubectl port-forward service/sname 8080:8080
   ```

5. Hit the [endpoint](http://localhost:8080/hello) from browser



### References: 


1. [stackoverflow link](https://stackoverflow.com/a/66598466)


2. [spring-on-kubernetes-topical-guide](https://spring.io/guides/topicals/spring-on-kubernetes/)

3. [spring-boot-docker-topical-guide](https://spring.io/guides/topicals/spring-boot-docker/)

4. [Kubernetes labs](https://labs.play-with-k8s.com/)

5. [how-to-deploy-dockerized-app-to-kubernetes](https://medium.com/@sarathtchander/how-to-deploy-dockerized-spring-boot-app-in-k8s-minikube-for-beginners-378a1b0df153)

6. [spring-boot-apps-with-minikube-baeldung](https://www.baeldung.com/spring-boot-minikube?__cf_chl_tk=VCvE1u0lEkyeKZktAeYlQ__9UlWl6WNX6CV5EajGECg-1638361741-0-gaNycGzNCJE)


8. [edit-deployment-imagepullpolicy-never](https://www.talkingdotnet.com/how-to-run-locally-build-docker-images-with-kubernetes/)

7. [minikube-and-docker-common-registry](https://www.bogotobogo.com/DevOps/Docker/Docker_Kubernetes_Minikube.php)
