# Podを外部へ晒す（Expose）する
## clusterIp
```
kubectl expose pod helloworld \
--type ClusterIP \
--port 8080 \
--name helloworld-clusterip
```
## nodePort
```
kubectl expose pod helloworld \
--type NodePort \
--port 8080 \
--name helloworld-nodeport
```
## loadBalancer
```
kubectl expose pod helloworld \
--type LoadBalancer \
--port 8080 \
--name helloworld-loadbalancer
```

### Tips
```
--targetPort 3306
```
サービスからPodの特定のコンテナにつなぐときは上記のコマンドを使う。