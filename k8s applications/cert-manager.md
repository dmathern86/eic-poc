```
kubectl create namespace cert-manager
```
```
helm install cert-manager oci://dp.apps.rancher.io/charts/cert-manager \
--set crds.enabled=true \
--set-json 'global.imagePullSecrets=[{"name":"application-collection"}]' \
--namespace=cert-manager \
--version 1.15.2
```
