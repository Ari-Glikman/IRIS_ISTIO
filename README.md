## These Yamls are for the purpose of understanding the InterSystems Community article: "Getting Started Using Istio Service Mesh with Mirrored IRIS Environment in Kubernetes"
Note that this is part of an internal contest and the article may not be available for the public yet.

How to use:

1. Make sure you have a Kubernetes Cluster available
2. In terminal with kubectl config set to your cluster:
  > kubectl create secret docker-registry intersystems-pull-secret --docker-server=https://containers.intersystems.com --docker-username='yourUsername' --docker-password='yourPassword' --docker-email='yourEmail'
 

  > kubectl create secret generic iris-key-secret --from-file=iris.key

**note that you will need a key to do this.**

  > helm install intersystems iris_operator_amd-3.7.13.100/chart/iris-operator

**See here if you are having problems: https://community.intersystems.com/post/iko-lessons-learned-part-1-helm**
  
  > kubectl create cm iris-cpf --from-file common.cpf

**See here if you are having problems: https://community.intersystems.com/post/iko-lessons-learned-part-2-iriscluster**
  
  > kubectl create secret generic iris-webgateway-secret --from-literal='username=CSPSystem' --from-literal='password=yourPassword'
  
  > kubectl apply -f yourIrisCluster.yaml



The following are diagrams to help understand the yamls in a more illustrative form:

### **irisSimple.yaml**
![image](https://github.com/user-attachments/assets/9090f5b7-f123-4f58-a38a-b4fa70a5a33a)

---------------------------------------------------------------------------------------------

### **irisSimpleSidecCar.yaml**
![image](https://github.com/user-attachments/assets/196315c2-1165-456b-841b-6bcf8f838f88)

---------------------------------------------------------------------------------------------

### **irisMirrorSideCar.yaml**
![image](https://github.com/user-attachments/assets/c7a54b7a-cfcb-46d6-8cf3-83430cacf915)

