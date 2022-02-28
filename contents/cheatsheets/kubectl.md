# Kubernetes kubectl CLI Cheatsheet

#### Basic Pod Definition
```
apiVersion: v1
kind: pod
metadata:
    name: my_pod
    label: 
	  app: nginx
	  tier: frontend
spec:
   containers: 
	  - name: my-container
	    image: mynginx
```
kubectl create deployment deploy --image=nginx --port=80 -- Imperative way to create deployment file

kubectl get resources -- to view resources
 
kubectl get svc or service -- to view current services in cluster

kubectl describe po pod_name -- to view complete details of pod

kubectl get pods -- to show running pods in cluster

kubectl get pods -o wide 

kubectl describe po mypod

kubectl get pod mypod -o yaml

kubectl get pods --show-labels

kubectl scale --replicas=3 -f deploy.yaml -- to create replicas for any deployment 

kubectl scale --current-replicas=2 --replicas=3 -f deployment/mysql -- to scale up the replicas.. 

kubectl rollout undo deployment/frontend -- Rollback to the previous deployment

kubectl rollout undo deployment/frontend --to-revision=2  -- Roll back to specific version

kubectl apply -f ./manifest.yaml -- To apply changes for the manifest file	

To be completed.
