# Install heml in local

# Install Tiller in kubernetes
```
kubectl -n kube-system create sa tiller
kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller
```

# helm cheating sheet
```
helm list -a (get release-name)
helm get values release-name
helm delete release-name
helm delete --purge release-name
```

# Install filebeat
```
helm install --name elastic-search -f filebeat-heml.yaml stable/filebeat
kubectl --namespace=default get pods -l "app=filebeat,release=release-name"
```

# Install metricbeat
```
helm install --name elastic-metric -f metricbeat-helm.yaml stable/metricbeat
kubectl --namespace=default get pods -l "app=metricbeat,release=elastic-metric"
```
