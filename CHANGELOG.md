# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.5] - 2022-12-14

### Changed

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

[Unreleased]: https://github.com/giantswarm/observability-bundle/compare/v0.1.5...HEAD
[0.1.5]: https://github.com/giantswarm/observability-bundle/compare/v0.1.4...v0.1.5
[0.1.4]: https://github.com/giantswarm/observability-bundle/compare/v0.1.3...v0.1.4
[0.1.3]: https://github.com/giantswarm/observability-bundle/compare/v0.1.2...v0.1.3
[0.1.2]: https://github.com/giantswarm/observability-bundle/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/giantswarm/observability-bundle/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/giantswarm/observability-bundle/releases/tag/v0.1.0
