# Pod

A Pod is an atomic ( which means this is the smallest unit ) unit of work in the Kubernetes. In Kubernetes, you manage Pods instead of containers. Each Pod contains one or more containers. The containers that are running in a pod are shared in the network, storage, and lifecycle, and they are all run on the same node. In most cases, above 90%, the one-container-per-pod model is used, and you can think a Pod is a wrapper around the actual container. The multi-container per Pod has advanced use cases, and it's usually used in complex applications.
