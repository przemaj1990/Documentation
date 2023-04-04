# Documentation
Sum of all documentation from each cours I take. 

### How to install k8s on Cloud Native KUbernetes from cloud guru:
https://learn.acloud.guru/course/93e6884d-ac98-49b6-a9cd-5e357d2dbb41/learn/317a36ae-245e-4801-a1a0-6e39b085e3bd/4c5aa679-c702-468d-b79c-15f0f52e8572/watch

You can initialize the master node in kubeadm by creating a config file called kube-config.yml with these contents:
```
apiVersion: kubeadm.k8s.io/v1beta2
kind: ClusterConfiguration
networking:
    podSubnet: 10.244.0.0/16
apiServer:
    extraArgs:
        service-node-port-range: 8000-31274
```
Then run this command referencing that file:
    `kubeadm init --config kube-config.yml`
Use this command to set up a pod network after initializing the master with kubeadm init:
    `kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml`