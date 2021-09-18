# Kubernetes ReplicationController

As was said in the Pods section, Pods are **ephemeral** resources that they haven't any **self-healing** mechanism. One of our expectations is the high availability of the Pods. Furthermore, in many scenarios, we want to deploy several instances of our applications. The ReplicationController resource is one of the well-known Kubernetes resources that is used to achieve those things. With ReplicationController, we can achieve **self-healing**, **scaling**, and **desired state** for our applications.

The ReplicationController is watching for any changes in the selected Pods, and it's responsible for making them available based on the desired state that is considered by the user. Three important things should be described in its manifest, the **replicas**, **selector**, and **template**. All Pods that are selected by the ReplicationController are controlled directly with that, and they work as a child of their ReplicationController object. Let's describe the ReplicationController manifest fields that are introduced above:

 - **replicas**: It's a numeric value that shows the desired state. The ReplicationController makes sure that the instance of the running Pods which are selected based on the **selector** field is equal to this number.

 - **selector**: It's a key-value dictionary that the ReplicationController uses to find Pods. The desired state is achieved based on this field. ReplicationController counts the Pods that their Labels are matched to this field and determines the current state.

 - **template**: It contains PodSpec, the specification of the pod. The desired state is achieved by creating new pods that are based on this specification. Please note that the labels of the pod that specify in this field should be the same as the labels that are specified in the **selector** field. The manifest of this field is the same as the Pod manifest.

# Example

Here is an example of the ReplicationController manifest:

```yaml
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx-rc
  labels:
    app.kubernetes.io/name: nginx
    app.kubernetes.io/resource: rc
    app.kubernetes.io/part-of: kubernetes-complete-reference
    app.kubernetes.io/created-by: ssbostan
spec:
  replicas: 3
  selector:
    app.kubernetes.io/name: nginx
    app.kubernetes.io/resource: pod
    app.kubernetes.io/part-of: kubernetes-complete-reference
    app.kubernetes.io/created-by: ssbostan
  template:
    metadata:
      labels:
        app.kubernetes.io/name: nginx
        app.kubernetes.io/resource: pod
        app.kubernetes.io/part-of: kubernetes-complete-reference
        app.kubernetes.io/created-by: ssbostan
    spec:
      restartPolicy: Always
      containers:
        - name: nginx
          image: nginx:latest
          ports:
            - containerPort: 80
```
