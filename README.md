# Flapi - CertManager Cluster K3s

## ⚙ Setup Environment
1. Connect to the NODE MASTER in Cluster K3S.
2. Install HELM : https://helm.sh/docs/intro/install/
3. Use repo CERT-MANAGER HELM : https://artifacthub.io/packages/helm/cert-manager/cert-manager
4. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo helm repo add jetstack https://charts.jetstack.io
sudo helm repo update
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --version v1.16.2 --set crds.enabled=true --values values.yaml
sudo kubectl apply -f cluster-issuer.yaml
```

<br /><br /><br /><br />


## 🚀 Update chart CertManager HELM for values.yaml
1. Connect to the NODE MASTER in Cluster K3S.
2. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm upgrade cert-manager jetstack/cert-manager --namespace cert-manager --values values.yaml
```
