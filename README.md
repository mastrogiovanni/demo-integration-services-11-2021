# Prerequisite


# Run

Install minikube, kubectl

```
git clone -b 289-improve-kubernetes-api-resiliency https://github.com/iotaledger/integration-services

cd integration-services

minikube start

kubectl apply -f kubernetes/optional/

kubectl apply -f kubernetes

minikube addons enable ingress
```

Wait that ingress is setup

```
$ kubectl get ingress
NAME                         CLASS    HOSTS                          ADDRESS        PORTS   AGE
integration-service-api      <none>   ensuresec.solutions.iota.org   192.168.49.2   80      13m
integration-service-others   <none>   ensuresec.solutions.iota.org   192.168.49.2   80      13m
```

Map in `/etc/hosts` the association `192.168.49.2` to hostname `ensuresec.solutions.iota.org`

You can see dashboard of running pod using:

`minikube dashboard`

# 

BASE_URL=http://ensuresec.solutions.iota.org/api/v1
API_KEY=94F5BA49-12B6-4E45-A487-BF91C442276D


