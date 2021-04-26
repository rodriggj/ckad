# Core Concepts

## Topics
- [ ] Vocabulary
- [ ] Architecture
- [ ] Pods

### Vocabulary
- [ ] `Node` is a machine, physical or virtual on which Kubernetes is installed. A `node` is a worker machine on which containers will be launched by Kubernetes. (aka `minion`). A node is where application contianers are deployed. 

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116097328-48505a80-a667-11eb-97d0-2c037d1f64f9.png" width="200" height="250">
</p>

- [ ] `Cluster` in the event that a node fails, you must have redundant nodes. A collection of nodes is a `cluster`.

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116097448-61f1a200-a667-11eb-9495-61d2cdf0beb4.png" width="450">
</p>

- [ ] `Master` __IS__ a node, that is configured to manage the cluster. The `Master` node is responsible for ensuring that the cluster is running the configuration that was specified within the deployment service.

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116097632-8e0d2300-a667-11eb-868d-a336e37dc614.png" width="450">
</p>


### Architecture

- When you install `Kubernetes` on a system you are actually installing a series of components depicted below. 

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116098668-7da97800-a668-11eb-9007-56cee9fd656a.png" width="450">
</p>

- [ ] `API Server`: Acts as the front-end for Kubernetes, the users, management devices, command line interfaces all talk to the API server to interact with the K8 cluster. 
- [ ] `etcd`: ETCD is a distributed reliable key/value store used by K8 to store all data used to manage the cluser. When you have multiple nodes and multiple masters in your cluster ETCD stores all that information on all the nodes in the cluster ina a distributed manner. ETCD is responsible for implementing `locks` within the cluster to ensure there are no conflicts between the `Masters`.
- [ ] `kublet`: Agent running on each node communicating with the `master`.
- [ ] `container runtime`: The container runtime is the software running the containers, which can be `Docker`, `containerD`, etc.
- [ ] `controller`: The controllers are the brains in K8. They are responsible for noticiting and responding when nodes, container endpoints go down. The controllers make decisions to bring up new containers in such cases. 
- [ ] `scheduler`: Is responsible for distributing work or containers across multiple nodes. It looks for newly created containers and assigns them to nodes. 

#### Master vs. Worker Nodes
Realize the both `Master` and `Workers` are `Nodes` in kubernetes; the difference between the two is thier configuration.

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116146724-0b528b00-a69c-11eb-8826-0f96d09375a9.png" width="450">
</p>


#### `kubectl`

- [ ] CLI tool

```javascript
kubectl run hello-minikube
kubectl cluster-info
kubectl get nodes
kubectl describe pods <pod_name>
```

### PODs 
- [ ] K8 does not deploy containers directly to a worker Node. Instead it encapsulates the container in a K8 object known as a `pod`.
- [ ] A pod is an instance of your application
- [ ] A pod is the smallest object that you can create on K8

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116151575-0395e500-a6a2-11eb-839b-f06b36129c97.png" width="450">
</p>

#### Scaling PODs

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116151887-6edfb700-a6a2-11eb-948c-194d28f41da8.png" width="450">
</p>

#### Multi-Contanier Pods

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152009-9afb3800-a6a2-11eb-8f6f-0a2f09d605b4.png" width="450">
</p>

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152152-ca11a980-a6a2-11eb-85b6-c3d86c44d054.png" width="450">
</p>

#### `kubectl run ...` command
<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152152-ca11a980-a6a2-11eb-85b6-c3d86c44d054.png" width="450">
</p>

### YAML

- [ ] K8 objects are constructed using a YAML or JSON file format. You will have a file for each K8 Object you intend to use within your application deployment (e.g. Pod, Service, Deployment, etc). All YAML files are constructed with the same 4 `root` attributes, shown here. At minimum, these 4 elements _must_ be specified in your `manifest` file. 
- [ ] For the first & secondattributes, `apiVersion` & `kind` these are specified in the K8 documentation and are represented in the table below. 

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152649-69cf3780-a6a3-11eb-8595-fb265a956dfd.png" width="450">
</p>


- [ ] Note that the data structure within the YAML files.

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152698-781d5380-a6a3-11eb-8ac3-e75a804badb5.png" width="450">
</p>

 <p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152883-ba469500-a6a3-11eb-8458-8313b57189b7.png" width="450">
</p>   

<p align="center">
    <image src="https://user-images.githubusercontent.com/8760590/116152965-d6e2cd00-a6a3-11eb-91b5-68ef16350bc2.png" width="450">
</p>  

