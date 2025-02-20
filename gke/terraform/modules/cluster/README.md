<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | ~> 1.3 |
| <a name="requirement_google"></a> [google](#requirement\_google) | 4.80.0 |
| <a name="requirement_google-beta"></a> [google-beta](#requirement\_google-beta) | 4.80.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_google"></a> [google](#provider\_google) | 4.80.0 |
| <a name="provider_google-beta"></a> [google-beta](#provider\_google-beta) | 4.80.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_node_group_monitoring"></a> [node\_group\_monitoring](#module\_node\_group\_monitoring) | ../broker-node-pool | n/a |
| <a name="module_node_group_prod100k"></a> [node\_group\_prod100k](#module\_node\_group\_prod100k) | ../broker-node-pool | n/a |
| <a name="module_node_group_prod10k"></a> [node\_group\_prod10k](#module\_node\_group\_prod10k) | ../broker-node-pool | n/a |
| <a name="module_node_group_prod1k"></a> [node\_group\_prod1k](#module\_node\_group\_prod1k) | ../broker-node-pool | n/a |

## Resources

| Name | Type |
|------|------|
| [google-beta_google_container_cluster.cluster](https://registry.terraform.io/providers/hashicorp/google-beta/4.80.0/docs/resources/google_container_cluster) | resource |
| [google_container_node_pool.system](https://registry.terraform.io/providers/hashicorp/google/4.80.0/docs/resources/container_node_pool) | resource |
| [google_service_account.cluster](https://registry.terraform.io/providers/hashicorp/google/4.80.0/docs/resources/service_account) | resource |
| [google-beta_google_container_engine_versions.this](https://registry.terraform.io/providers/hashicorp/google-beta/4.80.0/docs/data-sources/google_container_engine_versions) | data source |
| [google_compute_zones.available](https://registry.terraform.io/providers/hashicorp/google/4.80.0/docs/data-sources/compute_zones) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | The name of the cluster and name (or name prefix) for all other infrastructure. | `string` | n/a | yes |
| <a name="input_kubernetes_api_authorized_networks"></a> [kubernetes\_api\_authorized\_networks](#input\_kubernetes\_api\_authorized\_networks) | The list of CIDRs that can access the Kubernetes API, in addition to the bastion host and worker nodes (which are added by default). | `list(string)` | `[]` | no |
| <a name="input_kubernetes_api_public_access"></a> [kubernetes\_api\_public\_access](#input\_kubernetes\_api\_public\_access) | When set to true, the Kubernetes API is accessible publically from the provided authorized networks. | `bool` | `false` | no |
| <a name="input_kubernetes_version"></a> [kubernetes\_version](#input\_kubernetes\_version) | The kubernetes version to use. Only used a creation time, ignored once the cluster exists. | `string` | n/a | yes |
| <a name="input_master_ipv4_cidr_block"></a> [master\_ipv4\_cidr\_block](#input\_master\_ipv4\_cidr\_block) | The CIDR used to assign IPs to the Kubernetes API endpoints. | `string` | n/a | yes |
| <a name="input_max_pods_per_node_messaging"></a> [max\_pods\_per\_node\_messaging](#input\_max\_pods\_per\_node\_messaging) | The maximum number of pods per worker node for the messaging node pools. | `number` | `8` | no |
| <a name="input_max_pods_per_node_system"></a> [max\_pods\_per\_node\_system](#input\_max\_pods\_per\_node\_system) | The maximum number of pods per worker node for the system node pool. | `number` | `16` | no |
| <a name="input_network_name"></a> [network\_name](#input\_network\_name) | The name of the network where the cluster will reside. | `string` | n/a | yes |
| <a name="input_node_pool_max_size"></a> [node\_pool\_max\_size](#input\_node\_pool\_max\_size) | The maximum number of worker nodes for the messaging node pools. | `string` | `20` | no |
| <a name="input_project"></a> [project](#input\_project) | The GCP project that the cluster will reside in. | `string` | n/a | yes |
| <a name="input_region"></a> [region](#input\_region) | The GCP region that the cluster will reside in. | `string` | n/a | yes |
| <a name="input_secondary_cidr_range_pods"></a> [secondary\_cidr\_range\_pods](#input\_secondary\_cidr\_range\_pods) | The secondary CIDR for the cluster's pods. | `string` | n/a | yes |
| <a name="input_secondary_cidr_range_services"></a> [secondary\_cidr\_range\_services](#input\_secondary\_cidr\_range\_services) | The secondary CIDR for the cluster's services. | `string` | n/a | yes |
| <a name="input_subnetwork_name"></a> [subnetwork\_name](#input\_subnetwork\_name) | The name of the subnetwork where the cluster will reside. | `string` | n/a | yes |

## Outputs

No outputs.
<!-- END_TF_DOCS -->