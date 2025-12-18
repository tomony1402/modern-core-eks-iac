# Label / Selector

## 概要
Label / Selector は、  
**Kubernetes が Pod を直接指定せず、役割ごとにまとめて扱うための仕組み**。

Pod は再作成されるため名前や IP が変わるが、  
Label を使うことで「同じ役割の Pod」を識別できる。

---

## Label とは
- Pod などのリソースに付ける **タグ（名札）**
- key=value の形式で表現する
- 機能はなく、役割を表すための情報

### 例
```text
app=web
env=dev

