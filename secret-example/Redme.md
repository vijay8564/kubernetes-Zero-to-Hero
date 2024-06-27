# Step 1: Create a Secret
First, create a Secret manifest file named my-secret.yaml. This file will contain the encoded data.


The data field contains the base64-encoded values of the secret data. You can use the echo command to encode your values:

```python
echo -n 'my-username' | base64
echo -n 'my-password' | base64
```

# Step 2: Apply the Secret
Apply the Secret to your Kubernetes cluster:
```python
kubectl apply -f my-secret.yaml
```

# Step 3: Use the Secret in an Nginx Pod
* Create a Pod manifest file named nginx-pod.yaml that uses the Secret:

 * In this manifest, the env section specifies environment variables for the container. The values for these variables are taken from the Secret.

# Step 4: Apply the Pod Manifest
Apply the Pod manifest to create the Nginx pod:

```python
kubectl apply -f nginx-pod.yaml
```

# Step 5: Verify the Pod
You can verify that the Pod is running and the environment variables are set by using:

```python
kubectl get pods
kubectl describe pod nginx-pod
kubectl exec -it nginx-pod -- printenv | grep USERNAME
kubectl exec -it nginx-pod -- printenv | grep PASSWORD
```