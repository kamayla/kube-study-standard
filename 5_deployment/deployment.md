# スケールアップコマンド
```
kubectl scale --replicas=10 deploy helloworld
```
# ローリングアップデート
```
kubectl set image deploy helloworld \
helloworld=gcr.io/google-samples/hello-app:2.0
```
# 一つ前のバージョンにロールバック
```
kubectl rollout undo deploy helloworld
```