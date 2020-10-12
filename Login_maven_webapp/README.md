Clone code from github:
----------------------
    git clone https://github.com/kiranpayyavuala/Kubernetes.git
    cd Login_maven_webapp
    
Deployment Kubernetes Tomcat web Application
--------------------------------------------
    kubectl apply -f Deployment/Tomcat-Deployment.yml
    kubectl apply -f Deployment/Tomcat-LoadBalancer.yml
    
Now Goto aws--> ec2--> Loadbalancer and get the DNS Name and check in browser 

    <Loadbalancer>/LoginPage
