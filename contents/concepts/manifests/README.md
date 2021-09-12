# Kubernetes Manifests

Kubernetes manifests are specifications of the Kubernetes objects that are represented in YAML or JSON format. It's so typical to write manifest in YAML format, and because of that, we intend to introduce the YAML syntax of the Kubernetes manifests.

<p align="center">
  <img alt="Kubernetes Manifests" src="https://raw.githubusercontent.com/ssbostan/kubernetes-complete-reference/master/assets/contents/concepts/manifests/manifests.png">
</p>

Each object has three main fields, **apiVersion**, **kind**, **metadata**. Most of them, especially all workloads, have **spec** and **status** fields.
