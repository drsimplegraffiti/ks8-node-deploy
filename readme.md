
On your Docker desktop enable the Kubernetes

> npm init -y

> npm i express

> touch .dockignore Dockerfile docker-compose.yml

> docker compose up

#### To use kubernetes ensure that the kubernetes is enabled on your docker desktop


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/heu2q1li57pf9zdjt164.png)


#### Rebuild image
> docker compose build

#### start minikube
> minikube start --driver=docker

#### Check the deployment
> kubectl get deployment

#### Create deployment
> kubectl apply -f deployment.yml

#### Check the deployment
> kubectl get deployment


#### check in describe
> kubectl describe deployment



#### check pods
> kubectl get pods

#### Delete all deployments
> kubectl delete deployment --all

#### Delete all pods
> kubectl delete pods --all

#### Delete all services
> kubectl delete services --all


#### stop minikube
> minikube stop

#### inspect the pod
> kubectl describe pod <pod-name>
> kubectl describe pod myapp-57d878494d-mbht2

#### in case you get the error:
ErrImageNeverPull

type the following command
> eval $(minikube docker-env)
then rebuild the image : docker compose build
then apply the deployment : kubectl apply -f deployment.yml

#### Create service
```service.yml
apiVersion: v1
kind: Service
metadata:
  name: myapp
spec:
  selector:
    app: myapp
  ports:
    - port: 80
      targetPort: 3000
  type: LoadBalancer
```

#### Apply service
> kubectl apply -f service.yml

#### Check service
> kubectl get services



#### if you are getting <pending> in the external ip column, type the following command
> minikube tunnel --cleanup

#### check the service
> kubectl get services

<!-- ##### resolving issues: use powershell as admin
> Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All

> minikube config set driver hyperv

> minikube stop  -->