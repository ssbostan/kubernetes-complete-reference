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

This component is responsible for managing Kubernetes resources. Almost every Kubernetes resource has a controller. For example, checking resource state, controlling the application desired state and replicas, applications high availability, checking nodes and applications liveness are some functions and responsibilities of this component. Although each controller is run in a separate process but to reduce complexity, they are all compiled into a single binary and run in a single process. The high availability of the Kube-controller-manager is done by leader election. In simple words, leader election is a mechanism that guarantees only one instance of service is responsible for making decisions. While all other instances are inactive, but they are ready to hold a new election and announcing a new leader when something happens to the current leader. All instances except the leader are locked and cannot make any decision.

> For high availability, run at least two instances of Kube-controller-manager on different servers.

### <a name="kube-scheduler">kube-scheduler:</a>

Where Kubernetes pods should be running is the major responsibility of this component. The scheduler is responsible for selecting eligible nodes to run newly created pods. When a new pod is created by a user or a controller, no nodes are assigned for running that pod, and the scheduler must assign a proper node to run that. Many factors like resource requirements, policy constraints, affinity, and anti-affinity are taken into account for scheduling decisions. In the case of high-availability deployment, this component is just like Kube-controller-manager, and more than one instance can not be active at the same time.

> For high availability, run at least two instances of Kube-scheduler on different servers.

### <a name="cloud-controller-manager">cloud-controller-manager:</a>

This component is a cloud-specific unit that runs where Kubernetes is deployed on the cloud services. The Cloud-controller-manager connects the Kubernetes cluster to the cloud provider API to achieve cloud functionalities. You should note that this component only runs controllers that are specific to your cloud provider. If Kubernetes is deployed on on-premises servers, no instances of this component are run. Each controller is a separate process, but they are all compiled into a single binary and running as a single process to reduce complexity.

> For high availability, run at least two instances of Cloud-controller-manager on different servers.

## <a name="worker-nodes">Worker nodes:</a>

Worker nodes that were formerly called Minions are one of the most important parts of the Kubernetes cluster. They are responsible for running containers. Kubernetes supports various container runtimes and can work with multiple container runtimes at the same time. Each cluster should have at least one worker node to run application containers.

> For high availability scenarios, at least three worker nodes are recommended.

### <a name="kubelet">kubelet:</a>

The kubelet is a most sensitive component in the Kubernetes ecosystem that is responsible for running containers managed by the Kubernetes. This component from one side connects to the Kubernetes API server and from the other side connects to the Container Runtime. It takes Kubernetes PodSpec and ensures that the containers are described in those PodSpec are running and healthy. All other containers that are not created by the Kubernetes are not managed with the kubelet. The kubelet speaks to Container Runtimes through the CRI, Container Runtime Interface. The CRI is a plugin that enables kubelet to use a wide variety of container runtimes without the need to recompile.

### <a name="kube-proxy">kube-proxy:</a>

To be completed.

### <a name="container-runtime">Container Runtime:</a>

To be completed.

