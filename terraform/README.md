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


## Terraform 構成方針

- 環境ごとに `envs/` 配下で Terraform 定義を分離
- module は Terraform Registry の公式・実績あるものを優先的に利用
- dev 環境では最小構成を基本とし、段階的に拡張する
