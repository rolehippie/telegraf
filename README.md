# telegraf

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/telegraf)
[![General Workflow](https://github.com/rolehippie/telegraf/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/telegraf/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/telegraf/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/telegraf/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/telegraf/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/telegraf/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/telegraf)](https://github.com/rolehippie/telegraf/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.telegraf-blue)](https://galaxy.ansible.com/rolehippie/telegraf)

Ansible role to install and configure telegraf.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [requires_docker_group](#requires_docker_group)
  - [requires_sudo_group](#requires_sudo_group)
  - [telegraf_aggregators_default](#telegraf_aggregators_default)
  - [telegraf_aggregators_extra](#telegraf_aggregators_extra)
  - [telegraf_collection_jitter](#telegraf_collection_jitter)
  - [telegraf_debug](#telegraf_debug)
  - [telegraf_flush_interval](#telegraf_flush_interval)
  - [telegraf_flush_jitter](#telegraf_flush_jitter)
  - [telegraf_global_tags](#telegraf_global_tags)
  - [telegraf_hostname](#telegraf_hostname)
  - [telegraf_interval](#telegraf_interval)
  - [telegraf_keyring](#telegraf_keyring)
  - [telegraf_logfile](#telegraf_logfile)
  - [telegraf_logfile_rotation_interval](#telegraf_logfile_rotation_interval)
  - [telegraf_logfile_rotation_max_archives](#telegraf_logfile_rotation_max_archives)
  - [telegraf_logfile_rotation_max_size](#telegraf_logfile_rotation_max_size)
  - [telegraf_logtarget](#telegraf_logtarget)
  - [telegraf_metric_batch_size](#telegraf_metric_batch_size)
  - [telegraf_metric_buffer_limit](#telegraf_metric_buffer_limit)
  - [telegraf_omit_hostname](#telegraf_omit_hostname)
  - [telegraf_plugins_default](#telegraf_plugins_default)
  - [telegraf_plugins_extra](#telegraf_plugins_extra)
  - [telegraf_precision](#telegraf_precision)
  - [telegraf_processors_default](#telegraf_processors_default)
  - [telegraf_processors_extra](#telegraf_processors_extra)
  - [telegraf_prometheus_listen](#telegraf_prometheus_listen)
  - [telegraf_prometheus_password](#telegraf_prometheus_password)
  - [telegraf_prometheus_username](#telegraf_prometheus_username)
  - [telegraf_prometheus_version](#telegraf_prometheus_version)
  - [telegraf_quiet](#telegraf_quiet)
  - [telegraf_repo_distribution](#telegraf_repo_distribution)
  - [telegraf_repo_release](#telegraf_repo_release)
  - [telegraf_round_interval](#telegraf_round_interval)
  - [telegraf_templates](#telegraf_templates)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`


## Default Variables

### requires_docker_group

Optionally disable docker group join

#### Default value

```YAML
requires_docker_group: true
```

### requires_sudo_group

Optionally disable sudo group join

#### Default value

```YAML
requires_sudo_group: true
```

### telegraf_aggregators_default

List of default aggregators, combined with extra

#### Default value

```YAML
telegraf_aggregators_default: []
```

#### Example usage

```YAML
telegraf_aggregators_default
  - plugin: foo
    config:
      - option1 = "value1"
      - option2 = "value2"
```

### telegraf_aggregators_extra

List of extra aggregators, combined with default

#### Default value

```YAML
telegraf_aggregators_extra: []
```

#### Example usage

```YAML
telegraf_aggregators_extra
  - plugin: foo
    config:
      - option1 = "value1"
      - option2 = "value2"
```

### telegraf_collection_jitter

Collection jitter is used to jitter the collection by a random amount

#### Default value

```YAML
telegraf_collection_jitter: 0s
```

### telegraf_debug

Log at debug level

#### Default value

```YAML
telegraf_debug: false
```

### telegraf_flush_interval

Default flushing interval for all outputs

#### Default value

```YAML
telegraf_flush_interval: 10s
```

### telegraf_flush_jitter

Jitter the flush interval by a random amount

#### Default value

```YAML
telegraf_flush_jitter: 0s
```

### telegraf_global_tags

List of global tags

#### Default value

```YAML
telegraf_global_tags: []
```

#### Example usage

```YAML
telegraf_global_tags:
  - key: rack
    value: r155
  - key: switch
    value: sw5
```

### telegraf_hostname

Override default hostname

#### Default value

```YAML
telegraf_hostname: '{{ inventory_hostname }}'
```

### telegraf_interval

Default data collection interval for all inputs

#### Default value

```YAML
telegraf_interval: 10s
```

### telegraf_keyring

Path for the repository keyring

#### Default value

```YAML
telegraf_keyring: /usr/share/keyrings/telegraf-archive-keyring.gpg
```

### telegraf_logfile

Name of the file to be logged to when using the file logtarget

#### Default value

```YAML
telegraf_logfile:
```

### telegraf_logfile_rotation_interval

The logfile will be rotated after the time interval specified

#### Default value

```YAML
telegraf_logfile_rotation_interval:
```

### telegraf_logfile_rotation_max_archives

Maximum number of rotated archives to keep, any older logs are deleted

#### Default value

```YAML
telegraf_logfile_rotation_max_archives:
```

### telegraf_logfile_rotation_max_size

The logfile will be rotated when it becomes larger than the specified size

#### Default value

```YAML
telegraf_logfile_rotation_max_size:
```

### telegraf_logtarget

Log target controls the destination for logs

#### Default value

```YAML
telegraf_logtarget: stderr
```

### telegraf_metric_batch_size

Telegraf will send metrics to outputs in batches of this amount

#### Default value

```YAML
telegraf_metric_batch_size: 1000
```

### telegraf_metric_buffer_limit

Maximum number of unwritten metrics per output

#### Default value

```YAML
telegraf_metric_buffer_limit: 10000
```

### telegraf_omit_hostname

If set to True, do no set the host tag in the telegraf agent

#### Default value

```YAML
telegraf_omit_hostname: false
```

### telegraf_plugins_default

List of default plugins, combined with extra

#### Default value

```YAML
telegraf_plugins_default:
  - plugin: net
    config:
      - ignore_protocol_stats = false
      - interfaces =  ["eth*"]
  - plugin: cpu
    config:
      - percpu = true
      - totalcpu = true
      - collect_cpu_time = false
      - report_active = false
  - plugin: disk
    config:
      - ignore_fs = ["tmpfs", "devtmpfs", "devfs"]
  - plugin: conntrack
    config:
      - dirs = ["/proc/sys/net/netfilter"]
  - plugin: docker
    config:
      - endpoint = "unix:///var/run/docker.sock"
      - timeout = "5s"
      - perdevice = true
      - total = true
  - plugin: filestat
    config:
      - files = ["/var/log/**.log"]
  - plugin: ping
    config:
      - count = 3
      - ping_interval = 1.0
      - timeout = 1.0
      - deadline = 10
      - urls = ["google.de"]
  - plugin: netstat
  - plugin: diskio
  - plugin: kernel
  - plugin: mem
  - plugin: processes
  - plugin: swap
  - plugin: system
  - plugin: kernel_vmstat
  - plugin: linux_sysctl_fs
```

### telegraf_plugins_extra

List of extra plugins, combined with default

#### Default value

```YAML
telegraf_plugins_extra: []
```

#### Example usage

```YAML
telegraf_plugins_extra
  - plugin: net
    config:
      - ignore_protocol_stats = false
      - interfaces =  ["eth*"]
```

### telegraf_precision

Precision will be set to the same timestamp order as the collection interval

#### Default value

```YAML
telegraf_precision:
```

### telegraf_processors_default

List of default processors, combined with extra

#### Default value

```YAML
telegraf_processors_default: []
```

#### Example usage

```YAML
telegraf_processors_default
  - plugin: foo
    config:
      - option1 = "value1"
      - option2 = "value2"
```

### telegraf_processors_extra

List of extra processors, combined with default

#### Default value

```YAML
telegraf_processors_extra: []
```

#### Example usage

```YAML
telegraf_processors_extra
  - plugin: foo
    config:
      - option1 = "value1"
      - option2 = "value2"
```

### telegraf_prometheus_listen

Address to listen for Prometheus

#### Default value

```YAML
telegraf_prometheus_listen: 0.0.0.0:9273
```

### telegraf_prometheus_password

Password used by Prometheus

#### Default value

```YAML
telegraf_prometheus_password:
```

### telegraf_prometheus_username

Username used by Prometheus

#### Default value

```YAML
telegraf_prometheus_username:
```

### telegraf_prometheus_version

Metrics version used by the prometheus client output

#### Default value

```YAML
telegraf_prometheus_version: 2
```

### telegraf_quiet

Log only error level messages

#### Default value

```YAML
telegraf_quiet: false
```

### telegraf_repo_distribution

Enforce a specific distribution for repo source

#### Default value

```YAML
telegraf_repo_distribution | default(ansible_distribution) | lower
```

### telegraf_repo_release

Enforce a specific release for repo source

#### Default value

```YAML
telegraf_repo_release | default(ansible_distribution_release)
```

### telegraf_round_interval

Rounds collection interval to interval

#### Default value

```YAML
telegraf_round_interval: true
```

### telegraf_templates

Path to templates loaded into telegraf.d directory

#### Default value

```YAML
telegraf_templates:
```

## Discovered Tags

**_telegraf_**


## Dependencies

- [rolehippie.docker](https://github.com/rolehippie/docker)
- [rolehippie.sudo](https://github.com/rolehippie/sudo)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
