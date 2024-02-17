vim com.yaml
apiVersion: v1
kind: Pod
metadata:
  name: command-demo
  labels:
    purpose: demonstrate-command
spec:
  containers:
  - name: command-demo-container
    image: debian
    command: ["printenv"]
    args: ["HOSTNAME", "KUBERNETES_PORT"]
  restartPolicy: OnFailure

kubectl apply -f com.yaml
kubectl get pod
kubectl logs command-demo

```
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10 
```

The above command created a deployment named hello minikube using image from google registry 

```
kubectl expose deployment hello-minikube --type=NodePort --port=8080
```
```
minikube service hello-minikube --url
```
