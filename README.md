# Kubernetes External DNS for AWS EKS

Terraform module [External DNS with Istio Gateway](https://github.com/kubernetes-sigs/external-dns/blob/master/docs/tutorials/istio.md) for aws.

## Usage

```
module "external-dns-aws" {
  source  = "gitizenme/external-dns-aws/kubernetes"
  version = "1.0.1"

  domain           = "my-domain.com"
  k8s_cluster_name = "cluster-name"
  k8s_replicas         = 2
  hosted_zone_id       = "ROUTE53 ZONE ID"
}
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.12 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |
| kubernetes | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| domain | Domain to add external DNS to | `string` | n/a | yes |
| k8s\_cluster\_name | Current Cluster Name | `string` | n/a | yes |
| hosted\_zone\_id | Route53 Hosted Zone ID | `string` | n/a | yes |
| external\_dns\_version | The AWS External DNS version to use. See https://github.com/kubernetes-sigs/external-dns/releases for available versions | `string` | `"0.7.6"` | no |
| k8s\_cluster\_type | K8s cluster Type | `string` | `"eks"` | no |
| k8s\_namespace | Kubernetes namespace to deploy the AWS External DNS into. | `string` | `"kube-system"` | no |
| k8s\_pod\_labels | Additional labels to be added to the Pods. | `map(string)` | `{}` | no |
| k8s\_replicas | Amount of replicas to be created. | `number` | `1` | no |

## Outputs

| Name | Description |
|------|-------------|
| kubernetes\_deployment | n/a |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
