# ECS Fargate Production Infrastructure

## What is this?
Production **ECS Fargate** stack: cluster, services, task defs, ALB, target groups — all in Terraform.

## Why it matters
Fargate = containers without EC2 management. You pay per vCPU-second, AWS handles the host. Knowing how to wire it cleanly is a core modern-AWS skill.

## What you did
- Cluster + per-service task definitions sized to each workload
- ALB with listener rules routing by path/host to different target groups
- CloudWatch log groups per container

## Interview one-liner
"I run our production ECS Fargate fleet — cluster, services, ALB routing, CloudWatch logs, all in Terraform."

## Key concepts
- **Task definition** = container blueprint (vs. the running task)
- **Target group deregistration delay** — the #1 cause of dropped requests
- **Capacity providers** — FARGATE vs. FARGATE_SPOT
