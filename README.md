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

