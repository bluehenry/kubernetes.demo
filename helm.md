#Install heml in local

#Install Tiller in kubernetes
kubectl -n kube-system create sa tiller
kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller

#Install filebeat
helm install --name elastic-search -f filebeat.yaml stable/filebeat

kubectl --namespace=default get pods -l "app=filebeat,release=release-name"

#helm cheating sheet
helm list -a (get release-name)
helm get values release-name
helm delete release-name
