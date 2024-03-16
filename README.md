# Terraform Cloud Linode Firewall

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_linode"></a> [linode](#requirement\_linode) | 2.16.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_linode"></a> [linode](#provider\_linode) | 2.16.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [linode_firewall.this](https://registry.terraform.io/providers/linode/linode/2.16.0/docs/resources/firewall) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_default_inbound_policy"></a> [default\_inbound\_policy](#input\_default\_inbound\_policy) | The default behavior for inbound traffic. This setting can be overridden by updating the inbound.action property of the Firewall Rule. (ACCEPT, DROP) | `string` | `"DROP"` | no |
| <a name="input_default_outbound_policy"></a> [default\_outbound\_policy](#input\_default\_outbound\_policy) | The default behavior for outbound traffic. This setting can be overridden by updating the outbound.action property for an individual Firewall Rule. (ACCEPT, DROP) | `string` | `"ACCEPT"` | no |
| <a name="input_firewall_disabled"></a> [firewall\_disabled](#input\_firewall\_disabled) | If true, the Firewall's rules are not enforced (defaults to false). | `bool` | `false` | no |
| <a name="input_firewall_label"></a> [firewall\_label](#input\_firewall\_label) | This Firewall's unique label. | `string` | n/a | yes |
| <a name="input_inbound_rules"></a> [inbound\_rules](#input\_inbound\_rules) | A firewall rule that specifies what inbound network traffic is allowed. | <pre>map(object({<br>    inbound_rule_label = string<br>    inbound_action     = string<br>    inbound_protocol   = string<br>    inbound_ports      = string<br>    ipv4_inbound_list  = list(string)<br>    ipv6_inbound_list  = list(string)<br>  }))</pre> | n/a | yes |
| <a name="input_outbound_rules"></a> [outbound\_rules](#input\_outbound\_rules) | A firewall rule that specifies what outbound network traffic is allowed. | <pre>map(object({<br>    outbound_rule_label = string<br>    outbound_action     = string<br>    outbound_protocol   = string<br>    outbound_ports      = string<br>    ipv4_outbound_list  = list(string)<br>    ipv6_outbound_list  = list(string)<br>  }))</pre> | n/a | yes |
| <a name="input_target_linodes"></a> [target\_linodes](#input\_target\_linodes) | A list of IDs of Linodes this Firewall should govern it's network traffic for. | `list(string)` | n/a | yes |

## Outputs

No outputs.
<!-- END_TF_DOCS -->