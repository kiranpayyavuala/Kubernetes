# spring-boot-mongo + Rolling Update
------------------------------------

Clone code from github:
----------------------
Version 1
---------
```
    git clone https://github.com/kiranpayyavuala/Kubernetes.git
    cd Kubernetes/Spring-boot-Rollingupdate
    mvn clean install
    docker build -t kiranpayyavuala/mykubeimages:<version1> .
    docker push kiranpayyavuala/mykubeimages:<version1>
```    
Deployment Kubernetes SpringBoot + MongoDB Application
------------------------------------------------------
`````
    cd spring-boot-mongo

    kubectl create -f RollingDeployment/mongo-deployment.yml
    kubectl create -f RollingDeployment/mongo-service.yml
    kubectl apply -f RollingDeployment/Spring-Rolling-deployment.yml
    kubectl apply -f RollingDeployment/Spring-Service.yml
``````

Now Goto aws--> ec2--> Loadbalancer and get the DNS Name and check in browser 
                       or
      kubectl get service,pvc,deployment,pods

Version 2
---------
Modify the code and build

```
    mvn clean install
    docker build -t kiranpayyavuala/mykubeimages:<version2> .
    docker push kiranpayyavuala/mykubeimages:<version2>
    kubectl rollout history deployment spring-deployment
    kubectl rollout history deployment spring-deployment --revision=1
    kubectl set image deployment nodejs-deployment spring-deployment=kiranpayyavuala/mykubeimages:<version2>
```

Check Wheter the version 2 has been updated or not
```
kubectl rollout history deployment spring-deployment --revision=2
```
Revert the previous version
```
kubectl rollout undo deployment spring-deployment --to-revision=1
```
