# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Add KSM metrics for Envoy Gateway resources.
- Add `application.giantswarm.io/team` annotation from HelmReleases as label to KSM emitted metrics.

### Changed

- Change team annotation in `Chart.yaml` to OpenContainers format (`io.giantswarm.application.team`).
- Update alloy-app to 0.16.1
- Update kube-prometheus-stack to 19.0.2
- Update prometheus-operator-crd to 19.0.1

## [2.6.0] - 2026-01-28

### Added

- Add KSM metrics for Gateway API resources.

## [2.5.0] - 2026-01-06

### Added

- Add KSM metrics `kube_servicemonitor_info` and `kube_podmonitor_info` for ServiceMonitor and PodMonitor resources
- Add KSM metrics `kube_podlog_info` for PodLog resource

## [2.4.1] - 2025-12-29

### Fixed

- Fixed KSM metrics for endpoints

## [2.4.0] - 2025-12-16

### Changed

- Upgrade `kube-prometheus-stack-app` to 19.0.0
- Update alloy-app to 0.16.0
  - Bumps alloy to 1.12.0

## [2.3.2] - 2025-10-15

### Added

- Add KSM metrics for cloudnative-pg Cluster objects

## [2.3.1] - 2025-10-14

### Fixed

- Update alloy-app to 0.15.1
  - Bumps alloy to 1.11.2

## [2.3.0] - 2025-10-09

### Changed

- Update alloy-app to 0.15.0
  - Bumps alloy to 1.11.0

## [2.2.2] - 2025-09-08

### Changed

- Upgrade `kube-prometheus-stack-app` to 18.1.0
- Add relabeling rules from `cluster-api-monitoring-app` so that `cluster_id` label points to the workload cluster name as expected in some alert definitions

## [2.2.1] - 2025-09-05

### Added

- Add KSM metrics for IRSAClaim objects

## [2.2.0] - 2025-09-02

### Changed

- Upgrade `kube-prometheus-stack` to 77.0.1
  - Bumps prometheus-operator and CRDs to 0.85.0
- Update alloy-app to 0.13.0

## [2.1.0] - 2025-08-21

### Changed

- Upgrade `kube-prometheus-stack` to 76.4.0
  - Bumps prometheus-operator and CRDs to 0.84.1
  - Bumps prometheus to 3.5.0
- Update alloy-app to 0.12.1
  - Bumps alloy to 1.10.1

## [2.0.0] - 2025-06-03

### Removed

- Clean up old and deprecated telemetry collectors:
  - `promtail`
  - `grafana-agent`
  - `promtheus-agent`
- Disable PodSecurityPolicies by default as PodSecurityPolicies are deprecated and removed in Kubernetes v1.25+ clusters

## [1.16.1] - 2025-06-03

### Fixed

- Fix catalog for alloy apps as it is now pushed to the default catalog.

## [1.16.0] - 2025-06-02

### Changed

- Upgrade `alloy-app` from 0.10.0 to 0.11.0
-  This bumps the version of `Alloy` from 1.8.3 to 1.9.0

## [1.15.0] - 2025-06-02

### Changed

- Upgrade `alloy-app` from 0.9.0 to 0.10.0
  - This bumps the version of `Alloy` from 1.7.1 to 1.8.3

## [1.14.1] - 2025-05-21

### Changed

- Reconfigure Flux-related part of the KSM to use wildcards instead of hardcoded versions.
- Rename Flux-related metrics produced by the KSM.

## [1.14.0] - 2025-05-13

### Changed

- Upgrade `kube-prometheus-stack` to 72.3.0
  - Bumps prometheus-operator to 0.82.0
  - Bumps prometheus-operator CRDs to 0.82.0

## [1.13.0] - 2025-04-10

### Added

- Add support for enabling pre-configured custom resources in KSM
- Add metrics containing labels for Crossplane resources

### Changed

