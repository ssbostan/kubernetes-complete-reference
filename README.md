# kubernetes-complete-reference

![Visits Badge](https://badges.pufler.dev/visits/ssbostan/kubernetes-complete-reference)
![GitHub last commit](https://img.shields.io/github/last-commit/ssbostan/kubernetes-complete-reference)
[![GitHub license](https://img.shields.io/github/license/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/network)
[![GitHub issues](https://img.shields.io/github/issues/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/issues)

<p align="center">
 <img alt="Kubernetes Logo" src="https://kubernetes.io/images/kubernetes-horizontal-color.png">
</p>

<p align="center">The completest reference for the <strong>Kubernetes</strong> container orchestration engine.</p>

<p align="center">Created by <a href="https://github.com/ssbostan">ssbostan</a> and contributors.</p>

# What is Kubernetes?

Kubernetes - aka K8s - is a container orchestration engine for automating deployment, scaling, and management of containerized applications. With Kubernetes, a set of container engines (Docker, Containerd, CRI-O, etc.) that were deployed on various servers (both physical and virtual) can be brought together to manage complex container-based software environments. The set of these servers is called the Kubernetes Cluster. So to speak, the Kubernetes cluster is a set of nodes that can run containers which they managed centrally with an amazing tool called Kubernetes. Kubernetes is a leading container orchestration engine in the current container ecosystem.

## Why we need Kubernetes?

In software environments that use containers, usually microservices, we have many concerns such as storage and network needs, dynamic configuration per run environments, load balancing, application scaling, high availability, etc. Kubernetes is the answer to these concerns. With the Kubernetes platform, all things such as that described above are managed automatically by this great platform. Before Kubernetes, these concerns were solved manually or automatically in scattered tools. With Kubernetes, all of them are done on just one platform.

# Table of Contents:

Kubernetes topics are categorized into these top headers. It may change in future.

 1. **Kubernetes Concepts**
    - [**Kubernetes Architecture**](contents/concepts/architecture/README.md)
      - [Data plane](contents/concepts/architecture/README.md#data-plane)
        - [Etcd cluster](contents/concepts/architecture/README.md#data-plane)
      - [Control plane](contents/concepts/architecture/README.md#control-plane)
        - [kube-apiserver](contents/concepts/architecture/README.md#kube-apiserver)
        - [kube-controller-manager](contents/concepts/architecture/README.md#kube-controller-manager)
        - [kube-scheduler](contents/concepts/architecture/README.md#kube-scheduler)
        - [cloud-controller-manager](contents/concepts/architecture/README.md#cloud-controller-manager)
      - [Worker nodes](contents/concepts/architecture/README.md#worker-nodes)
        - [kubelet](contents/concepts/architecture/README.md#kubelet)
        - [kube-proxy](contents/concepts/architecture/README.md#kube-proxy)
        - [Container Runtime](contents/concepts/architecture/README.md#container-runtime)
    - [**Kubernetes Manifests**](contents/concepts/manifests/README.md)
      - [Manifest Metadata (ObjectMeta)](contents/concepts/manifests/README.md#objectmeta)
    - **Kubernetes Resources**
      - **Kubernetes Workloads**
        - [Pods](contents/concepts/resources/workloads/pods.md)
        - [ReplicationController](contents/concepts/resources/workloads/replicationcontroller.md)
        - [ReplicaSet](contents/concepts/resources/workloads/replicaset.md)
        - [Deployment](contents/concepts/resources/workloads/deployment.md)
        - [DaemonSet](contents/concepts/resources/workloads/daemonset.md)
        - [StatefulSet](contents/concepts/resources/workloads/statefulset.md)
        - [Job](contents/concepts/resources/workloads/job.md)
        - [CronJob](contents/concepts/resources/workloads/cronjob.md)
      - **Service Discovery and Load Balancing**
        - [Service](contents/concepts/resources/service/service.md)
        - [Endpoints](contents/concepts/resources/service/endpoints.md)
        - [EndpointSlice](contents/concepts/resources/service/endpointslice.md)
        - [Ingress](contents/concepts/resources/service/ingress.md)
      - **Config and Storage Resources**
        - [ConfigMap](contents/concepts/resources/storage/configmap.md)
        - [Secret](contents/concepts/resources/storage/secret.md)
        - [PersistentVolume](contents/concepts/resources/storage/persistentvolume.md)
        - [PersistentVolumeClaim](contents/concepts/resources/storage/persistentvolumeclaim.md)
        - [StorageClass](contents/concepts/resources/storage/storageclass.md)
      - **High-Availability and Scaling Resources**
        - [PodDisruptionBudget](contents/concepts/resources/scaling/poddisruptionbudget.md)
        - [HorizontalPodAutoscaler](contents/concepts/resources/scaling/horizontalpodautoscaler.md)
        - [VerticalPodAutoscaler](contents/concepts/resources/scaling/verticalpodautoscaler.md)
      - **Authentication and Authorization**
        - [Role](contents/concepts/resources/authz/role.md)
        - [ClusterRole](contents/concepts/resources/authz/clusterrole.md)
        - [RoleBinding](contents/concepts/resources/authz/rolebinding.md)
        - [ClusterRoleBinding](contents/concepts/resources/authz/clusterrolebinding.md)
        - [ServiceAccount](contents/concepts/resources/authz/serviceaccount.md)
      - **Security and Quota Management Resources**
        - [NetworkPolicy](contents/concepts/resources/security/networkpolicy.md)
        - [PodSecurityPolicy](contents/concepts/resources/security/podsecuritypolicy.md)
        - [CertificateSigningRequest](contents/concepts/resources/security/certificatesigningrequest.md)
        - [ResourceQuota](contents/concepts/resources/security/resourcequota.md)
        - [LimitRange](contents/concepts/resources/security/limitrange.md)
      - **Kubernetes Cluster Resources**
        - [Namespace](contents/concepts/resources/cluster/namespace.md)
        - [Node](contents/concepts/resources/cluster/node.md)
 2. **Kubernetes Cheatsheets**
    - [Kubernetes kubectl CLI](contents/cheatsheets/kubectl.md)
    - [Kubernetes YAML Manifests (All-in-one)](contents/cheatsheets/manifests.md)
 3. **Kubernetes Best Practices**
 4. **Kubernetes Tutorials**
    - **External Resources**
      - [Kubernetes Installation Methods The Complete Guide](https://itnext.io/kubernetes-installation-methods-the-complete-guide-1036c860a2b3)
      - [Kubernetes Storage — Part 1 — NFS complete tutorial](https://itnext.io/kubernetes-storage-part-1-nfs-complete-tutorial-75e6ac2a1f77)
      - [Kubernetes Storage — Part 2 — GlusterFS complete tutorial](https://itnext.io/kubernetes-storage-part-2-glusterfs-complete-tutorial-77542c12a602)
 5. **Kubernetes Tools**
    - **Installation Tools**
      - [Kubeadm (Official Installation Tool)](contents/tools/installation/kubeadm.md)
      - [minikube (Local Kubernetes cluster)](contents/tools/installation/minikube.md)
      - [Kubespray (Ansible-based Installer)](contents/tools/installation/kubespray.md)
      - [Kops (Kubernetes Operations)](contents/tools/installation/kops.md)
      - [Charmed Kubernetes (Ubuntu Juju)](contents/tools/installation/charmed-kubernetes.md)
      - [KinD (Kubernetes in Docker)](contents/tools/installation/kind.md)
      - [K3s (Rancher Lightweight Kubernetes)](contents/tools/installation/k3s.md)
      - [K3d (Rancher K3s in Docker)](contents/tools/installation/k3d.md)
      - [MicroK8s (Canonical Zero-ops Kubernetes)](contents/tools/installation/microk8s.md)
      - [RKE (Rancher Kubernetes Engine)](contents/tools/installation/rke.md)
      - [KubeSphere (Distributed Kubernetes Platform)](contents/tools/installation/kubesphere.md)
      - [KubeKey (KubeSphere Installer)](contents/tools/installation/kubekey.md)
      - [Kubermatic (Central Kubernetes Management Platform)](contents/tools/installation/kubermatic.md)
      - [KubeOne (Kubermatic Installer)](contents/tools/installation/kubeone.md)
 6. **Kubernetes Examples**

# How to contribute:

All contributions are welcomed. [CONTRIBUTING.md](CONTRIBUTING.md)

Everyone interested in the Kubernetes can contribute to this reference.

Saeid Bostandoust <ssbostan@linuxmail.org>
