# kind

## Installing With A Package Manager

On macOS via Homebrew:
```
brew install kind
```

On macOS via MacPorts:
```
sudo port selfupdate && sudo port install kind
```

On Windows via Chocolatey (https://chocolatey.org/packages/kind)
```
choco install kind
```

On Windows via Scoop (https://scoop.sh/#/apps?q=kind&id=faec311bb7c6b4a174169c8c02358c74a78a10c2)
```
scoop bucket add main
scoop install main/kind
```

On Windows via Winget (https://github.com/microsoft/winget-pkgs/tree/master/manifests/k/Kubernetes/kind)
```
winget install Kubernetes.kind
```


## Creating a Cluster

### create
```
kind create cluster --config kind-example-config.yaml
```
### get
```
kind get clusters
```

### delete
```
kind delete cluster
```

## Configuration
### kind-example-config.yaml
```
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
  - containerPort: 443
    hostPort: 443
    protocol: TCP
- role: worker
- role: worker
- role: worker
```
