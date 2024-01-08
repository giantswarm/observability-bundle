# Observability bundle upgrade guide

This document describes the changes that need to be made to the observability bundle to upgrade from one version to another.

## Upgrade from 0.x.y to 1.0.0

### Changes

Release 1.0.0 of the observability bundle brings along a number of breaking changes that need to be addressed when upgrading from 0.x.y.

The main changes are:

- Moving all user configs from under `apps.<appName>.userConfig` from string to regular helm values to `userConfig.<appName>`
- Renaming of `prometheus-operator-app` to `kube-prometheus-stack`
- Renaming of `promtail-agent` to `prometheusAgent`
- Renaming of `prometheus-operator-crd` to `prometheusOperatorCrd`

### Upgrade steps

To ensure a smooth upgrade, you can keep the old and new values along side each other before the upgrade to Giant Swarm Platform release 20.0.0 and then remove the old values once the upgrade is complete.

Here is the list of changes that you need to apply to your values file:

- Copy all user configs from `apps.<appName>.userConfig` to regular helm values to `userConfig.<appName>`. Note that this is now moving from a string template to regular values so it is easier to change the values.
- Rename from `userConfig.prometheus-operator-app.configMap.values.prometheus-operator-app` to `userConfig.kubePrometheusStack.configMap.values.kube-prometheus-stack`
- Rename `userConfig.promtail-app` to `userConfig.promtail` if it applies to your use case

```yaml
apiVersion: v1
data:
  values: |
    # new values, to add before upgrade
    userConfig:
      kubePrometheusStack:
        configMap:
          values:
            kube-prometheus-stack:
              my-custom-prometheus-operator-config: xxx
      promtail:
        configMap:
          values:
            my-custom-promtail-config: xxx
    # old values, to remove after upgrade
    apps:
      prometheus-operator-app:
        userConfig:
          configMap:
            values: | ## This is moving from a string to a regular helm value
              my-custom-prometheus-operator-config: xxx
      promtail-app:
        userConfig:
          configMap:
            values: | ## This is moving from a string to a regular helm value
              my-custom-promtail-config: xxx
kind: ConfigMap
metadata:
  name: clusterID-observability-bundle-user-values
  namespace: clusterID
```

#### Prometheus Operator namespace override

If you are overriding the namespace for the Prometheus Operator, you will need to edit the configmap like so:

```yaml
apiVersion: v1
data:
  values: |
    apps:
      # old values, to remove after upgrade
      prometheus-operator-app:
        namespace: monitoring
      # new values, to add before upgrade
      kubePrometheusStack:
        namespace: monitoring
kind: ConfigMap
metadata:
  name: clusterID-observability-bundle-user-values
  namespace: clusterID
```

#### Grafana users

If you are using grafana with persistence enabled, you will need to be careful not to lose your data.
To that end, you should set the value for both `apps.prometheus-operator-app.userConfig.configMap.values.kube-prometheus-stack.grafana.persistence.existingClaim` and `userConfig.kubePrometheusStack.configMap.values.kube-prometheus-stack.grafana.persistence.existingClaim` to match the name of your existing PVC.

Example:

```yaml
apiVersion: v1
data:
  values: |
    userConfig:
      kubePrometheusStack:
        configMap:
          values:
            kube-prometheus-stack:
              grafana:
                persistence:
                  enabled: true
                  existingClaim: grafana
    apps:
      prometheus-operator-app:
        userConfig:
          configMap:
            values: |
              prometheus-operator-app:
                grafana:
                  persistence:
                    enabled: true
                    existingClaim: grafana
kind: ConfigMap
metadata:
  name: clusterID-observability-bundle-user-values
  namespace: clusterID
```

### Clean up

Once your cluster is upgraded to release 20.0.0 and the observability bundle is upgraded to version 1.0.0, then you can start cleaning up the old configuration by:
- Removing all `apps.<appName>.userConfig` from your values file
- Removing the `apps.prometheus-operator-app` section from your values file if it applies.
