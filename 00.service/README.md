# Kubernetes Service

## Service
Expose an application running in your cluster behind a single outward-facing endpoint, even when the workload is split across multiple backends.
In Kubernetes, a Service is a method for exposing a network application that is running as one or more Pods in your cluster.

A key aim of Services in Kubernetes is that you don't need to modify your existing application to use an unfamiliar service discovery mechanism. You can run code in Pods, whether this is a code designed for a cloud-native world, or an older app you've containerized. You use a Service to make that set of Pods available on the network so that clients can interact with it.

If you use a Deployment to run your app, that Deployment can create and destroy Pods dynamically. From one moment to the next, you don't know how many of those Pods are working and healthy; you might not even know what those healthy Pods are named. Kubernetes Pods are created and destroyed to match the desired state of your cluster. Pods are ephemeral resources (you should not expect that an individual Pod is reliable and durable).

Each Pod gets its own IP address (Kubernetes expects network plugins to ensure this). For a given Deployment in your cluster, the set of Pods running in one moment in time could be different from the set of Pods running that application a moment later.

## Service Type: ExternalName
Services of type ExternalName map a Service to a DNS name, not to a typical selector such as my-service or cassandra. You specify these Services with the spec.externalName parameter.

## jaeger-collector

### dev
```
kubectl apply -f k8s-jaeger-collector-service.yaml -n dev
```

### staging
```
kubectl apply -f k8s-jaeger-collector-service.yaml -n staging
```

### prod
```
kubectl apply -f k8s-jaeger-collector-service.yaml -n prod
```

## loki

### dev
```
kubectl apply -f k8s-loki-service.yaml -n dev
```

### staging
```
kubectl apply -f k8s-loki-service.yaml -n staging
```

### prod
```
kubectl apply -f k8s-loki-service.yaml -n prod
```

## seq

### dev
```
kubectl apply -f k8s-seq-service.yaml -n dev
```

### staging
```
kubectl apply -f k8s-seq-service.yaml -n staging
```

### prod
```
kubectl apply -f k8s-seq-service.yaml -n prod
```

## tempo

### dev
```
kubectl apply -f k8s-tempo-service.yaml -n dev
```

### staging
```
kubectl apply -f k8s-tempo-service.yaml -n staging
```

### prod
```
kubectl apply -f k8s-tempo-service.yaml -n prod
```

## elasticsearch

### dev
```
kubectl apply -f k8s-elasticsearch-service.yaml -n dev
```

### staging
```
kubectl apply -f k8s-elasticsearch-service.yaml -n staging
```

### prod
```
kubectl apply -f k8s-elasticsearch-service.yaml -n prod
```