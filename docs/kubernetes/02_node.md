# Node

## 概要
Node は Pod（コンテナ）が実際に動作する Linux サーバ。

## 理解ポイント
- Node は Kubernetes に参加しているサーバ
- Kubernetes は Node に Pod の実行を指示する
- コンテナの実行は Linux カーネル機能に委ねられる

## AWS（EKS）との対応
- Node = EC2 インスタンス
- Node Group = Auto Scaling Group

## ひとことまとめ
Node は Kubernetes における
コンテナの実行基盤となる Linux サーバである。

