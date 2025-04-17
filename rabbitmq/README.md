# RabbitMQ

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
 helm show values bitnami/rabbitmq > .\values.yaml
```

## User Password

```
  ## @param auth.username RabbitMQ application username
  ## ref: https://github.com/bitnami/containers/tree/main/bitnami/rabbitmq#environment-variables
  ##
  username: guest
  ## @param auth.password RabbitMQ application password
  ## ref: https://github.com/bitnami/containers/tree/main/bitnami/rabbitmq#environment-variables
  ##
  password: guest
  ## @param auth.securePassword Whether to set the RabbitMQ password securely. This is incompatible with loading external RabbitMQ definitions and 'true' when not setting the auth.password parameter.
  ## ref: https://github.com/bitnami/containers/tree/main/bitnami/rabbitmq#environment-variables
  ##
  securePassword: false
```

## Extra Plugins
```
## @param extraPlugins Extra plugins to enable (single string containing a space-separated list)
## Use this instead of `plugins` to add new plugins
##
extraPlugins: "rabbitmq_auth_backend_ldap rabbitmq_shovel rabbitmq_shovel_management"
```

## Metrics
```
  ## @param metrics.enabled Enable exposing RabbitMQ metrics to be gathered by Prometheus
  ##
  enabled: true
```

## Helm Upgrade/Install
```
 helm upgrade --install rabbitmq bitnami/rabbitmq --version 15.5.3 -f values.yaml
```