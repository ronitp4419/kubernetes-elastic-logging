# kubernetes-elastic-logging
## Elastic stack deployment on K8S

###### Create example-app namespace
>kubectl create ns example-app

###### lets create some resources.
>kubectl apply -n example-app -f secrets/secret.yaml
>kubectl apply -n example-app -f configmaps/configmap.yaml
>kubectl apply -n example-app -f deployments/deployment.yaml

###### remember to change the `type: LoadBalancer`
>kubectl apply -n example-app -f services/service.yaml
