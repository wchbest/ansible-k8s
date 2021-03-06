# Ansible Playbook to setup Kubernetes Cluster

## Prerequisites for Ansible Controller

* Ansible 2.5.x installed
* Git installed

## Kubernetes Cluster to setup

* OS: Oracle Linux 7.5.0 Minimal Install
* Kubernetes: v1.13.0
    * Single node cluster
    * kubelet,kube-proxy, kube-apiserver, kube-controller-manager, kube-scheduler, and etcd are managed by systemd (i.e. not containerized)
        * kubelet and kube-proxy run as root, and the rest run as non-root
    * Communication between k8s components is encrypted by TLS
    * Authentication by x509 client certificates
    * TLS Bootstrapping
        * Bootstrap token
        * Auto approval for CSRs
    * [Certificate Rotation](https://kubernetes.io/docs/tasks/tls/certificate-rotation/) is enabled
    * etcd 3.3.10
    * [Weave Net](https://www.weave.works/oss/net/) 2.5.0
    * [CoreDNS](https://github.com/coredns/coredns) 1.2.6
    * Service cluster IP range: 10.0.0.0/16
    * Cluster CIDR: 10.32.0.0/16
    * [Proxy mode](https://kubernetes.io/docs/concepts/services-networking/service/#virtual-ips-and-service-proxies): ipvs
    * PodSecurityPolicy is enabled
    * Using [KubeletConfiguration](https://kubernetes.io/docs/tasks/administer-cluster/kubelet-config-file/ ), [KubeProxyConfiguration](https://github.com/kubernetes/kube-proxy/blob/master/config/v1alpha1/types.go), and [KubeSchedulerConfiguration](https://github.com/kubernetes/kube-scheduler/blob/master/config/v1alpha1/types.go)
* Tools
    * [kube-prompt](https://github.com/c-bata/kube-prompt)
    * [dry](https://github.com/moncho/dry)
    * etc.

## How to use

```sh
$ su -
# git clone https://github.com/kaitoy/ansible-k8s.git
# cd ansible-k8s
# sh play.sh
```
