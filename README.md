# Kubernetes config
## Ubuntu pod
```
kubectl apply -f ubuntu-pod.yaml --kubeconfig=kubeconfig
kubectl expose pod ubuntu --type=NodePort --name=ubuntu-service --port=5000 --kubeconfig=kubeconfig
kubectl expose pod ubuntu --type=NodePort --name=ubuntu-service-frontend --port=8080 --kubeconfig=kubeconfig
```

Use this command to attach to the pod shell
```
kubectl exec --stdin --tty ubuntu --kubeconfig=kubeconfig -- /bin/bash
```

## Tarantool pod
```
kubectl apply -f tarantool.yaml --kubeconfig=kubeconfig
kubectl expose pod tarantool --name=tarantool-service --port=3301 --type=NodePort --kubeconfig=kubeconfig
```

To initialize database with schemas run the `init.lua` script on the Tarantool pod.
