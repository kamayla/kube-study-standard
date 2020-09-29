# k8s勉強会　基礎編
## セットアップ
### localにVagrantが適応されているか確認
```
sysctl -a | grep -E --color 'machdep.cpu.features|VMX'
```
上記のコマンドでVMXの有効を確認し有効でなければ以下でDL And Installしてください。

https://www.virtualbox.org/wiki/Downloads

### minikubeのインストール
```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.8.0/minikube-darwin-amd64 \
  && chmod +x minikube
```

```
sudo mv minikube /usr/local/bin
```

### kubectlのインストール
1.ダウンロードしてください(今回はv1.17.11を特別に指定しています。)
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.17.11/bin/darwin/amd64/kubectl
```
2.kubectlバイナリを実行可能にしてください。
```
chmod +x ./kubectl
```
3.バイナリをPATHの中に移動させてください。
```
sudo mv ./kubectl /usr/local/bin/kubectl
```
4.インストールしたバージョンがv1.17.11あることを確認してください
```
kubectl version --client
```
