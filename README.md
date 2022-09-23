<!-- BEGIN_TF_DOCS -->
[![Tests](https://github.com/netascode/terraform-aci-scaffolding/actions/workflows/test.yml/badge.svg)](https://github.com/netascode/terraform-aci-scaffolding/actions/workflows/test.yml)

# Terraform ACI IP SLA Policy

Description

Location in GUI:
`Tenants` » `Policies` » `Protocol` » `IP SLA` » `IP SLA Monitoring Policies`

## Examples

```hcl
module "aci_ip_sla_policy" {
  source  = "netascode/ip_sla_policy/aci"
  version = ">= 0.0.1"

  name        = "ABC"
  description = "My Description"
  tenant      = "TEN1"
  multiplier  = 10
  frequency   = 120
  sla_type    = "tcp"
  port        = 65001
}
```

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0.0 |
| <a name="requirement_aci"></a> [aci](#requirement\_aci) | >= 2.0.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aci"></a> [aci](#provider\_aci) | >= 2.0.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_name"></a> [name](#input\_name) | IP SLA Policy name. | `string` | n/a | yes |
| <a name="input_description"></a> [description](#input\_description) | IP SLA Policy description. | `string` | `""` | no |
| <a name="input_tenant"></a> [tenant](#input\_tenant) | IP SLA Policy Tenant's name. | `string` | n/a | yes |
| <a name="input_multiplier"></a> [multiplier](#input\_multiplier) | IP SLA Policy multiplier. | `number` | `3` | no |
| <a name="input_frequency"></a> [frequency](#input\_frequency) | IP SLA Policy frequency. | `number` | `60` | no |
| <a name="input_port"></a> [port](#input\_port) | IP SLA Policy port. | `number` | `0` | no |
| <a name="input_sla_type"></a> [sla\_type](#input\_sla\_type) | IP SLA Policy type. | `string` | `"icmp"` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_dn"></a> [dn](#output\_dn) | Distinguished name of `fvIPSLAMonitoringPol` object. |
| <a name="output_name"></a> [name](#output\_name) | IP SLA Policy name. |

## Resources

| Name | Type |
|------|------|
| [aci_rest_managed.fvIPSLAMonitoringPol](https://registry.terraform.io/providers/CiscoDevNet/aci/latest/docs/resources/rest_managed) | resource |
<!-- END_TF_DOCS -->