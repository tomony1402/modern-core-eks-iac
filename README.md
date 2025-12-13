# modern-core-eks-iac

オンプレミスで構築していたコアサービスをモデルに、
AWS EKS + IaC を用いたモダンな基盤構築を行うポートフォリオ。

## リポジトリ初期化手順

本リポジトリは、ローカル環境で以下の手順により初期化した。

```bash
mkdir modern-core-eks-iac
cd modern-core-eks-iac

git init
git branch -m main

vi README.md

git add README.md
git commit -m "init: add README"

git remote add origin https://github.com/kensho1402/modern-core-eks-iac.git
git push -u origin main
