# my-charts

## Add helm chart repository to your environment

```
$ helm repo add my-charts https://yunsangjun.github.io/my-charts/stable
$ helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "my-charts" chart repository
Update Complete. ⎈Happy Helming!⎈
```

## Confirm the repository

```
$ helm repo list
NAME     	URL                                                       
...                                     
my-charts	https://yunsangjun.github.io/my-charts/stable
```

## Search charts in the repository

```
$ helm search repo my-charts
NAME            CHART VERSION   APP VERSION     DESCRIPTION
my-charts/demo  0.1.0           1.16.0          A Helm chart for Kubernetes
```

## Using the chart

```
$ helm install demo my-charts/demo
NAME: demo
LAST DEPLOYED: Mon Jan 17 23:09:00 2022
NAMESPACE: hclouddemo
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace hclouddemo -l "app.kubernetes.io/name=demo,app.kubernetes.io/instance=demo" -o jsonpath="{.items[0].metadata.name}")
  export CONTAINER_PORT=$(kubectl get pod --namespace hclouddemo $POD_NAME -o jsonpath="{.spec.containers[0].ports[0].containerPort}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl --namespace hclouddemo port-forward $POD_NAME 8080:$CONTAINER_PORT
```
