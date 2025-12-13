# ADR-001: VPC 構築に terraform-aws-modules/vpc を採用する

## ステータス
Accepted

## 背景
EKS 基盤を構築するにあたり、AWS VPC を Terraform により管理する必要がある。
VPC は他のリソース（EKS, ALB, NAT Gateway 等）の基盤となるため、
保守性と実績のある構成が求められる。

## 検討した選択肢
- aws_vpc / aws_subnet などを用いた自作実装
- Terraform Registry で公開されている VPC module の利用

## 採用理由
- Terraform Registry で広く利用されており、実績が豊富
- EKS 利用を前提としたサブネット構成を容易に実現できる
- 可読性が高く、将来的な拡張・保守がしやすい

## 参照
- Terraform Registry:
  https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws
- GitHub Repository:
  https://github.com/terraform-aws-modules/terraform-aws-vpc

