# Kubernetes Manifests

Kubernetes manifests are specifications of the Kubernetes objects that are represented in YAML or JSON format. It's so typical to write manifest in YAML format, and because of that, we intend to introduce the YAML syntax of the Kubernetes manifests.

<p align="center">
  <img alt="Kubernetes Manifests" src="https://raw.githubusercontent.com/ssbostan/kubernetes-complete-reference/master/assets/contents/concepts/manifests/manifests.png">
</p>

Each object has three main fields, **apiVersion**, **kind**, **metadata**. Most of them, especially all workloads, have **spec** and **status** fields.

 - **apiVersion**: Points to the API version that exists in your Kubernetes cluster and has the desired resource.
 - **kind**: Specifies the wanted Kubernetes resource that exists in the selected API version.
 - **metadata**: An instance of the ObjectMeta dictionary that contains the object specifications.
 - **spec**: It contains the actual specifications of the object. Each Kubernetes resource has its own spec.
 - **status**: The current status of the object. This field is read-only, and the Kubernetes core can only update that.
