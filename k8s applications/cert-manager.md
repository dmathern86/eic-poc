```
kubectl create namespace cert-manager
```
```
kubectl -n <namespace> create secret docker-registry application-collection --docker-server=dp.apps.rancher.io --docker-username=<yourUser> --docker-password=<yourPassword>
```
```
helm install cert-manager oci://dp.apps.rancher.io/charts/cert-manager \
--set crds.enabled=true \
--set-json 'global.imagePullSecrets=[{"name":"application-collection"}]' \
--namespace=cert-manager \
--version 1.15.2
```
