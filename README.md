# kubernetes-elastic-logging  
## Elastic stack deployment on K8S  

###### Get all list of all namespaces available in cluster
>kubectl get ns  

###### Change directory to elk
>cd .\elk  

###### List all current available pods in namespace 'kube-system'  
>kubectl get pods -n kube-system  

## Deploy Elasticsearch  
>kubectl apply -f elasticsearch-ss.yaml  

###### Verify Elasticsearch deployment  
>kubectl get pods -n kube-system  
>kubectl describe pod [ELASTICSEARCH_PODNAME] -n kube-system  
>kubectl logs [ELASTICSEARCH_PODNAME] -n kube-system  

## Deploy Logstash  
>kubectl apply -f logstash-deployment.yaml  

###### Verify Logstash deployment  
>kubectl get pods -n kube-system  
>kubectl describe pod [LOGSTASH_PODNAME] -n kube-system  
>kubectl logs [LOGSTASH_PODNAME] -n kube-system  

## Deploy Filebeat  
>kubectl apply -f filebeat-ds.yaml  

###### Verify Filebeat deployment  
>kubectl get pods -n kube-system  
>kubectl describe pod [FILEBEAT_PODNAME] -n kube-system  
>kubectl logs [FILEBEAT_PODNAME] -n kube-system  

## Deploy Metricbeat  
>kubectl apply -f metricbeat-ds.yaml  

###### Verify Metricbeat deployment  
>kubectl get pods -n kube-system  
>kubectl describe pod [METRICBEAT_PODNAME] -n kube-system  
>kubectl logs [METRICBEAT_PODNAME] -n kube-system  

## Deploy Kibana  
>kubectl apply -f kibana-deployment.yaml  

###### Verify kibana deployment  
>kubectl get pods -n kube-system  
>kubectl describe pod [KIBANA_PODNAME] -n kube-system  
>kubectl logs [KIBANA_PODNAME] -n kube-system  

## Deploy Curator CronJob  
>kubectl apply -f curator-cronjob.yaml  

###### Verify kibana deployment  
>kubectl get cronjobs -n kube-system  
>kubectl describe cronjob [KIBANA_CRONAME] -n kube-system  
>kubectl logs [KIBANA_CRONNAME] -n kube-system  

## Deploy Example App  

###### Create example-app namespace  
>kubectl create ns example-app  

###### lets create some resources.  
>kubectl apply -n example-app -f secrets/secret.yaml  
>kubectl apply -n example-app -f configmaps/configmap.yaml  
>kubectl apply -n example-app -f deployments/deployment.yaml  

###### remember to change the `type: LoadBalancer`  
>kubectl apply -n example-app -f services/service.yaml  
