# 1. ディレクトリ作成と移動
mkdir modern-core-eks-iac
cd modern-core-eks-iac

# 2. ローカルを初期化
git init
git branch -m main

# 3. GitHub リポジトリと連携（最初からSSHがおすすめ！）
git remote add origin git@github.com:kensho1402/modern-core-eks-iac.git

# 4. 【重要】GitHub 側の .gitignore を自分の手元に強制的に合流させる
# これで GitHub 側の歴史が自分の手元に入ってきます
git pull origin main --allow-unrelated-histories

# 5. README 作成とコミット
vi README.md
git add README.md
git commit -m "init: add README"

# 6. プッシュ
# 既に pull で繋がっているので、エラーなく通ります
git push -u origin main



#GitHub リポジトリとの連携（HTTPS）
git remote add origin https://github.com/kensho1402/modern-core-eks-iac.git
git push -u origin main

#GitHub 接続方式を SSH に変更

git remote set-url origin git@github.com:kensho1402/modern-core-eks-iac.git
git push

