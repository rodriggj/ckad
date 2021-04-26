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

- [ ] _API Server_: 
- [ ] _etcd_: 
- [ ] _kubelet_: 
- [ ] _Container Runtime_: 
- [ ] _Controller_: 
- [ ] _Scheduler_: 