# Step 1: Create a ConfigMap with the Custom HTML
* Create a ConfigMap manifest file named nginx-configmap.yaml with your custom index.html content.

# Step 2: Apply the ConfigMap
* Apply the ConfigMap to your Kubernetes cluster:
```python
kubectl apply -f nginx-configmap.yaml
```

# Step 3: Create a Pod Manifest to Use the ConfigMap
* Create a Pod manifest file named nginx-pod.yaml that uses the ConfigMap to mount the index.html file into the Nginx container:

* In this manifest, the volumeMounts section mounts the ConfigMap's index.html file into the container's /usr/share/nginx/html/index.html. The subPath specifies which file from the ConfigMap to mount.

# Step 4: Apply the Pod Manifest
* Apply the Pod manifest to create the Nginx pod:
```python
kubectl apply -f nginx-pod.yaml
```
# Step 5: Verify the Pod
* Check that the Pod is running and verify the index.html content:
```python
kubectl get pods
kubectl describe pod nginx-pod
kubectl exec -it nginx-pod -- cat /usr/share/nginx/html/index.html
```
# Step 6: Access the Nginx Server
* To view the changes in the index.html, you can port-forward the Nginx Pod to your local machine:

```python
kubectl port-forward pod/nginx-pod 8080:80
```
* Then, open your browser and navigate to http://localhost:8080 to see the "Hello, World!" message.

* By following these steps, you’ve successfully created a ConfigMap to change the index.html file in an Nginx container to display "Hello, World!".