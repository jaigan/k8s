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
autokube folder contains the scripts which is used for setup the local cluster having 

k8s master setup 
master-pre-req.sh

k8s worker nde setup 
worker-pre-req.sh 
```

```bash
# vagrant up
```
```bash
# vagrant ssh master-1
```
After this stage you can use kubectl



