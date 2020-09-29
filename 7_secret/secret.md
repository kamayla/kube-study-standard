# Secretのyamlを生成

```
kubectl create secret generic my-secret \
--from-literal=SECRET_KEY1=hogehoge \
--from-literal=SECRET_KEY2=fugafuga \
--dry-run -o yaml > secret.yaml
```
このコマンドを実行すると以下のyamlが生成されます。

```
apiVersion: v1
data:
  SECRET_KEY1: aG9nZWhvZ2U=
  SECRET_KEY2: ZnVnYWZ1Z2E=
kind: Secret
metadata:
  creationTimestamp: null
  name: my-secret
```
ご覧の通りvalueがbase64でエンコードされています。しかしこれっは誰でもdecodeできてしまいます。試しに以下のコマンドを実行してください。

```
echo aG9nZWhvZ2U= | base64 -d
```

hogehogeと結果が返るはずです。
以上の理由から、本番運用ではSecretにDBのパスワードなどを保存するのは良くないそうです。

```
kubectl apply -f secret.yaml
```

```
kubectl describe secret my-secret
```