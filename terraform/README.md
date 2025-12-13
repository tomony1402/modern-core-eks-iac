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


## Terraform 構成方針

- 環境ごとに `envs/` 配下で Terraform 定義を分離
- module は Terraform Registry の公式・実績あるものを優先的に利用
- dev 環境では最小構成を基本とし、段階的に拡張する

## VPC モジュールについて

本リポジトリでは、AWS VPC の構築に  
Terraform Registry の公式モジュール  
`terraform-aws-modules/vpc/aws` を利用している。

### 採用理由

- VPC / Subnet / RouteTable / IGW / NAT Gateway など
  基本構成を一括で管理できる
- 多くの実績があり、EKS 構成との相性が良い
- low-level な `resource` を直接書かずに済み、
  設計意図に集中できる

### モジュールの基本的な挙動

本モジュールでは、以下のリソースが **自動的に作成・関連付け** される。

- VPC
- Internet Gateway（IGW）
- Public / Private Subnet
- Route Table
- Route Table Association

### Public / Private Subnet の考え方

Terraform では、Subnet 自体に  
「public / private」という属性は存在しない。

本モジュールでは **ルート定義によって役割が決まる**。

| Subnet 種別 | 0.0.0.0/0 の行き先 | 結果 |
|------------|------------------|------|
| public     | Internet Gateway | インターネット通信可能 |
| private    | なし / NAT GW    | 直接は不可 |

### Public Subnet の挙動

`public_subnets` を指定すると、以下が自動で行われる。

- Internet Gateway の作成
- Public 用 Route Table の作成
- `0.0.0.0/0 → IGW` のルート追加
- Public Subnet への Route Table 関連付け

結果として、Public Subnet に配置されたリソースは  
インターネット通信が可能となる。

### Private Subnet の挙動

`private_subnets` に対しては  
Internet Gateway へのルートは作成されない。

- `enable_nat_gateway = true` の場合  
  → NAT Gateway 経由で外部通信可能
- 無効の場合  
  → 完全なプライベートネットワーク

### 設計上の注意点

- 本モジュールは内部的に多くの `resource` を含むため、
  `terraform plan` を確認することで挙動を理解する
- ブラックボックスにせず、
  必要に応じて module の source code を参照する

