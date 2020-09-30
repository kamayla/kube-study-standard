# IngressのHTTPS化
SSLターミネーションの設定はSecretを作成する必要がある。以下が作成例。

```
kubectl create secret tls ingress-tls --cert=192.168.64.6.pem --key=192.168.64.6-key.pem
```

keyの作成にはmkcertが便利

install

```
brew install mkcert
```

認証局作成

```
mkcert -install
```

証明書発行

```
mkcert sample.co.jp
```

# ストレステスト
まずはmetrics-serverをenable。
HorizontalPodAutoscalerはこのmetrics-serverの集計を元にPodをオートスケールします。

リスト確認

```
minikube addons list
```

enableする

```
minikube addons enable metrics-server
```

metrics-server podが起動しているか確認

```
kubectl get pod,svc -n kube-system
```

これを済ませると以下のコマンドが使えます

```
kubectl top pod
kubectl top node
```

## abコマンドでストレステスト

```
ab -n [総リクエスト数] -c [同時リクエスト数] [URL]
```


