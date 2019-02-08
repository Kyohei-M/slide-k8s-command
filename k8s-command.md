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

使い方がわからないものは --help で確認

---
### kubectlコマンド

- apply
- config
- create
- delete
- describe
- exec
- get

---
### kubectlコマンド

- logs
- patch
- replace
- scale
- top
- version

etc...

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

例

```console
$ kubectl create -f sample.yaml

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

例

```console
$ kubectl patch pod sample-pod -p \
'{"spec":{"containers":[{"name":"sample","image":"new image"}]}}'

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

- リソース名を指定した削除は行わない

---
### リソース一覧を表示

```console
$ kubectl get [リソースの種類]

```

- リソース名指定で個別表示
- -o wide で追加情報を表示

例

```console
$ kubectl get po,rs,deploy

```

---
### コンテナ上でコマンドを実行

```console
$ kubectl exec -it [Pod名] [コマンド]

```

例

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

- スケールアウト、スケールイン
- 通常はマニフェストの修正を行う

例

```console
$ kubectl scale --replicas=5 deploy/sample-deploy

```

---
### リソース詳細を表示

```console
$ kubectl describe [リソースの種類] [リソース名]

```

- 状態、イベント、リビジョン等の確認

例

```console
$ kubectl describe rs sample-rs

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