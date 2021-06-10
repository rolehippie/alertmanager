# work

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/alertmanager) [![Testing Build](https://github.com/rolehippie/alertmanager/workflows/testing/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/alertmanager/workflows/readme/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/alertmanager/workflows/galaxy/badge.svg)](https://github.com/rolehippie/alertmanager/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/alertmanager)](https://github.com/rolehippie/alertmanager/blob/master/LICENSE) 

Ansible role to install and configure Alertmanager. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [alertmanager_data_retention](#alertmanager_data_retention)
  * [alertmanager_domain](#alertmanager_domain)
  * [alertmanager_download](#alertmanager_download)
  * [alertmanager_group_by](#alertmanager_group_by)
  * [alertmanager_inhibit_rules](#alertmanager_inhibit_rules)
  * [alertmanager_listen_address](#alertmanager_listen_address)
  * [alertmanager_oauth2_allowed_groups](#alertmanager_oauth2_allowed_groups)
  * [alertmanager_oauth2_client_id](#alertmanager_oauth2_client_id)
  * [alertmanager_oauth2_client_secret](#alertmanager_oauth2_client_secret)
  * [alertmanager_oauth2_cookie_secret](#alertmanager_oauth2_cookie_secret)
  * [alertmanager_oauth2_download](#alertmanager_oauth2_download)
  * [alertmanager_oauth2_enabled](#alertmanager_oauth2_enabled)
  * [alertmanager_oauth2_keycloak_url](#alertmanager_oauth2_keycloak_url)
  * [alertmanager_oauth2_listen_address](#alertmanager_oauth2_listen_address)
  * [alertmanager_oauth2_provider](#alertmanager_oauth2_provider)
  * [alertmanager_oauth2_static_groups](#alertmanager_oauth2_static_groups)
  * [alertmanager_oauth2_static_users](#alertmanager_oauth2_static_users)
  * [alertmanager_oauth2_upstream](#alertmanager_oauth2_upstream)
  * [alertmanager_oauth2_version](#alertmanager_oauth2_version)
  * [alertmanager_receiver](#alertmanager_receiver)
  * [alertmanager_receivers](#alertmanager_receivers)
  * [alertmanager_routes](#alertmanager_routes)
  * [alertmanager_smtp_from](#alertmanager_smtp_from)
  * [alertmanager_smtp_password](#alertmanager_smtp_password)
  * [alertmanager_smtp_require_tls](#alertmanager_smtp_require_tls)
  * [alertmanager_smtp_smarthost](#alertmanager_smtp_smarthost)
  * [alertmanager_smtp_username](#alertmanager_smtp_username)
  * [alertmanager_version](#alertmanager_version)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### alertmanager_data_retention

Data retention for alertmanager state

#### Default value

```YAML
alertmanager_data_retention: 120h
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

### alertmanager_listen_address

Listen address for the alertmanager

#### Default value

```YAML
alertmanager_listen_address: 0.0.0.0:9093
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
alertmanager_oauth2_upstream: http://{{ alertmanager_listen_address }}
```

### alertmanager_oauth2_version

Version of the OAuth2 Proxy to download

#### Default value

```YAML
alertmanager_oauth2_version: 7.1.3
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
alertmanager_version: 0.21.0
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
