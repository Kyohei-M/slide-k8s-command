name: inverse
layout: true
class: center, middle, inverse

---
# Kubernetes入門

---
# コマンド編

---
layout: false
### 対象者

- Kubernetes未経験者

---
### 参考書籍

<center><img src="https://images-na.ssl-images-amazon.com/images/I/71F%2BqeYXNgL.jpg" width=45%></center>

---
### 参考サイト

公式

<https://kubernetes.io/docs/reference/kubectl/>

---
class: center, middle, inverse
# kubectl
---
### kubectl？

Kubernetesのコマンドを実行するCLIツール

---

### シンタックス

```console
kubectl [command] [TYPE] [NAME] [flags]
```

---
### kubectlコマンド

- apply
- config
- create
- delete
- describe
- exec

---
### kubectlコマンド

- get
- logs
- patch
- replace
- scale
- top
- version

---
### バージョン確認

```console
$ kubectl version

```

---
### リソース作成

```console
$ kubectl create -f [リソース定義ファイル]

```

---
### リソース差し替え

```console
$ kubectl replace -f [リソース定義ファイル]

```

---
### リソース更新

```console
$ kubectl patch [リソースの種類]/[リソース名] \
-p [更新後内容]

```

---
### リソース定義を適用

```console
$ kubectl apply -f [リソース定義ファイル]

```

- create, replace, patchを合わせたような機能

---
### リソース削除

```console
$ kubectl delete -f [リソース定義ファイル]

```

---
### リソース一覧を表示

```console
$ kubectl get [po,rs,deploy...]

```

---
### コンテナに接続

```console
$ kubectl exec -it [Pod名] /bin/bash

```

---
### ログの確認

```console
$ kubectl logs [Pod名]

```

---
### リソース消費量確認

```console
$ kubectl top [pod | node]

```

---
### サイズを変更

```console
$ kubectl scale --replicas=n [リソースの種類]/[リソース名]

```

---
### リソース詳細を表示

```console
$ kubectl describe [リソースの種類] [リソース名]

```

---
### 設定の変更

```console
$ kubectl config [サブコマンド]
```

- kubeconfigファイルを修正

---
class: center, middle, inverse
# デモ