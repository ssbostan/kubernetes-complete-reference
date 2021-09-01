# kubernetes-complete-reference

![Visits Badge](https://badges.pufler.dev/visits/ssbostan/kubernetes-complete-reference)
![GitHub last commit](https://img.shields.io/github/last-commit/ssbostan/kubernetes-complete-reference)
[![GitHub license](https://img.shields.io/github/license/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/network)
[![GitHub issues](https://img.shields.io/github/issues/ssbostan/kubernetes-complete-reference)](https://github.com/ssbostan/kubernetes-complete-reference/issues)

The most complete reference for the **Kubernetes** container orchestration engine.

Copyright 2021 Saeid Bostandoust <ssbostan@linuxmail.org>

# What is Kubernetes?

Kubernetes - aka K8s - is a container orchestration engine for automating deployment, scaling, and management of containerized applications. With Kubernetes, a set of container engines (Docker, Containerd, CRI-O, etc.) that were deployed on various servers (both physical and virtual) can be brought together to manage complex container-based software environments. The set of these servers is called the Kubernetes Cluster. So to speak, the Kubernetes cluster is a set of nodes that can run containers which they managed centrally with an amazing tool called Kubernetes. Kubernetes is a leading container orchestration engine in the current container ecosystem.

## Why we need Kubernetes?

In software environments that use containers, usually microservices, we have many concerns such as storage and network needs, dynamic configuration per run environments, load balancing, application scaling, high availability, etc. Kubernetes is the answer to these concerns. With the Kubernetes platform, all things such as that described above are managed automatically by this great platform. Before Kubernetes, these concerns were solved manually or automatically in scattered tools. With Kubernetes, all of them are done on just one platform.

# Table of Contents:

Kubernetes topics are categorized into these top headers. It may change in the future.

 1. **Kubernetes Concepts**
    - [**Kubernetes Architecture**](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md)
      - [Data plane](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#data-plane)
        - [Etcd cluster](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#data-plane)
      - [Control plane](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#control-plane)
        - [kube-apiserver](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#kube-apiserver)
        - [kube-controller-manager](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#kube-controller-manager)
        - [kube-scheduler](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#kube-scheduler)
        - [cloud-controller-manager](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#cloud-controller-manager)
      - [Worker nodes](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#worker-nodes)
        - [kubelet](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#kubelet)
        - [kube-proxy](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#kube-proxy)
        - [Container Runtime](https://github.com/ssbostan/kubernetes-complete-reference/blob/master/contents/concepts/architecture.md#container-runtime)
 2. **Kubernetes Cheatsheets**
 3. **Kubernetes Best Practices**
 4. **Kubernetes Tools**
 5. **Kubernetes Examples**

# How to contribute:

All contributions are welcomed. Contributors are introduced on the main page of this repository.

Contribution rules will explain as soon as possible.
