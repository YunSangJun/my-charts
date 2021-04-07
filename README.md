# my-charts

## Add helm chart repository to your environment

```
$ helm repo add my-charts https://yunsangjun.github.io/my-charts/stable
```

## Confirm the repository

```
$ help repo list
NAME     	URL                                                       
...                                     
my-charts	https://yunsangjun.github.io/my-charts/stable
```

## Search charts in the repository

```
$ helm search repo my-charts
NAME          	CHART VERSION	APP VERSION	DESCRIPTION                
my-charts/demo	0.1.0        	1.0        	A Helm chart for Kubernetes
```

## Using the chart

```
$ helm install my-charts/demo
NAME:   flippant-narwhal
LAST DEPLOYED: Wed Oct  3 15:11:52 2018
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1beta2/Deployment
NAME                   AGE
flippant-narwhal-demo  0s

==> v1/Pod(related)

NAME                                    READY  STATUS             RESTARTS  AGE
flippant-narwhal-demo-54dd9c69f8-b77dz  0/1    ContainerCreating  0         0s

==> v1/Service

NAME                   AGE
flippant-narwhal-demo  0s


NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=demo,app.kubernetes.io/instance=flippant-narwhal" -o jsonpath="{.items[0].metadata.name}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl port-forward $POD_NAME 8080:80
```
