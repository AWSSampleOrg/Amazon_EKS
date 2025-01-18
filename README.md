https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html

# Resource

## list all objects

```sh
kubectl get "$(kubectl api-resources --verbs=list -o name | tr "\n" "," | sed -e 's/,$//')" -o wide --all-namespaces
```

## describe a object

```sh
kubectl describe ns,no,ing,svc,endpoints,ds,deploy,rs,sts,po,sa,pdb,cj,jobs,sc,pv,pvc --all-namespaces 2>/dev/null
```

## list events sorted by timestamp

```sh
date && kubectl get events --sort-by=.metadata.creationTimestamp --all-namespaces
```

## When a node doesn't join a cluster

```sh
kubectl get svc
kubectl get nodes
kubectl describe configmap -n kube-system aws-auth
```

## When a pod doesn't launch

```sh
kubectl get pods
kubectl get pod <pod name>
kubectl describe pods --all-namespaces=true
kubectl logs <pod name>
```
