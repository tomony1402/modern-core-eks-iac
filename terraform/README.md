# Terraform ディレクトリについて

本ディレクトリでは、AWS 上のインフラリソースを
Terraform により Infrastructure as Code (IaC) として管理する。

## 管理対象（予定）

- VPC
- IAM ロール
- EKS クラスター
- EKS 周辺リソース

## 方針

- 手動でのリソース作成は行わず、Terraform を正とする
- 環境差分はディレクトリまたは変数で管理する
- 実行はローカルではなく、HCP Terraform を利用する想定とする

## 構成方針（予定）


