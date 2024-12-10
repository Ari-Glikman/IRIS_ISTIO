## These Yamls are for the purpose of understanding the InterSystems Community article: "Getting Started Using Istio Service Mesh with Mirrored IRIS Environment in Kubernetes"

How to use:

1. Make sure you have a Kubernetes Cluster available
2. In terminal with kubectl config set to your cluster:
  > kubectl create secret docker-registry intersystems-pull-secret --docker-server=https://containers.intersystems.com --docker-username='<your username>' --docker-password='<your password>' --docker-email='<your password>'
 

  > kubectl create secret generic iris-key-secret --from-file=iris.key

** note that you will need a key to do this.**

  > helm install intersystems iris_operator_amd-3.7.13.100/chart/iris-operator

** See here if you are having problems: https://community.intersystems.com/post/iko-lessons-learned-part-1-helm**
  
  > kubectl create cm iris-cpf --from-file common.cpf

** See here if you are having problems: https://community.intersystems.com/post/iko-lessons-learned-part-2-iriscluster**
  
  > kubectl create secret generic iris-webgateway-secret --from-literal='username=CSPSystem' --from-literal='password=yourpassword'
  
  > kubectl apply -f yourIrisCluster.yaml



