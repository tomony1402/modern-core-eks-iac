# Deployment

## 概要
Deployment は、Pod の **あるべき状態（desired state）** を宣言し、
その状態を維持するための Kubernetes リソース。

Pod は壊れる前提のため、Pod を直接管理せず、
Deployment を通して管理する。

---

## 理解ポイント
- Deployment は Pod の数や更新方針を管理する
- Pod が減ると、自動で新しい Pod を作成する
- Pod は Deployment の定義をもとに作られる

---

## Podとの関係
- Pod は個体として管理されない
- Deployment は「同じ役割の Pod を何個動かすか」を管理する
- Pod は結果として作られる存在

---

## Kubernetesとの関係
- Deployment に宣言された状態をもとに、
  Kubernetes が実際の Pod の状態を監視する
- Pod の数が足りなければ、
  Node（kubelet）に Pod 作成を指示する

---

## ひとことまとめ
Deployment は、Pod を直接扱わず、  
「あるべき状態」を宣言して維持する仕組みである。

