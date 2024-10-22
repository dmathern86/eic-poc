# Installing RKE2
To install RKE2, the script provided at https://get.rke2.io can be used as follows:
```
curl -sfL https://get.rke2.io | INSTALL_RKE2_VERSION=v1.28.13-rke2r1 sh
```
```
mkdir -p /etc/rancher/rke2
cat <<EOF > /etc/rancher/rke2/config.yaml
token: 'your cluster token'
system-default-registry: registry.rancher.com
tls-san:
  - FQDN of fixed registration address on load balancer
  - other hostname
  - IP v4 address
EOF
```

```
systemctl enable rke2-server --now
```

```
/var/lib/rancher/rke2/bin/kubectl --kubeconfig /etc/rancher/rke2/rke2.yaml get nodes
```

```
export PATH=$PATH:/var/lib/rancher/rke2/bin/
export KUBECONFIG=/etc/rancher/rke2/rke2.yaml
```
# Installing Helm
To install Rancher Prime and some of its required components, you need to use Helm.
One way to install Helm is to run:
```
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```