- Upgrade `kube-prometheus-stack` to 72.3.0
  - Bumps prometheus-operator to 0.82.0

## [1.12.0] - 2025-03-21

### Changed

- Upgrade `kube-prometheus-stack` from 69.5.1 to 70.1.1
  - Bumps prometheus-operator to 0.81.0
  - Bumps prometheus to 3.2.1

## [1.11.0] - 2025-02-27

### Changed

- prometheus-operator will not check promql syntax for prometheusRules that are labelled `observability.giantswarm.io/rule-type: logs`
- Upgrade `alloy` to chart 0.9.0.
  - Bumps `alloy` from to 1.5.1 to 1.7.1

## [1.10.0] - 2025-02-26

### Changed

- Upgrade `alloy` to chart 0.8.0.
  - Bumps `alloy` from to 1.5.0 to 1.6.1
- Upgrade `kube-prometheus-stack` from 66.2.1 to 69.5.1
  - Bumps prometheus-operator to 0.80.1
  - Bumps prometheus to 3.0.1

## [1.9.0] - 2024-11-18

### Added

- Add `alloy` v0.7.0 as `alloyEvents`.

### Changed

- Upgrade `alloy-logs` and `alloy-metrics` to chart 0.7.0.
  - Bumps `alloy` from 1.4.2 to 1.5.0
- upgrade `kube-prometheus-stack` from 65.1.1 to 66.2.1
  - prometheus-operator CRDs from 0.75.0 to 0.78.1
  - prometheus-operator from 0.77.1 to 0.78.1
  - prometheus from 2.54.1 to 2.55.1
  - kube-state-metrics from 2.13.0 to 2.14.0
  - grafana from 8.5.0 to 8.6.0

## [1.8.0] - 2024-10-30

### Changed

- Upgrade `prometheus-agent` from v0.6.9 to v0.7.0.
  - Adds extraArgs to be able to use nice features like wal truncation
- upgrade `kube-prometheus-stack` from 61.0.0 to 65.1.1
  - prometheus-operator CRDs from 0.73.0 to 0.75.0
  - prometheus-operator from 0.75.0 to 0.77.1
  - prometheus upgraded from 2.53.0 to 2.54.1
  - grafana from 8.2.0 to 8.5.0
  - thanos ruler upgraded from 0.35.1 to 0.36.1
  - prometheus-node-exporter upgraded from 1.8.1 to 1.8.2

### Fixed

- Add missing depends on annotation on alloy-metrics and alloy-logs to make sure they are deployed after the prometheus-operator-crds.

## [1.7.0] - 2024-10-09

### Changed

- Upgrade `alloyLogs` to v0.6.1
  - Allow passing PodLogs via helm chart values
  - Upgrade to Alloy v1.4.2 which fixes a bug with component reload/evaluation and keeping Alloy up-to-date
  - Fixes an issue with CiliumNetworkPolicy preventing Alloy to run in clustering mode

## [1.6.2] - 2024-09-17

### Fixed

- Fixed `alloyMetrics` catalog

## [1.6.1] - 2024-08-20

### Fixed

- Disable usage reporting to GrafanaLabs by:
  - Bumping `alloyLogs` and `alloyMetrics` to v0.4.1.
  - Bumping `grafanaAgent` to v0.4.6.

## [1.6.0] - 2024-08-20

### Added

- Add `alloy` v0.4.0 as `alloyMetrics`.

### Changed

- Bump `alloyLogs` to v0.4.0.

## [1.5.3] - 2024-08-08

### Fixed

- Rename `alloy-logs` app to camel case `alloyLogs`.

## [1.5.2] - 2024-07-24

### Changed

- Fix CNP issues (allow traffic from pods in kube-system to nginx-ingress-controller)
  - Upgrade `grafana-agent` to 0.4.5.
  - Upgrade `alloy` to 0.3.1.
  - Upgrade `promtail` to 1.5.4.

## [1.5.1] - 2024-07-19

### Changed

