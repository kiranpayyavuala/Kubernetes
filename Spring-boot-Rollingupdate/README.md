# spring-boot-mongo
-------------------

Clone code from github:
-------
    git clone https://github.com/kiranpayyavuala/Kubernetes.git
    cd Kubernetes/
    mvn clean install
    docker build -t kiranpayyavuala/mykubeimages:<version1> .
    docker push kiranpayyavuala/mykubeimages:<version1>
    
Deployment Kubernetes SpringBoot + MongoDB Application
------
    cd spring-boot-mongo

    kubectl create -f mongo-deployment.yml
    kubectl create -f mongo-service.yml
    kubectl apply -f spring-deployment.yml
    kubectl apply -f spring-service.yml
    
    
Now Goto aws--> ec2--> Loadbalancer and get the DNS Name and check in browser 
