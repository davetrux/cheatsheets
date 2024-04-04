# Kubernetes Commands

## List Pods

```bash
kubectl get pods
```

## Remove a Pod

```bash
kubectl delete pod <pod-name>
```

## List Deployments

```bash
kubectl get deployment
```

## List Services

```bash
kubectl get service
```

## Copy File from a Pod

```bash
kubectl cp <podname>:<filePathInPod> <localPathIncluding filename>
```


## Current Context

```bash
kubectl config current-context
```

## Cluster Info

```bash
kubectl cluster-info
```

## Get Pod Logs

```bash
kubectl logs <podName>
```

## Get Init Logs

```bash
kubectl logs <podName> -c <initName>
```

## Shell into a Pod

```bash
kubectl exec -ti <podName> -- bash
```

## Port forward a pod

```bash
kubectl port-forward <podname> <localport>:<podport>
```

## Force a Deployment to Re-pull Image
```bash
kubectl rollout restart deployment <deploymentname>
```

## Helm

### Show Releases

```bash
helm list -a
```

### Delete a Release

```bash
helm delete <releasename> --purge
```

### Create helm files

```bash
helm create <name>
```
