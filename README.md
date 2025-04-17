# GHLearning-Kubernetes-Helm

## Quickstart Guide
This guide covers how you can quickly get started using Helm.

## Prerequisites
The following prerequisites are required for a successful and properly secured use of Helm.

1. A Kubernetes cluster
2. Deciding what security configurations to apply to your installation, if any
3. Installing and configuring Helm.

## Install Kubernetes or have access to a cluster
- You must have Kubernetes installed. For the latest release of Helm, we recommend the latest stable release of Kubernetes, which in most cases is the second-latest minor release.
- You should also have a local configured copy of kubectl.

See the [Helm Version Support Policy](https://helm.sh/docs/topics/version_skew/) for the maximum version skew supported between Helm and Kubernetes.

## Install Helm
Download a binary release of the Helm client. You can use tools like homebrew, or look at [the official releases page](https://github.com/helm/helm/releases).

For more details, or for other options, see [the installation guide](https://helm.sh/docs/intro/install/).
### Homebrew
```
brew install helm
```

### Chocolatey
```
choco install kubernetes-helm
```

### Scoop
```
scoop install helm
```

### Snap
```
sudo snap install helm --classic
```

## Initialize a Helm Chart Repository
Once you have Helm ready, you can add a chart repository. Check Artifact Hub for available Helm chart repositories.
```
$ helm repo add bitnami https://charts.bitnami.com/bitnami
```

## Install an Example Chart
To install a chart, you can run the helm install command. Helm has several ways to find and install a chart, but the easiest is to use the bitnami charts.
```
$ helm repo update  
```

## Learn About Releases
It's easy to see what has been released using Helm:
```
$ helm list
```

## Uninstall a Release
To uninstall a release, use the helm uninstall command:
```
$ helm uninstall mysql-1612624192
```

## Reading the Help Text
```
$ helm get -h
```

