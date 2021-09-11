# Kubernetes Pods

A Pod is an atomic ( which means this is the smallest unit ) unit of work in the Kubernetes. In Kubernetes, you manage Pods instead of containers. Each Pod contains one or more containers. The containers that are running in a pod are shared in the network, storage, and lifecycle, and they are all run on the same node. In most cases, above 90%, the one-container-per-pod model is used, and you can think a Pod is a wrapper around the actual container. The multi-container per Pod has advanced use cases, and it's usually used in complex applications.

Pods are ephemeral resources in the Kubernetes. They haven't a self-healing mechanism, and when they are stopped and started again, for any reason, all data that exist in them are removed. If you want to keep your data, you should use persistent storage. Another note that you should consider is when the Pod is stopped and started again, the IP address of it may changes. The Service resource is used to discover pods and enables communicating with them by a persistent IP address and DNS name.

Stopping and starting a pod causes the system to reschedule a new pod. Because of that, the concerns explained above happen.

Because Pods do not have any self-healing mechanism, we rarely create them directly. Instead, we use Controllers like Deployment, ReplicaSet, DaemonSet, etc., that they create and manage Pods for us. These controllers provide various mechanisms like self-healing, high availability, upgrading, etc. For example, when a node that hosts the pod is failed, the controller tells the system to reschedule a new instance of the pod to run on a healthy node. See more information at Workloads topics.

<p align="center">
  <img alt="Kubernetes Pods" src="https://raw.githubusercontent.com/ssbostan/kubernetes-complete-reference/master/assets/contents/concepts/resources/workloads/pods.png">
</p>

 - **Pod 1**: This is a one-container-per-pod model. In most cases, we use this model.
 - **Pod 2**: In this Pod, two containers are running, and the network and lifecycle of them are shared together.
 - **Pod 3**: In this Pod, two containers are running, and the network, storage, and lifecycle of them are shared together.
 - **Pod 4**: This example is like the previous one but on a larger scale.

# Example

Here is a brief example of Pod manifest:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: test
  labels:
    app.kubernetes.io/name: test
    app.kubernetes.io/created-by: kubernetes-complete-reference
spec:
  containers:
    - name: test
      image: alpine:latest
      command: ["echo", "Hello World!"]
  restartPolicy: Never
```
