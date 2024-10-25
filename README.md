# Description

This Ansible role sets up and configures Sonda, a monitoring tool designed to test and track the performance of store nodes. It deploys a Sonda container that publishes messages to a waku node on the same host at fixed intervals and performs store queries to the specified store nodes to confirm message receipt and response accuracy.

# Requirements

This role assumes:
- Docker environment on the target system to run Sonda container. 
- Access to the [nwaku repository](https://github.com/waku-org/nwaku) on GitHub for downloading specific Sonda configuration files is required.
- The list of fleets needs to be accessible at `https://fleets.status.im/`.

# Configuration

The following variables can be customized for configuring Sonda and nwaku:

```yaml

# General settings
nim_waku_sonda_cont_name:       'sonda'                                                                          # Container name for Sonda
nim_waku_sonda_metrics_port:    8004                                                                             # Metrics port for monitoring Sonda
nim_waku_sonda_github_url_path: 'https://raw.githubusercontent.com/waku-org/nwaku/modify-sonda-setup/apps/sonda' # GitHub path for Sonda files
nim_waku_sonda_fleets_url:      'https://fleets.status.im/'                                                      # Fleets information URL
nim_waku_cont_rest_port:        8645                                                                             # Nim waku node rest port

# Required variables from waku node configuration
# nim_waku_pubsub_topics: ~                     # Topics used by Waku pubsub
# nim_waku_cont_name: ~                         # Waku container name
# nim_waku_cluster_id: ~                        # Cluster ID for Waku network
```


