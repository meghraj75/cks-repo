created nginx Ingress
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml

now create two services that route traffic to pod1 and pod 2

service 1 ---->pod 1

service 2 ---> pod 2 


-----------------

kubectl run pod1 --image=httpd  

kubectl run pod2 --image=httpd  

kubectl expose pod pod1 --port 80 --name service1

kubectl expose pod pod2 --port 80 --name service2

kubectl apply -f .\ingress.yml

kubectl run test --rm -it --image=busybox -- sh

bcz we running busy box inside k8 cluster 

wget -qO- http://service1

wget -qO- http://service2

-------------------------------------------------------------------------------

Implementing tls 

