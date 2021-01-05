# Terraform Modules Template

[![tflint](https://github.com/applike/terraform-aws-label/workflows/tflint/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Atflint+event%3Apush+branch%3Amaster)
[![tfsec](https://github.com/applike/terraform-aws-label/workflows/tfsec/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Atfsec+event%3Apush+branch%3Amaster)
[![yamllint](https://github.com/applike/terraform-aws-label/workflows/yamllint/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Ayamllint+event%3Apush+branch%3Amaster)
[![misspell](https://github.com/applike/terraform-aws-label/workflows/misspell/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Amisspell+event%3Apush+branch%3Amaster)
[![pre-commit-check](https://github.com/applike/terraform-aws-label/workflows/pre-commit-check/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Apre-commit-check+event%3Apush+branch%3Amaster)
[![release](https://github.com/applike/terraform-aws-label/workflows/release/badge.svg?branch=master&event=push)](https://github.com/applike/terraform-aws-label/actions?query=workflow%3Arelease+event%3Apush+branch%3Amaster)
![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/applike/terraform-aws-label)
[![License](https://img.shields.io/github/license/applike/terraform-aws-label)](https://github.com/applike/terraform-aws-label/blob/master/LICENSE)

## Example
```hcl
module "label" {
  source  = "applike/label/aws"
  version = "1.0.0"
}
```
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.14.0 |

## Providers

No provider.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| additional\_tag\_map | Additional tags for appending to tags\_as\_list\_of\_maps. Not added to `tags`. | `map(string)` | `{}` | no |
| application | Solution application, e.g. 'app' or 'jenkins' | `string` | `null` | no |
| attributes | Additional attributes (e.g. `1`) | `list(string)` | `[]` | no |
| context | Single object for setting entire context at once.<br>See description of individual variables for details.<br>Leave string and numeric variables as `null` to use default value.<br>Individual variable settings (non-null) override settings in context object,<br>except for attributes, tags, and additional\_tag\_map, which are merged. | <pre>object({<br>    enabled             = bool<br>    project             = string<br>    environment         = string<br>    family              = string<br>    application         = string<br>    delimiter           = string<br>    attributes          = list(string)<br>    tags                = map(string)<br>    additional_tag_map  = map(string)<br>    regex_replace_chars = string<br>    label_order         = list(string)<br>    id_length_limit     = number<br>  })</pre> | <pre>{<br>  "additional_tag_map": {},<br>  "application": null,<br>  "attributes": [],<br>  "delimiter": null,<br>  "enabled": true,<br>  "environment": null,<br>  "family": null,<br>  "id_length_limit": null,<br>  "label_order": [],<br>  "project": null,<br>  "regex_replace_chars": null,<br>  "tags": {}<br>}</pre> | no |
| delimiter | Delimiter to be used between `project`, `environment`, `family`, `application` and `attributes`.<br>Defaults to `-` (hyphen). Set to `""` to use no delimiter at all. | `string` | `null` | no |
| enabled | Set to false to prevent the module from creating any resources | `bool` | `null` | no |
| environment | Environment, e.g. 'uw2', 'us-west-2', OR 'prod', 'staging', 'dev', 'UAT' | `string` | `null` | no |
| family | Family, e.g. 'prod', 'staging', 'dev', OR 'source', 'build', 'test', 'deploy', 'release' | `string` | `null` | no |
| id\_length\_limit | Limit `id` to this many characters.<br>Set to `0` for unlimited length.<br>Set to `null` for default, which is `0`.<br>Does not affect `id_full`. | `number` | `null` | no |
| label\_order | The naming order of the id output and Name tag.<br>Defaults to ["project", "environment", "family", "application", "attributes"].<br>You can omit any of the 5 elements, but at least one must be present. | `list(string)` | `null` | no |
| project | Project, which could be your organization name or abbreviation, e.g. 'eg' or 'cp' | `string` | `null` | no |
| regex\_replace\_chars | Regex to replace chars with empty string in `project`, `environment`, `family` and `application`.<br>If not set, `"/[^a-zA-Z0-9-]/"` is used to remove all characters other than hyphens, letters and digits. | `string` | `null` | no |
| tags | Additional tags (e.g. `map('BusinessUnit','XYZ')` | `map(string)` | `{}` | no |

## Outputs

| Name | Description |
|------|-------------|
| additional\_tag\_map | The merged additional\_tag\_map |
| application | Normalized application |
| attributes | List of attributes |
| context | Merged but otherwise unmodified input to this module, to be used as context input to other modules.<br>Note: this version will have null values as defaults, not the values actually used as defaults. |
| delimiter | Delimiter between `project`, `environment`, `family`, `application` and `attributes` |
| enabled | True if module is enabled, false otherwise |
| environment | Normalized environment |
| family | Normalized family |
| id | Disambiguated ID restricted to `id_length_limit` characters in total |
| id\_full | Disambiguated ID not restricted in length |
| id\_length\_limit | The id\_length\_limit actually used to create the ID, with `0` meaning unlimited |
| label\_order | The naming order actually used to create the ID |
| normalized\_context | Normalized context of this module |
| project | Normalized project |
| regex\_replace\_chars | The regex\_replace\_chars actually used to create the ID |
| tags | Normalized Tag map |
| tags\_as\_list\_of\_maps | Additional tags as a list of maps, which can be used in several AWS resources |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
