# Step 1: Create a Namespace
```python
kubectl apply -f namespace.yaml
```

# Step 2: Create a New Context
* You can create a new context by updating your kubeconfig file. This can be done using kubectl config set-context.
```python
kubectl config set-context my-context --namespace=my-namespace --cluster=minikube --user=minikube
```
* my-context: The name of the context you are creating.
```python
choose a name example: <my-context>
```

* my-namespace: The namespace you want to attach to this context.
```python
kubectl get namespace
example: <my-namespace>
```

* my-cluster: The name of the cluster.
```python
kubectl config get-clusters
example: <minikube>
```

* my-user: The user associated with the context.
```python
kubectl config get-users
example: <minikube>
```
# Step 3: Use the New Context

```python
kubectl config use-context my-context
```

# List the pods

```python
kubectl get po
```