# dev 環境について

本ディレクトリは、Terraform によるインフラ構成を
検証・試行するための開発環境（dev）を想定している。

## 目的

- Terraform の構成検証
- module 設計の試行
- 破壊的変更を含む apply / destroy の実施

## prod 環境との違い

- dev 環境は破棄・再作成を前提とする
- 本番相当の可用性や冗長性は考慮しない
- 本番環境（prod）に適用する前の確認用途とする

## 運用方針

- `terraform apply` は本ディレクトリ配下で実行する
- 本ディレクトリの state は dev 専用とする
- dev 環境はコストを最小限に抑える構成とする


## 現在の構成

- VPC CIDR: 10.0.0.0/16
- Availability Zone: ap-northeast-1a / ap-northeast-1c
- public subnet: 外部公開（ALB 等）用
- private subnet: EKS Node / Pod 配置用

## 設計判断

- dev 環境のため NAT Gateway は作成していない
- private subnet はインターネットへの直接通信を持たない
- `public_subnets` を指定したため、Internet Gateway は module 側で自動作成される
- `terraform plan` により、想定どおりのリソースが作成されることを確認済み

