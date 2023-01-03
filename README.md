# alertmanager

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/alertmanager) [![Testing Build](https://github.com/rolehippie/alertmanager/workflows/testing/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/alertmanager/workflows/readme/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/alertmanager/workflows/galaxy/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/alertmanager)](https://github.com/rolehippie/alertmanager/blob/master/LICENSE)

Ansible role to install and configure Alertmanager.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Default Variables](#default-variables)
  - [alertmanager_data_retention](#alertmanager_data_retention)
  - [alertmanager_default_folders](#alertmanager_default_folders)
  - [alertmanager_default_labels](#alertmanager_default_labels)
  - [alertmanager_default_publish](#alertmanager_default_publish)
  - [alertmanager_default_volumes](#alertmanager_default_volumes)
  - [alertmanager_domain](#alertmanager_domain)
  - [alertmanager_download](#alertmanager_download)
  - [alertmanager_extra_folders](#alertmanager_extra_folders)
  - [alertmanager_extra_labels](#alertmanager_extra_labels)
  - [alertmanager_extra_publish](#alertmanager_extra_publish)
  - [alertmanager_extra_volumes](#alertmanager_extra_volumes)
  - [alertmanager_group_by](#alertmanager_group_by)
  - [alertmanager_image](#alertmanager_image)
  - [alertmanager_inhibit_rules](#alertmanager_inhibit_rules)
  - [alertmanager_installation](#alertmanager_installation)
  - [alertmanager_listen_address](#alertmanager_listen_address)
  - [alertmanager_network](#alertmanager_network)
  - [alertmanager_oauth2_allowed_groups](#alertmanager_oauth2_allowed_groups)
  - [alertmanager_oauth2_client_id](#alertmanager_oauth2_client_id)
  - [alertmanager_oauth2_client_secret](#alertmanager_oauth2_client_secret)
  - [alertmanager_oauth2_cookie_secret](#alertmanager_oauth2_cookie_secret)
  - [alertmanager_oauth2_default_labels](#alertmanager_oauth2_default_labels)
  - [alertmanager_oauth2_default_publish](#alertmanager_oauth2_default_publish)
  - [alertmanager_oauth2_download](#alertmanager_oauth2_download)
  - [alertmanager_oauth2_enabled](#alertmanager_oauth2_enabled)
  - [alertmanager_oauth2_extra_labels](#alertmanager_oauth2_extra_labels)
  - [alertmanager_oauth2_extra_publish](#alertmanager_oauth2_extra_publish)
  - [alertmanager_oauth2_image](#alertmanager_oauth2_image)
  - [alertmanager_oauth2_keycloak_url](#alertmanager_oauth2_keycloak_url)
  - [alertmanager_oauth2_listen_address](#alertmanager_oauth2_listen_address)
  - [alertmanager_oauth2_network](#alertmanager_oauth2_network)
  - [alertmanager_oauth2_provider](#alertmanager_oauth2_provider)
  - [alertmanager_oauth2_static_groups](#alertmanager_oauth2_static_groups)
  - [alertmanager_oauth2_static_users](#alertmanager_oauth2_static_users)
  - [alertmanager_oauth2_upstream](#alertmanager_oauth2_upstream)
  - [alertmanager_oauth2_version](#alertmanager_oauth2_version)
  - [alertmanager_receiver](#alertmanager_receiver)
  - [alertmanager_receivers](#alertmanager_receivers)
  - [alertmanager_routes](#alertmanager_routes)
  - [alertmanager_smtp_from](#alertmanager_smtp_from)
  - [alertmanager_smtp_password](#alertmanager_smtp_password)
  - [alertmanager_smtp_require_tls](#alertmanager_smtp_require_tls)
  - [alertmanager_smtp_smarthost](#alertmanager_smtp_smarthost)
  - [alertmanager_smtp_username](#alertmanager_smtp_username)
  - [alertmanager_version](#alertmanager_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### alertmanager_data_retention

Data retention for alertmanager state

#### Default value

```YAML
alertmanager_data_retention: 120h
```

### alertmanager_default_folders

List of default folders to create

#### Default value

```YAML
alertmanager_default_folders:
  - /etc/alertmanager
  - /var/lib/alertmanager
```

### alertmanager_default_labels

List of default labels to assign to docker

#### Default value

```YAML
alertmanager_default_labels: []
```

### alertmanager_default_publish

List of default port publishing for docker

#### Default value

```YAML
alertmanager_default_publish: []
```

#### Example usage

```YAML
alertmanager_default_publish:
  - 127.0.0.1:9093:9093
```

### alertmanager_default_volumes

List of default volumes to mount for docker

#### Default value

```YAML
alertmanager_default_volumes:
  - /var/lib/alertmanager:/var/lib/alertmanager
  - /etc/alertmanager:/etc/alertmanager
```

### alertmanager_domain

Domain for external access

#### Default value

```YAML
alertmanager_domain:
```

#### Example usage

```YAML
alertmanager_domain: https://alertmanager.example.com
```

### alertmanager_download

URL to the archive of the release to install

#### Default value

```YAML
alertmanager_download: https://github.com/prometheus/alertmanager/releases/download/v{{
  alertmanager_version }}/alertmanager-{{ alertmanager_version }}.linux-amd64.tar.gz
```

### alertmanager_extra_folders

List of extra folders to create

#### Default value

```YAML
alertmanager_extra_folders: []
```

#### Example usage

```YAML
alertmanager_extra_folders:
  - /path/to/host/folder1
  - /path/to/host/folder2
  - /path/to/host/folder3
```

### alertmanager_extra_labels

List of extra labels to assign to docker

#### Default value

```YAML
alertmanager_extra_labels: []
```

### alertmanager_extra_publish

List of extra port publishing for docker

#### Default value

```YAML
alertmanager_extra_publish: []
```

#### Example usage

```YAML
alertmanager_extra_publish:
  - 127.0.0.1:9093:9093
```

### alertmanager_extra_volumes

List of extra volumes to mount for docker

#### Default value

```YAML
alertmanager_extra_volumes: []
```

#### Example usage

```YAML
alertmanager_extra_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### alertmanager_group_by

List of alerting groups

#### Default value

```YAML
alertmanager_group_by: []
```

#### Example usage

```YAML
alertmanager_group_by:
  - alertname
  - app
```

### alertmanager_image

Docker image to use for deployment

#### Default value

```YAML
alertmanager_image: quay.io/prometheus/alertmanager:v{{ alertmanager_version }}
```

### alertmanager_inhibit_rules

List of alerting recipients

#### Default value

```YAML
alertmanager_inhibit_rules: []
```

#### Example usage

```YAML
alertmanager_inhibit_rules:
  - source_match:
      severity: critical
    target_match:
      severity: 'warning'
    equal:
      - alertname
      - dev
      - instance
```

### alertmanager_installation

Select installation method, could be native or docker

#### Default value

```YAML
alertmanager_installation: native
```

### alertmanager_listen_address

Listen address for the alertmanager

#### Default value

```YAML
alertmanager_listen_address: 0.0.0.0:9093
```

### alertmanager_network

Optional docker network to attach

#### Default value

```YAML
alertmanager_network:
```

### alertmanager_oauth2_allowed_groups

List of groups to allow access

#### Default value

```YAML
alertmanager_oauth2_allowed_groups: []
```

#### Example usage

```YAML
alertmanager_oauth2_allowed_groups:
  - /Group1
  - /Group2
  - /Group3
```

### alertmanager_oauth2_client_id

Client ID for OAuth2 authentication

#### Default value

```YAML
alertmanager_oauth2_client_id:
```

### alertmanager_oauth2_client_secret

Client secret for OAuth2 authentication

#### Default value

```YAML
alertmanager_oauth2_client_secret:
```

### alertmanager_oauth2_cookie_secret

Cookie secret used by OAuth2 proxy

#### Default value

```YAML
alertmanager_oauth2_cookie_secret:
```

### alertmanager_oauth2_default_labels

List of default labels to assign to docker on OAuth2 Proxy

#### Default value

```YAML
alertmanager_oauth2_default_labels: []
```

### alertmanager_oauth2_default_publish

List of default port publishing for docker on OAuth2 Proxy

#### Default value

```YAML
alertmanager_oauth2_default_publish: []
```

#### Example usage

```YAML
alertmanager_oauth2_default_publish:
  - 127.0.0.1:9092:9092
```

### alertmanager_oauth2_download

#### Default value

```YAML
alertmanager_oauth2_download: https://github.com/oauth2-proxy/oauth2-proxy/releases/download/v{{
  alertmanager_oauth2_version }}/oauth2-proxy-v{{ alertmanager_oauth2_version }}.linux-amd64.tar.gz
```

### alertmanager_oauth2_enabled

URL of the OAuth2 Proxy to download

#### Default value

```YAML
alertmanager_oauth2_enabled: false
```

### alertmanager_oauth2_extra_labels

List of extra labels to assign to docker on OAuth2 Proxy

#### Default value

```YAML
alertmanager_oauth2_extra_labels: []
```

### alertmanager_oauth2_extra_publish

List of extra port publishing for docker on OAuth2 Proxy

#### Default value

```YAML
alertmanager_oauth2_extra_publish: []
```

#### Example usage

```YAML
alertmanager_oauth2_extra_publish:
  - 127.0.0.1:9092:9092
```

### alertmanager_oauth2_image

Docker image to use for deployment

#### Default value

```YAML
alertmanager_oauth2_image: quay.io/oauth2-proxy/oauth2-proxy:v{{ alertmanager_oauth2_version
  }}
```

### alertmanager_oauth2_keycloak_url

URL of the Keycloak realm

#### Default value

```YAML
alertmanager_oauth2_keycloak_url:
```

### alertmanager_oauth2_listen_address

Listem address for the OAuth2 proxy

#### Default value

```YAML
alertmanager_oauth2_listen_address: 0.0.0.0:9092
```

### alertmanager_oauth2_network

Optional docker network to attach on OAuth2 Proxy

#### Default value

```YAML
alertmanager_oauth2_network: '{{ alertmanager_network }}'
```

### alertmanager_oauth2_provider

Provider for OAuth2 authentication

#### Default value

```YAML
alertmanager_oauth2_provider: keycloak
```

### alertmanager_oauth2_static_groups

List of groups assigned to static users

#### Default value

```YAML
alertmanager_oauth2_static_groups: []
```

### alertmanager_oauth2_static_users

List of users to allow access

#### Default value

```YAML
alertmanager_oauth2_static_users: []
```

#### Example usage

```YAML
alertmanager_oauth2_static_users:
  - username: username1
    password: p455w0rd
  - username: username2
    password: p455w0rd
  - username: username3
    password: p455w0rd
```

### alertmanager_oauth2_upstream

Upstream target for the OAuth2 proxy

#### Default value

```YAML
alertmanager_oauth2_upstream: http://{{ alertmanager_listen_address if alertmanager_installation
  == 'native' else 'alertmanager:9093' }}
```

### alertmanager_oauth2_version

Version of the OAuth2 Proxy to download

#### Default value

```YAML
alertmanager_oauth2_version: 7.4.0
```

### alertmanager_receiver

Standard conect for alerts

#### Default value

```YAML
alertmanager_receiver:
```

### alertmanager_receivers

List of alerting recipients

#### Default value

```YAML
alertmanager_receivers: []
```

#### Example usage

```YAML
alertmanager_receivers:
  - name: mail-devops
    email_configs:
      - to: devops@example.com
        send_resolved: True
```

### alertmanager_routes

List of alerting routes

#### Default value

```YAML
alertmanager_routes: []
```

#### Example usage

```YAML
alertmanager_routes:
  - receiver: mail-devops
    match:
      severity: critical
```

### alertmanager_smtp_from

Sender for emails

#### Default value

```YAML
alertmanager_smtp_from:
```

### alertmanager_smtp_password

Password for SMTP connection

#### Default value

```YAML
alertmanager_smtp_password:
```

### alertmanager_smtp_require_tls

Require TLS for SMTP connection

#### Default value

```YAML
alertmanager_smtp_require_tls: true
```

### alertmanager_smtp_smarthost

Host for SMTP connection

#### Default value

```YAML
alertmanager_smtp_smarthost:
```

### alertmanager_smtp_username

Username for SMTP connection

#### Default value

```YAML
alertmanager_smtp_username:
```

### alertmanager_version

Version of the release to install

#### Default value

```YAML
alertmanager_version: 0.25.0
```

## Discovered Tags

**_alertmanager_**

**_oauth2_**


## Dependencies

- [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)