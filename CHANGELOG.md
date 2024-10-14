# Changelog

## [2.2.1](https://github.com/rolehippie/alertmanager/compare/v2.2.0...v2.2.1) (2024-10-14)


### Bugfixes

* **deps:** update dependency oauth2-proxy/oauth2-proxy to v7.7.1 ([9a7204f](https://github.com/rolehippie/alertmanager/commit/9a7204ffbd3bbe26c879c976c107238b4ecd3298))

## [2.2.0](https://github.com/rolehippie/alertmanager/compare/v2.1.0...v2.2.0) (2024-10-07)


### Features

* **deps:** update dependency oauth2-proxy/oauth2-proxy to v7.7.0 ([eaade26](https://github.com/rolehippie/alertmanager/commit/eaade26c441bb2b66a3a78cdb7812b82cb66c058))

## [2.1.0](https://github.com/rolehippie/alertmanager/compare/v2.0.0...v2.1.0) (2024-03-18)


### Features

* **deps:** update minor versions ([3c1255b](https://github.com/rolehippie/alertmanager/commit/3c1255bfb6ad59ccd80acc0fe844201996560432))

## [2.0.0](https://github.com/rolehippie/alertmanager/compare/v1.6.1...v2.0.0) (2024-02-12)


### Features

* drop support for ubuntu 18.04 ([f360db7](https://github.com/rolehippie/alertmanager/commit/f360db799a63477cefc6f6905e2113251170d6df))
* used full qualified collection names ([37b429f](https://github.com/rolehippie/alertmanager/commit/37b429f5613487e8b32941458c7a06e5f387f539))


### Bugfixes

* remove meta requirements and document used collections ([4644054](https://github.com/rolehippie/alertmanager/commit/4644054161a039929757dd6b12d160c5f4bfedce))
* use right attribute for user shell ([ed3ea0a](https://github.com/rolehippie/alertmanager/commit/ed3ea0a549a170d5a8e796106765b70ffca7899f))

## [1.6.1](https://github.com/rolehippie/alertmanager/compare/v1.6.0...v1.6.1) (2023-09-25)


### Bugfixes

* **deps:** update dependency oauth2-proxy/oauth2-proxy to v7.5.1 ([7997547](https://github.com/rolehippie/alertmanager/commit/7997547178145171f090ad4f26d3d0067321a82f))

## [1.6.0](https://github.com/rolehippie/alertmanager/compare/v1.5.0...v1.6.0) (2023-09-11)


### Features

* **deps:** update dependency oauth2-proxy/oauth2-proxy to v7.5.0 ([12e575e](https://github.com/rolehippie/alertmanager/commit/12e575e68a2f796a8eda2ee0b247a324eabe187d))

## [1.5.0](https://github.com/rolehippie/alertmanager/compare/v1.4.0...v1.5.0) (2023-08-31)


### Features

* **deps:** update dependency prometheus/alertmanager to v0.26.0 ([d1d1b11](https://github.com/rolehippie/alertmanager/commit/d1d1b11ddbe1551dc506d76e7d46887957406241))

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
