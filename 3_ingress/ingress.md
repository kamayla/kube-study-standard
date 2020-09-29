# minikubeでIngressをセットアップ
## minikubeのaddonリストを確認
```
minikube addons list
```
## Ingressをenableする
```
minikube addons enable ingress
```
## ingress controllerをチェック
```
kubectl get pods -n kube-system
```