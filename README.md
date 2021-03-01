# alertmanager

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/alertmanager) [![Build Status](https://img.shields.io/drone/build/rolehippie/alertmanager/master?logo=drone)](https://cloud.drone.io/rolehippie/alertmanager) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/alertmanager)](https://github.com/rolehippie/alertmanager/blob/master/LICENSE) 

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
