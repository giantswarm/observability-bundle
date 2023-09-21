# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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

[Unreleased]: https://github.com/giantswarm/observability-bundle/compare/v0.8.4...HEAD
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
