# kubectl 

## install
### linux 
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```

## pods

### get info
```bash
kubectl describe all
```

```bash
# get backend endpoints
kubectl get endpoints
```