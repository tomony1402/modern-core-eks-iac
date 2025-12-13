# Git リポジトリ初期化手順

本ドキュメントでは、本リポジトリを作成する際に実施した
Git の初期化および GitHub との連携手順をまとめる。

---

## ローカルリポジトリ作成

```bash
mkdir modern-core-eks-iac
cd modern-core-eks-iac

git init
git branch -m main

#README 作成と初回コミット

vi README.md
git add README.md
git commit -m "init: add README"

#GitHub リポジトリとの連携（HTTPS）
git remote add origin https://github.com/kensho1402/modern-core-eks-iac.git
git push -u origin main

#GitHub 接続方式を SSH に変更

git remote set-url origin git@github.com:kensho1402/modern-core-eks-iac.git
git push

