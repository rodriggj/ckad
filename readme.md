# Core Concepts

## Topics
- [ ] Vocabulary
- [ ] Architecture

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