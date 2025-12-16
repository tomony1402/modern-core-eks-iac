# Service

## 概要
Service は、Pod の前に立つ安定した通信の入口。

Pod は再作成やスケールにより IP が変化するため、
Pod を直接通信先として利用すると疎通が不安定になる。
Service は Pod の集合に対して固定の接続先を提供する。

## 理解ポイント
- Service は Pod の集合をまとめて扱う
- 通信先は Pod ではなく Service を指定する
- Pod の IP や数が変わっても Service は変わらない

## Podとの関係
- Pod は頻繁に作り直される
- Pod の IP は固定されない
- Service はラベルを使って Pod を識別・案内する

## ひとことまとめ
Service は、変わり続ける Pod に対して
変わらない通信の入口を提供する仕組みである。
