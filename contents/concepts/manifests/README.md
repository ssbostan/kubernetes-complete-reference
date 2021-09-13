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

# <a name="objectmeta">ObjectMeta metadata</a>

Each Kubernetes object that is related to a persisted resource must have ObjectMeta metadata. It consists of all metadata that is related to the entire object. For example, the object **uid**, **name**, **labels**, **annotations**, **namespace**, etc. You should note that the ObjectMeta that is specified in the **metadata** field of the manifest is a mandatory field, and it should be written for every object.

Here is the list of the ObjectMeta fields:

 - **name** (Required): Specifies the name of the object. It should be assigned during resource creation and must be unique within the namespace. After object creation, it can't be changed anymore.

 - **labels** (Optional): It's a dictionary of key-value pairs and is used to organize and categorize objects. Labels are one of the most important parts of the Kubernetes objects because they are related to object selectors that are used to identify members of specific categories. They can be queried by the Kubernetes system and the user.

 - **annotations** (Optional): It's a dictionary of unstructured key-value pairs that are used to adding extra info to the object. Annotations are usually used by third-party components and complex systems. They are not queryable.

 - **uid** (Required): The UID is a unique identifier that is assigned to the object by the Kubernetes itself. It's a read-only field and should not be assigned directly by the user. After resource creation, it can't be changed.

 - **namespace** (Optional): This field represents the namespace that the object must be created on that. After creating the object, it cannot be changed. If it's not assigned during the creation of the object, it points to the **default** namespace.

 - **clusterName** (Optional): In multi-cluster environments, it points to the cluster that the object belongs to that. Currently, Kubernetes is not using this field and ignores that throughout resource creation or updating.
