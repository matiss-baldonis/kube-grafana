# kube-grafana
Launch Graphana locally + argocd application
## Add repository to argocd
### Add this repositories URL and git key to ArgoCD
```  argocd repo add git@github.com:matiss-baldonis/kube-grafana --ssh-private-key-path ~/.ssh/id_ed25519 ```

### Launch ArgoCD pipeline from manifests/setup/grafana/application/grafana
### by deploying a Kubernetes grafana instance. 
```  kubectl apply -f grafana.yaml ```
### ArgoCD will launch deployment and deploy all neccessary kubernetes manifests in this repository.

### Forward ports to make Grafana available in browser
```
kubectl port-forward service/grafana 3000:3000 --namespace=grafana
```

### Open Grafana in browser:

``` localhost:3000 ```

### TODO:
```- Implement ingress so that Grafana can be accessed via DNS name that points to k8s service```
