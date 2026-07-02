# Module design decisions

## VPC before EKS

Network topology is fixed first. EKS module consumes subnet IDs — never creates ad hoc networking.

## IRSA over static credentials

Pods receive IAM roles via OIDC. No long-lived keys in cluster.

## Node groups by workload class

Separate node groups for general workloads vs memory-heavy jobs. Easier rightsizing and cost attribution.

## State and environments

- One state per environment
- No shared state between prod and non-prod
- Remote backend (S3 + DynamoDB lock) required for team use
