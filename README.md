# Terraform EKS Patterns

Modular Terraform patterns for production AWS EKS platforms.

## Structure

```
modules/
  vpc/           # Multi-AZ VPC, public/private subnets, NAT
  eks/           # EKS cluster, node groups, IRSA
  observability/ # Prometheus/Grafana hooks (placeholder)
examples/
  production/    # Wired example with variables
docs/
  design-decisions.md
```

## Principles

- Composable modules with explicit inputs/outputs
- IRSA for pod-level AWS permissions
- Private subnets for worker nodes
- Tags for cost allocation and ownership
- CI: `terraform fmt`, `validate`, `tflint`, `checkov`

## Related

- [terraform-aws-vpc-module](https://github.com/Jkudjo/terraform-aws-vpc-module) — standalone VPC module

## Status

Scaffold in progress. Modules will be added incrementally with tested examples.
