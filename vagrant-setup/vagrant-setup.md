# AutoKube

## Fully Automated Kubernetes Cluster Setup, with one master and N workers.

This will install:

- The lastest Kubernetes version (currently 1.30)
- Containerd as a runtime
- Calico as a CNI.

## Requirements

You have to install:
- [Vagrant](https://www.vagrantup.com/) 
- and [VirtualBox](https://www.virtualbox.org/)

## How To Use It

```bash
# git clone https://github.com/jaigan/k8s.git
```

```bash
# cd k8s/AutoKube
```

AutoKube folder contains the scripts and vagrantfile which is used for setup the local cluster.  

## k8s master node setup 

./scripts/master-pre-req.sh

## k8s worker node setup 
./scripts/worker-pre-req.sh 

```bash
# vagrant up
```
```bash
# vagrant ssh master-1
# sudo su -
# kubectl get nodes
```

## Check the nodes status and kubelet status
```bash
# sudo su -
# systemctl status kubelet
# kubectl get nodes
```

## Check the IP of the Node

```bash
ip -f inet addr show eth1 | grep -Po 'inet \K[\d.]+'
```
After this stage you can use kubectl




