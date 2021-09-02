# Kubernetes Architecture

Each **Kubernetes cluster** is divided into three parts, **Data plane**, **Control plane**, and **Workers**. The data plane, **Etcd**, is responsible for store Kubernetes data like configurations, manifests, resources, etc. The control plane that runs various components is responsible for managing the whole cluster as well as the worker nodes. Worker nodes are responsible for running and managing containers.

## <a name="data-plane">Data plane:</a>

**Etcd** is a distributed key-value store that is used as a Kubernetes database to store Kubernetes data. You should note that the meaning of data does not files! We are talking about the cluster configuration, resources, manifests, etc. Because of the nature of distributed systems, we need to run Etcd in a clustered way. So to speak, An etcd cluster needs a majority of nodes, a quorum, to agree on updates to the cluster state. For a cluster with n members, a quorum is (n/2)+1. For any odd-sized cluster, adding one node will always increase the number of nodes necessary for a quorum. All cluster data are stored in the Etcd database. You should have a proper backup solution for it.

> Minimum viable clusters must have at least three Etcd nodes.

> Production-ready clusters are run with at least five dedicated Etcd nodes.

## <a name="control-plane">Control plane:</a>

The Kubernetes control plane that was formerly called Master is the brain of Kubernetes that manages the whole cluster and worker nodes. A couple of components that each one has a specific function are run in the control plane nodes. These components are described below.

> For high availability, at least two control plane nodes must exist in the cluster.

> Production-ready clusters are run with at least three control plane nodes.

### <a name="kube-apiserver">kube-apiserver:</a>

The API server is the main component of the Kubernetes control plane that exposes the Kubernetes API to clients. All clients (other components and users) are connected to Kube-apiserver to do their works. The API server is the only component that is connected directly to the data plane, Etcd. All data operations should be done through the API server, and this component is responsible for responding to client requests. The API server is a stateless service that can be run in a highly available fashion. Just run several instances and balance traffic between them.

> For high availability, run at least two instances of Kube-apiserver on different servers.

### <a name="kube-controller-manager">kube-controller-manager:</a>

To be completed.

### <a name="kube-scheduler">kube-scheduler:</a>

To be completed.

### <a name="cloud-controller-manager">cloud-controller-manager:</a>

To be completed.

## <a name="worker-nodes">Worker nodes:</a>

Worker nodes that were formerly called Minions are one of the most important parts of the Kubernetes cluster. They are responsible for running containers. Kubernetes supports various container runtimes and can work with multiple container runtimes at the same time. Each cluster should have at least one worker node to run application containers.

> For high availability scenarios, at least three worker nodes are recommended.

### <a name="kubelet">kubelet:</a>

To be completed.

### <a name="kube-proxy">kube-proxy:</a>

To be completed.

### <a name="container-runtime">Container Runtime:</a>

To be completed.

