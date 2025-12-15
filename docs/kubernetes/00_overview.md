# Kubernetes 概要

Kubernetes は、コンテナを複数の Linux サーバ上で
安定して実行・管理するための基盤である。

## 役割
- コンテナの実行状態を管理する
- Pod の配置先（Node）を決定する
- 落ちた Pod を再起動する

## 責務の分離
- コンテナの実行: Node 上の Linux（カーネル機能）
- 状態管理と制御: Kubernetes

## ひとことまとめ
Kubernetes はコンテナを直接実行せず、
Linux に実行を委ねるオーケストレーターである。

