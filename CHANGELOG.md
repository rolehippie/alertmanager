# Changelog

## [1.4.0](https://github.com/rolehippie/alertmanager/compare/v1.3.0...v1.4.0) (2023-08-24)


### Features

* add optional defaults for cpu and memory limit ([4ee11f6](https://github.com/rolehippie/alertmanager/commit/4ee11f650f85743fde3ff206ffc2eb52d01c3987))

## [1.3.0](https://github.com/rolehippie/alertmanager/compare/v1.2.0...v1.3.0) (2023-07-06)


### Features

* add options to disable access and auth logging for oauth2 proxy ([13477a5](https://github.com/rolehippie/alertmanager/commit/13477a50b6e6092e1b9ebda4a02bfdf9f151b5a2))

## [1.2.0](https://github.com/rolehippie/alertmanager/compare/v1.1.0...v1.2.0) (2023-07-05)


### Features

* add templates to alertmanager ([6f21e1a](https://github.com/rolehippie/alertmanager/commit/6f21e1a5fa5999e738ac8914aedf016d43dbf447))

## [1.1.0](https://github.com/rolehippie/alertmanager/compare/v1.0.0...v1.1.0) (2023-01-04)


### Features

* pull docker image as part of playbook, not service ([a8071ea](https://github.com/rolehippie/alertmanager/commit/a8071ea33de311cf79761c4bbd18bde4ec513df3))

## 1.0.0 (2023-01-03)

### Features

* **deps:** update dependency prometheus/alertmanager to v0.25.0 ([bcda30a](https://github.com/rolehippie/alertmanager/commit/bcda30a5a89010f1ef4cddcb6d60bdbd3a03a323))
* integrate docker install method ([fc9cab4](https://github.com/rolehippie/alertmanager/commit/fc9cab4b37acdaf694d7fe4c3ebb298c77281c10))
* integrated automated release process ([d48cf14](https://github.com/rolehippie/alertmanager/commit/d48cf1443bb84398592f74e6c05ab8684b45722d))

### Bugfixes

* only set smtp credentials if provided ([5b48b21](https://github.com/rolehippie/alertmanager/commit/5b48b210a949686e5b6239eebea6afe4ca85ae1b))
* stdout and stderr for version check ([ebe074a](https://github.com/rolehippie/alertmanager/commit/ebe074ae342baaffd92a363a8bad11e96a445192))
* use include_tasks instead of include ([91eba82](https://github.com/rolehippie/alertmanager/commit/91eba8205e055e670e1481a50a1d2851aae47b5f))
* use keycloak-oidc provider for oauth2 proxy ([7515c45](https://github.com/rolehippie/alertmanager/commit/7515c451acbae1907e700bf2c7fc93b39ca920d4))