- Upgrade `prometheus-operator-crd` to 11.0.1.

## [1.5.0] - 2024-07-18

### Added

- Add `alloy` v0.3.0 as `alloy-logs`

### Changed

- prometheus-operator will not check promql syntax for prometheusRules that are labelled `application.giantswarm.io/prometheus-rule-kind: loki`

## [1.4.0] - 2024-07-03

### Changed

- Upgrade `kube-prometheus-stack` to 11.0.0 and `prometheus-operator-crd` to 11.0.0. This upgrade mainly consists in:
  - kube-prometheus-stack dependency chart upgraded from [56.21.2](https://github.com/prometheus-community/helm-charts/releases/tag/kube-prometheus-stack-56.21.2) to [61.0.0](https://github.com/prometheus-community/helm-charts/releases/tag/kube-prometheus-stack-61.0.0)
  - prometheus upgrade from 2.50.1 to [2.53.0](https://github.com/prometheus-community/helm-charts/releases/tag/prometheus-25.22.0)
  - thanos ruler upgrade from 0.34.1 to [0.35.1](https://github.com/thanos-io/thanos/releases/tag/v0.35.1)
  - kube-state-metrics from 2.10.0 to 2.12.0
  - prometheus-operator from 0.71.2 [0.75.0](https://github.com/prometheus-operator/prometheus-operator/releases/tag/v0.75.0) - adding remoteWrite.proxyFromEnvironment and Scrape Class support
  - prometheus-node-exporter upgraded from 1.8.0 to [1.8.1](https://github.com/prometheus/node_exporter/releases/tag/v1.8.1)
- Upgrade `grafana-agent` from 0.4.3 to 0.4.4
  - This version enables the override the grafana agent `CiliumNetworkPolicy` egress and ingress sections.

## [1.3.4] - 2024-04-04

### Changed

- Upgrade `kube-prometheus-stack` to 9.1.2.

## [1.3.3] - 2024-04-03

### Changed

- Upgrade `grafana-agent` to 0.4.3.
  - This version upgrade consists in internal changes
- Upgrade `kube-prometheus-stack` to 9.1.1

## [1.3.2] - 2024-03-13

### Changed

- Upgrade `promtail` to 1.5.3.
  - Set RAM limit to 2x requests

## [1.3.1] - 2024-03-12

### Changed

- Upgrade `promtail` to 1.5.2.
  - Adjust CPU settings

## [1.3.0] - 2024-03-06

### Changed

- Upgrade `kube-prometheus-stack` to 9.1.0.

## [1.2.4] - 2024-03-06

### Changed

- upgrade `prometheus-agent` to 0.6.9.

## [1.2.3] - 2024-02-19

### Changed

- upgrade `prometheus-agent` to 0.6.8.

## [1.2.2] - 2024-02-13

### Changed

- Upgrade `promtail` to 1.5.1.
- Upgrade `grafana-agent` to 0.4.1.

## [1.2.1] - 2024-02-07

### Added

- Add dependency on `prometheus-operator-crd` to all apps.

## [1.2.0] - 2024-02-07

### Changed

- Upgrade `kube-prometheus-stack` and `prometheus-operator-crd` to 9.0.0.
- Add the `global.podSecurityStandards.enforced` value back to be able to work on CAPI WCs.

## [1.1.1] - 2024-01-30

### Changed

- Upgrade `kube-prometheus-stack` to 8.1.3 (gsoci registry).

## [1.1.0] - 2024-01-22

### Changed

- Upgrade `promtail` to 1.5.0.
- Upgrade `kube-prometheus-stack` to 8.1.2.
- Upgrade `grafana-agent` to 0.4.0.
- Upgrade `prometheus-agent` to 0.6.7.

## [1.0.0] - 2024-01-08

### Changed

- *!Breaking change*: Simplify configuration for the bundled apps. See our [upgrade guide](./docs/upgrade.md)
  - Move all user configs from under `apps.<appName>.userConfig` from string to regular helm values to `userConfig.<appName>`
  - Rename `prometheus-operator-app` to `kube-prometheus-stack`
  - Rename `promtail-app` to `promtail`
- Enforce `Cilium Network Policy` by default.
- Enforce `Pod Security Standard` by default.
- Upgrade `kube-prometheus-stack` to 8.1.1 and `prometheus-operator-crd` to 8.0.0
- Upgrade `grafana-agent` to 0.3.2.

## [0.10.1] - 2023-11-15

### Fixed

- Extend `prometheus-operator-app` timeout to avoid race condition with VPA causing the app to be stuck in `pending-install` state.

## [0.10.0] - 2023-11-08

### Changed

- Upgrade `grafana-agent` to 0.3.0.

## [0.9.1] - 2023-11-02

### Changed

- Upgrade `prometheus-agent` to 0.6.6.

## [0.9.0] - 2023-10-26

### Added

- Add `grafana-agent-app` to `observability-bundle`.

## [0.8.9] - 2023-10-18

### Fixed

- Disable `kube-state-metrics` psp when `pod security policies` are enforced.

## [0.8.8] - 2023-10-11

### Changed

- Upgrade `prometheus-operator-app` to 6.2.1.
- Upgrade `prometheus-agent` to 0.6.5.

## [0.8.7] - 2023-10-04

### Changed

- Upgrade `prometheus-agent` to 0.6.4.

## [0.8.6] - 2023-10-03

### Fixed

- Fix missing external labels on the prometheus agent when global.podSecurityStandards.enforced is set to false.

## [0.8.5] - 2023-10-03

### Changed

- Add condition for PSP installation in helm chart.

## [0.8.4] - 2023-09-21

### Changed

- Upgrade `prometheus-agent` to 0.6.3.

## [0.8.3] - 2023-09-21

### Changed

- Enable the `kube-proxy` servicemonitor.

## [0.8.2] - 2023-09-13

### Changed

- Upgrade `promtail` to 1.4.0.

## [0.8.1] - 2023-09-12

- Upgrade `prometheus-agent` to 0.6.2.
  - Upgrade `prometheus` to 2.47.0.
- Upgrade `prometheus-operator-app` and `prometheus-operator-crd` to 6.1.0.

## [0.8.0] - 2023-09-04

### Changed

- Upgrade `prometheus-agent` to 0.6.0.
- Upgrade `prometheus-operator-app` and `prometheus-operator-crd` to 6.0.0.

## [0.7.5] - 2023-08-29

### Added

- Add extraConfig priority support.

## [0.7.4] - 2023-08-29

### Changed

- Upgrade `prometheus-operator-app` to 5.2.0.

## [0.7.3] - 2023-08-24

### Changed

- Add extra config for `prometheus-operator-app` to be able to enable cilium.
- Upgrade `prometheus-operator-app` and `prometheus-operator-crd` to 5.1.0.

## [0.7.2] - 2023-07-13

### Changed

- Upgrade `prometheus-operator-app` to 5.0.7.

## [0.7.1] - 2023-06-29

### Changed

- Upgrade `promtail-app` to 1.1.1.
- Upgrade `prometheus-operator-app` to 5.0.6.

## [0.7.0] - 2023-06-12

### Changed

- Upgrade `prometheus-operator-app` to 5.0.5.
- Upgrade `prometheus-operator-crd` to 5.0.0.

## [0.6.0] - 2023-05-22

### Changed

- Upgrade `prometheus-agent-app` to 0.5.3.
- Upgrade `prometheus-operator-app` to 4.4.0.

## [0.5.1] - 2023-05-11

### Changed

- Remove cluster prefix to app name in _helpers.tpl

## [0.5.0] - 2023-05-10

### Changed

- Remove custom config in favor of proper extra-config.
- Upgrade `prometheus-agent-app` to 0.5.2 to allow sharding capabilities.
- Upgrade `prometheus-operator-app` to 4.2.4.

## [0.4.3] - 2023-04-26

- Upgrade `prometheus-operator-app` to 4.2.3.

## [0.4.2] - 2023-04-21

### Changed

- Upgrade `prometheus-agent-app` to 0.4.1.

## [0.4.1] - 2023-04-20

### Changed

- Upgrade `prometheus-agent-app` to 0.4.0.

## [0.4.0] - 2023-04-13

### Added

- Add extra configmap and secret to `promtail-app`.

### Changed

- Upgrade `prometheus-operator-app` to 4.2.1.

### Removed

- Moving prometheus-operator-app user-configs to the prometheus-operator-app https://github.com/giantswarm/prometheus-operator-app/pull/249

## [0.3.0] - 2023-03-22

### Changed

- Add new app dependency mechanism (`app-operator.giantswarm.io/depends-on`) to the prometheus-operator-app and agent so they are not installed until the CRD app is deployed.
- prometheus-operator: drop `apiserver_request_slo_duration_seconds_bucket` metrics from apiserver
- upgrade `prometheus-operator-app` to 4.0.1 and `prometheus-operator-crd` to 4.0.0
- upgrade `prometheus-agent` to 0.3.0 to support chinese registry

### Added

- Add `promtail-app` v1.0.1 disabled by default.

## [0.2.0] - 2023-02-21

### Changed

- Upgrade `prometheus-agent` from to 0.1.7 to 0.2.0.

## [0.1.9] - 2023-01-16

### Changed

- Upgrade `prometheus-operator-app` to 3.0.0.
- Upgrade `prometheus-operator-crd` to 3.0.0.

## [0.1.8] - 2022-12-19

### Changed

- Upgrade `prometheus-agent` from 0.1.6 to 0.1.7.

## [0.1.7] - 2022-12-19

## Changed

- Tuned default helm timeouts

## [0.1.6] - 2022-12-14

### Added

- Push to `control-plane-catalog`.

## [0.1.5] - 2022-12-14

### Changed

- Enable `app-build-suite`.
- Push to `aws` and `azure` app collections.

### Fixed

- Fix `kube-scheduler` port.
- Fix `org-` namespace detection.

## [0.1.4] - 2022-12-06

### Changed

- Change `ServiceMonitor` and `PodMonitor` discovery label selector.
- Enable renovate and bump dependencies.

## [0.1.3] - 2022-11-25

### Changed

- Change controller-manager and scheduler ServiceMonitor selector.

## [0.1.2] - 2022-11-08

### Changed

- Bump prometheus-agent to 0.1.5

### Added

- Add selectors for prometheus-agent ServiceMonitors

## [0.1.1] - 2022-10-26

### Fixed

- Fix target relabellings.

## [0.1.0] - 2022-10-24

### Added

- First release.
- Add a way of wiring extra config in the apps.

### Changed

- `app.giantswarm.io` label group was changed to `application.giantswarm.io`

[Unreleased]: https://github.com/giantswarm/observability-bundle/compare/v2.6.0...HEAD
[2.6.0]: https://github.com/giantswarm/observability-bundle/compare/v2.5.0...v2.6.0
[2.5.0]: https://github.com/giantswarm/observability-bundle/compare/v2.4.1...v2.5.0
[2.4.1]: https://github.com/giantswarm/observability-bundle/compare/v2.4.0...v2.4.1
[2.4.0]: https://github.com/giantswarm/observability-bundle/compare/v2.3.2...v2.4.0
[2.3.2]: https://github.com/giantswarm/observability-bundle/compare/v2.3.1...v2.3.2
[2.3.1]: https://github.com/giantswarm/observability-bundle/compare/v2.3.0...v2.3.1
[2.3.0]: https://github.com/giantswarm/observability-bundle/compare/v2.2.2...v2.3.0
[2.2.2]: https://github.com/giantswarm/observability-bundle/compare/v2.2.1...v2.2.2
[2.2.1]: https://github.com/giantswarm/observability-bundle/compare/v2.2.0...v2.2.1
[2.2.0]: https://github.com/giantswarm/observability-bundle/compare/v2.1.0...v2.2.0
[2.1.0]: https://github.com/giantswarm/observability-bundle/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/giantswarm/observability-bundle/compare/v1.16.1...v2.0.0
[1.16.1]: https://github.com/giantswarm/observability-bundle/compare/v1.16.0...v1.16.1
[1.16.0]: https://github.com/giantswarm/observability-bundle/compare/v1.15.0...v1.16.0
[1.15.0]: https://github.com/giantswarm/observability-bundle/compare/v1.14.1...v1.15.0
[1.14.1]: https://github.com/giantswarm/observability-bundle/compare/v1.14.0...v1.14.1
[1.14.0]: https://github.com/giantswarm/observability-bundle/compare/v1.13.0...v1.14.0
[1.13.0]: https://github.com/giantswarm/observability-bundle/compare/v1.12.0...v1.13.0
[1.12.0]: https://github.com/giantswarm/observability-bundle/compare/v1.11.0...v1.12.0
[1.11.0]: https://github.com/giantswarm/observability-bundle/compare/v1.10.0...v1.11.0
[1.10.0]: https://github.com/giantswarm/observability-bundle/compare/v1.9.0...v1.10.0
[1.9.0]: https://github.com/giantswarm/observability-bundle/compare/v1.8.0...v1.9.0
[1.8.0]: https://github.com/giantswarm/observability-bundle/compare/v1.7.0...v1.8.0
[1.7.0]: https://github.com/giantswarm/observability-bundle/compare/v1.6.2...v1.7.0
[1.6.2]: https://github.com/giantswarm/observability-bundle/compare/v1.6.1...v1.6.2
[1.6.1]: https://github.com/giantswarm/observability-bundle/compare/v1.6.0...v1.6.1
[1.6.0]: https://github.com/giantswarm/observability-bundle/compare/v1.5.3...v1.6.0
[1.5.3]: https://github.com/giantswarm/observability-bundle/compare/v1.5.2...v1.5.3
[1.5.2]: https://github.com/giantswarm/observability-bundle/compare/v1.5.1...v1.5.2
[1.5.1]: https://github.com/giantswarm/observability-bundle/compare/v1.5.0...v1.5.1
[1.5.0]: https://github.com/giantswarm/observability-bundle/compare/v1.4.0...v1.5.0
[1.4.0]: https://github.com/giantswarm/observability-bundle/compare/v1.3.4...v1.4.0
[1.3.4]: https://github.com/giantswarm/observability-bundle/compare/v1.3.3...v1.3.4
[1.3.3]: https://github.com/giantswarm/observability-bundle/compare/v1.3.2...v1.3.3
[1.3.2]: https://github.com/giantswarm/observability-bundle/compare/v1.3.1...v1.3.2
[1.3.1]: https://github.com/giantswarm/observability-bundle/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/giantswarm/observability-bundle/compare/v1.2.4...v1.3.0
[1.2.4]: https://github.com/giantswarm/observability-bundle/compare/v1.2.3...v1.2.4
[1.2.3]: https://github.com/giantswarm/observability-bundle/compare/v1.2.2...v1.2.3
[1.2.2]: https://github.com/giantswarm/observability-bundle/compare/v1.2.1...v1.2.2
[1.2.1]: https://github.com/giantswarm/observability-bundle/compare/v1.2.0...v1.2.1
[1.2.0]: https://github.com/giantswarm/observability-bundle/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/giantswarm/observability-bundle/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/giantswarm/observability-bundle/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/giantswarm/observability-bundle/compare/v0.10.1...v1.0.0
[0.10.1]: https://github.com/giantswarm/observability-bundle/compare/v0.10.0...v0.10.1
[0.10.0]: https://github.com/giantswarm/observability-bundle/compare/v0.9.1...v0.10.0
[0.9.1]: https://github.com/giantswarm/observability-bundle/compare/v0.9.0...v0.9.1
[0.9.0]: https://github.com/giantswarm/observability-bundle/compare/v0.8.9...v0.9.0
[0.8.9]: https://github.com/giantswarm/observability-bundle/compare/v0.8.8...v0.8.9
[0.8.8]: https://github.com/giantswarm/observability-bundle/compare/v0.8.7...v0.8.8
[0.8.7]: https://github.com/giantswarm/observability-bundle/compare/v0.8.6...v0.8.7
[0.8.6]: https://github.com/giantswarm/observability-bundle/compare/v0.8.5...v0.8.6
[0.8.5]: https://github.com/giantswarm/observability-bundle/compare/v0.8.4...v0.8.5
[0.8.4]: https://github.com/giantswarm/observability-bundle/compare/v0.8.3...v0.8.4
[0.8.3]: https://github.com/giantswarm/observability-bundle/compare/v0.8.2...v0.8.3
[0.8.2]: https://github.com/giantswarm/observability-bundle/compare/v0.8.1...v0.8.2
[0.8.1]: https://github.com/giantswarm/observability-bundle/compare/v0.8.0...v0.8.1
[0.8.0]: https://github.com/giantswarm/observability-bundle/compare/v0.7.5...v0.8.0
[0.7.5]: https://github.com/giantswarm/observability-bundle/compare/v0.7.4...v0.7.5
[0.7.4]: https://github.com/giantswarm/observability-bundle/compare/v0.7.3...v0.7.4
[0.7.3]: https://github.com/giantswarm/observability-bundle/compare/v0.7.2...v0.7.3
[0.7.2]: https://github.com/giantswarm/observability-bundle/compare/v0.7.1...v0.7.2
[0.7.1]: https://github.com/giantswarm/observability-bundle/compare/v0.7.0...v0.7.1
[0.7.0]: https://github.com/giantswarm/observability-bundle/compare/v0.6.0...v0.7.0
[0.6.0]: https://github.com/giantswarm/observability-bundle/compare/v0.5.1...v0.6.0
[0.5.1]: https://github.com/giantswarm/observability-bundle/compare/v0.5.0...v0.5.1
[0.5.0]: https://github.com/giantswarm/observability-bundle/compare/v0.4.3...v0.5.0
[0.4.3]: https://github.com/giantswarm/observability-bundle/compare/v0.4.2...v0.4.3
[0.4.2]: https://github.com/giantswarm/observability-bundle/compare/v0.4.1...v0.4.2
[0.4.1]: https://github.com/giantswarm/observability-bundle/compare/v0.4.0...v0.4.1
[0.4.0]: https://github.com/giantswarm/observability-bundle/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/giantswarm/observability-bundle/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/giantswarm/observability-bundle/compare/v0.1.9...v0.2.0
[0.1.9]: https://github.com/giantswarm/observability-bundle/compare/v0.1.8...v0.1.9
[0.1.8]: https://github.com/giantswarm/observability-bundle/compare/v0.1.7...v0.1.8
[0.1.7]: https://github.com/giantswarm/observability-bundle/compare/v0.1.6...v0.1.7
[0.1.6]: https://github.com/giantswarm/observability-bundle/compare/v0.1.5...v0.1.6
[0.1.5]: https://github.com/giantswarm/observability-bundle/compare/v0.1.4...v0.1.5
[0.1.4]: https://github.com/giantswarm/observability-bundle/compare/v0.1.3...v0.1.4
[0.1.3]: https://github.com/giantswarm/observability-bundle/compare/v0.1.2...v0.1.3
[0.1.2]: https://github.com/giantswarm/observability-bundle/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/giantswarm/observability-bundle/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/giantswarm/observability-bundle/releases/tag/v0.1.0
