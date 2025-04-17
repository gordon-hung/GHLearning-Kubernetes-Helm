# Redis

## Helm Repo Add Bitnami
```
 helm repo add bitnami https://charts.bitnami.com/bitnami
```

## Helm Repo Update
```
 helm repo update
```

## Helm Copy values.yaml
```
 helm show values bitnami/redis > .\values.yaml
```

## Password

```
  redis:
    password: "1qaz2wsx"
```

## When installing the chart with architecture=standalone, it will deploy a standalone Redis® StatefulSet. A single service will be exposed:
```
## @param architecture Redis&reg; architecture. Allowed values: `standalone` or `replication`
##
architecture: standalone
```

## Metrics
```
  ## @param metrics.enabled Start a sidecar prometheus exporter to expose Redis&reg; metrics
  ##
  enabled: true
```

## Helm Upgrade/Install
```
helm upgrade --install redis bitnami/redis --version 20.12.1 -f .\values.yaml
```