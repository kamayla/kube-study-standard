# ConfigMapマニフェストを生成

```
kubectl create configmap my-config \
--from-literal=TEST_ENV=Hello_World \
--dry-run \
-o yaml > configmap.yaml
```

# yamlからconfigMap生成

```
kubectl apply -f configmap.yaml
```

# ConfigMapの詳細を表示

```
kubectl describe configmap my-config
```