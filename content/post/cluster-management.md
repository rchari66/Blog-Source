---
title: "Cluster Management"
date: 2022-08-28T15:29:42Z
categories: ["CKA", "Cluster Management"]
draft: false
---

### Upgrading Kubeadm clusters
https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/

https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/#call-kubeadm-upgrade-1

### Install Network solution
https://kubernetes.io/docs/tasks/administer-cluster/network-policy-provider/

### Rolling updates of DaemonSets
https://kubernetes.io/docs/tasks/manage-daemon/update-daemon-set/



### Debug workder nodes
* Check Kubelet service in worker nodes
    ``` bash
    service kubelet status
    service kubelet start
    
    journalctl -u kubelet
    ```
* Check kubelet service's certifcates
    ``` 
    check config file for certs path: /var/lib/kubelet/config.yaml
    ```

* Check kubelet service logs
    ``` bash
    [sudo] journalctl -u kubelet[.service]
    ```
Note: Any monidifications to kubelet service, pls restart kubelet
    ``` bash
    service kubelet restart
    ```