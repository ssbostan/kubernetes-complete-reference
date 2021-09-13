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

<p align="center">The most complete reference for the <strong>Kubernetes</strong> container orchestration engine.</p>

<p align="center">Created by <a href="https://github.com/ssbostan">ssbostan</a> and contributors.</p>

# What is Kubernetes?

Kubernetes - aka K8s - is a container orchestration engine for automating deployment, scaling, and management of containerized applications. With Kubernetes, a set of container engines (Docker, Containerd, CRI-O, etc.) that were deployed on various servers (both physical and virtual) can be brought together to manage complex container-based software environments. The set of these servers is called the Kubernetes Cluster. So to speak, the Kubernetes cluster is a set of nodes that can run containers which they managed centrally with an amazing tool called Kubernetes. Kubernetes is a leading container orchestration engine in the current container ecosystem.

## Why we need Kubernetes?

In software environments that use containers, usually microservices, we have many concerns such as storage and network needs, dynamic configuration per run environments, load balancing, application scaling, high availability, etc. Kubernetes is the answer to these concerns. With the Kubernetes platform, all things such as that described above are managed automatically by this great platform. Before Kubernetes, these concerns were solved manually or automatically in scattered tools. With Kubernetes, all of them are done on just one platform.

# Table of Contents:

Kubernetes topics are categorized into these top headers. It may change in the future.

 1. **Kubernetes Concepts**
    - [**Kubernetes Architecture**](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md)
      - [Data plane](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#data-plane)
        - [Etcd cluster](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#data-plane)
      - [Control plane](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#control-plane)
        - [kube-apiserver](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#kube-apiserver)
        - [kube-controller-manager](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#kube-controller-manager)
        - [kube-scheduler](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#kube-scheduler)
        - [cloud-controller-manager](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#cloud-controller-manager)
      - [Worker nodes](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#worker-nodes)
        - [kubelet](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#kubelet)
        - [kube-proxy](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#kube-proxy)
        - [Container Runtime](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture/README.md#container-runtime)
    - [**Kubernetes Manifests**](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/manifests/README.md)
      - [Manifest Metadata (ObjectMeta)](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/manifests/README.md#objectmeta)
    - **Kubernetes Resources**
      - **Kubernetes Workloads**
        - [Pods](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/resources/workloads/pods.md)
        - ReplicationController
        - ReplicaSet
        - Deployment
        - DaemonSet
        - StatefulSet
        - Job
        - CronJob
      - **Service Discovery and Load Balancing**
        - Service
        - Endpoints
        - EndpointSlice
        - Ingress
      - **Config and Storage Resources**
        - ConfigMap
        - Secret
        - PersistentVolume
        - PersistentVolumeClaim
        - StorageClass
      - **High-Availability and Scaling Resources**
        - PodDisruptionBudget
        - HorizontalPodAutoscaler
        - VerticalPodAutoscaler
      - **Authentication and Authorization**
        - Role
        - ClusterRole
        - RoleBinding
        - ClusterRoleBinding
        - ServiceAccount
      - **Security and Quota Management Resources**
        - NetworkPolicy
        - PodSecurityPolicy
        - CertificateSigningRequest
        - ResourceQuota
        - LimitRange
      - **Kubernetes Cluster Resources**
        - Namespace
        - Node
 2. **Kubernetes Cheatsheets**
    - Kubernetes kubectl CLI
    - Kubernetes YAML Manifests (All-in-one)
 3. **Kubernetes Best Practices**
 4. **Kubernetes Tools**
    - **Installation Tools**
      - minikube
      - kind
      - k3s
      - k3d
      - microk8s
      - kubeadm
      - kubespray
      - kops
      - RKE (Rancher Kubernetes Engine)
      - Charmed Kubernetes
      - KubeSphere
      - KubeKey
      - Kubermatic
      - KubeOne
 5. **Kubernetes Examples**

# How to contribute:

All contributions are welcomed. [See Contribution Guide](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/CONTRIBUTING.md)

Everyone interested in the Kubernetes can contribute to this reference.

Saeid Bostandoust <ssbostan@linuxmail.org>
