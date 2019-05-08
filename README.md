# kubernetes.demo
kubernetes demo, cheat sheet, helm etc.

# Cheat sheet
## Get something
```bash
kubectl get all --all-namespaces
kubectl get namespaces
kubectl get nodes 
kubectl get all -n namespace_name
kubectl get deployment -n namespace_name
kubectl get svc --all-namespaces
kubectl get pods
kubectl get pods -l "release=metricbeat"
```

## Troubleshooting with kubectl
### kubectl get - list resources
### kubectl describe - show detailed information about a resource
### kubectl logs - print the logs from a container in a pod
```
kubectl logs pod-name
```
### kubectl exec - execute a command on a container in a pod
Getting a shell to a Container
```
kubectl exec -it pod-name -- /bin/bash
```


#Helm
(Helm)[https://helm.sh/] helps you manage Kubernetes applications.
## Install heml in local
## Install Tiller in kubernetes
```bash
kubectl -n kube-system create sa tiller
kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller
```
##
* Install filebeat
```bash
helm install --name elastic-search -f filebeat.yaml stable/filebeat
```
