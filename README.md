# Kubernetes Cluster using Ansible
* Please follow pre-requisite before proceeding further.

```
I am using 1 master and 2 worker node with host names as - 
master 
worker01
worker02
```

* Clone repository.
* Create multiple centos8 servers. One master and many worker. Use vagrant like [here](https://github.com/edib/many_vagrant_machines)
* Change the “ad_addr” in the env_variables file with the IP address of the Kubernetes master node.
* Add the IP Addresses of the worker nodes and the master node in the “hosts” file.
* Run the following command to setup the Kubernetes Master node.
* Additional MASTER setup is in progress.

```
ansible-playbook setup_master_node.yml
```

* After you executed above command, please run 

```
cd playbooks 
cat token_file > join_token
```


* Once the master node is ready, run the following command to set up the worker nodes.

```
ansible-playbook setup_worker_nodes.yml
```

* Once the workers have joined the cluster, run the following command to check the status of the worker nodes.
```
kubectl get nodes
```

## Reference:
* https://medium.com/faun/how-to-create-your-own-kubernetes-cluster-using-ansible-7c6b5c031a5d



