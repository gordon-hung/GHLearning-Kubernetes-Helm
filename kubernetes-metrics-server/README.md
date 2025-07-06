# Kubernetes Metrics Server

Metrics Server is a scalable, efficient source of container resource metrics for Kubernetes
built-in autoscaling pipelines.

Metrics Server collects resource metrics from Kubelets and exposes them in Kubernetes apiserver through [Metrics API]
for use by [Horizontal Pod Autoscaler] and [Vertical Pod Autoscaler]. Metrics API can also be accessed by `kubectl top`,
making it easier to debug autoscaling pipelines.

## secure-port 10250 修改 4443
```
      - args:
        - --cert-dir=/tmp
        - --secure-port=10250
```
修改如下
```		
      - args:
        - --cert-dir=/tmp
        - --secure-port=4443
```

## add --kubelet-insecure-tls
```
      - args:
        - --cert-dir=/tmp
        - --secure-port=10250
        - --kubelet-preferred-address-types=InternalIP,ExternalIP,Hostname
        - --kubelet-use-node-status-port
        - --metric-resolution=15s
```
修改如下
```		
      - args:
        - --cert-dir=/tmp
        - --secure-port=4443
        - --kubelet-preferred-address-types=InternalIP,ExternalIP,Hostname
        - --kubelet-use-node-status-port
        - --metric-resolution=15s
        - --kubelet-insecure-tls
```

## containerPort 10250 修改 4443
```
        ports:
        - containerPort: 10250
          name: https
          protocol: TCP
```
修改如下
```
        ports:
        - containerPort: 4443
          name: https
          protocol: TCP
```

## kubectl apply
```
kubectl apply -f .\high-availability-1.21+.yaml
```

## kubectl top pod

```
kubectl top pod -n kube-system 
```
![image](https://github.com/gordon-hung/GHLearning-Kubernetes-Helm/tree/master/kubernetes-metrics-server/Images/kubectl_top_pod.png)