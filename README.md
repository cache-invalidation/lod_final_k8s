# Kubernetes config
## Ubuntu pod
```
kubectl apply -f ubuntu-pod.yaml --kubeconfig=kubeconfig
kubectl expose pod ubuntu --type=NodePort --name=ubuntu-service --target-port=5000 --kubeconfig=kubeconfig
```

Use this command to attach to the pod shell
```
kubectl exec --stdin --tty ubuntu --kubeconfig=kubeconfig -- /bin/bash
```

## Tarantool pod
```
kubectl apply -f tarantool.yaml --kubeconfig=kubeconfig
kubectl expose pod tarantool --target-port=3301 --type=NodePort --kubeconfig=kubeconfig
```
