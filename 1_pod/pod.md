# helloworldPodのYaml作成コマンド
```
kubectl run \
--restart Never
--image gcr.io/google-samples/hello-app:1.0 \
--port 8080 \
--dry-run \
-o yaml > pod_helloworld.yaml
```

# curl起動コマンド

```
kubectl run \
--restart Never \
--image curlimages/curl:7.68.0 \
-it --rm curl sh
```

--rm はプロセス終了と共にコンテナを破棄。