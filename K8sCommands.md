# Kubernetes Commands

## List Pods

```
kubectl get pods
```

## Remove a Pod

```
kubectl delete pod <pod-name>
```

## List Deployments

```
kubectl get deployment
```

## List Services

```
kubectl get service
```

## Copy File from a Pod

```
kubectl cp <podname>:<filePathInPod> <localPathIncluding filename>
```


## Current Context

```
kubectl config current-context
```

## Cluster Info

```
kubectl cluster-info
```

## Get Pod Logs

```
kubectl logs <podName>
```

## Get Init Logs

```
kubectl logs <podName> -c <initName>
```

## Shell into a Pod

```
kubectl exec -ti <podName> -- bash
```

## Helm

### Show Releases

```
helm list -a
```

### Delete a Release

```
helm delete <releasename> --purge
```

### Create helm files

```
helm create <name>
```


