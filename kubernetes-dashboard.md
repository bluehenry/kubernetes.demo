# Kubernetes Dashboard

[Kubenetes Dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)
[How to sign in Kubernetes Dashboard](https://stackoverflow.com/questions/46664104/how-to-sign-in-kubernetes-dashboard)

* Deploying the Dashboard UI
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/aio/deploy/recommended/kubernetes-dashboard.yaml
```

* Get Dashboard token
```
kubectl -n kube-system describe secret 
```

* Access the Dashboard UI
```
kubectl proxy
```
Kubectl will make Dashboard available at http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/.
