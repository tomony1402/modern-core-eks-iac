# Pod

## 概要
Pod は Kubernetes における最小の実行単位。

## 理解ポイント
- Pod は 1つ以上のコンテナを含む
- IP はコンテナではなく Pod に付与される
- 多くの場合、1 Pod = 1 コンテナ構成

## Linuxとの対応
- Pod ≒ プロセス実行単位
- Kubernetes は systemd をクラスタに拡張したものと考えると理解しやすい

## ひとことまとめ
Pod は Kubernetes が管理する
「コンテナの実行単位」である。

