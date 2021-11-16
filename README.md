# Prerequisite

* [minikube](https://v1-18.docs.kubernetes.io/docs/tasks/tools/install-minikube/)
* [kubectl](https://v1-18.docs.kubernetes.io/docs/tasks/tools/install-kubectl/)

# Setup

## Setup minikube (single node kubernetes cluster):

```
minikube start
minikube addons enable ingress
```

## Setup resources

```bash
git clone -b 289-improve-kubernetes-api-resiliency https://github.com/iotaledger/integration-services
cd integration-services
kubectl apply -f kubernetes/optional/
kubectl apply -f kubernetes
```

Wait that ingress is setup: you should have something like:

```
$ kubectl get ingress
NAME                         CLASS    HOSTS                          ADDRESS        PORTS   AGE
integration-service-api      <none>   ensuresec.solutions.iota.org   192.168.49.2   80      13m
integration-service-others   <none>   ensuresec.solutions.iota.org   192.168.49.2   80      13m
```

Map in `/etc/hosts` the association `192.168.49.2` to hostname `ensuresec.solutions.iota.org`

You can see dashboard of running pod using:

`minikube dashboard`

## Test endpoint

You can check if everything is up and running with the following:

```
curl http://ensuresec.solutions.iota.org/info
```

# Exercise

You can go and practice with the `clients/summer-school-client` to create credential and verifiable credentials.

You can use as configuration inside the project a `.env` file with the following:

```
BASE_URL=http://ensuresec.solutions.iota.org/api/v1
API_KEY=94F5BA49-12B6-4E45-A487-BF91C442276D
```

