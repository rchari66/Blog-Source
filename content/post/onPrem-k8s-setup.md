---
title: "How to setup K8s on premise"
date: 2023-03-23T23:53:58Z
categories: ["onpremise"]
draft: false
---

This doc covers steps to bring up Kubernetes cluster in on premise environment using ansible.
Also deploy custom services(own services)


#### Pre-requisites
* Keep ssh creds(username & ssh_password) for all on premise VMs(master and worker nodes)
* install ansible (to setup and configure kubernetes)

Note: SSH keys provide better security over shh_passwords.



#### Approach (at high level)
* Create inventory file and add details of master and worker nodes

Sample:
``` yaml 
master1 <ip-1/master-node01> ansible_password=<???>

worker1 <ip-2/worker-node01> ansible_password=<???>
worker2 <ip-3/worker-node03> ansible_password=<???>
```


* Define playbooks to installing kubernetes on both Master and Worker nodes
    *  Create kube user with sudo permissions
    *  container runtime(containerd) and it's dependencies
    *  install kubernetes components(kubeadm, kubelet, kubectl)
    *  Configure kubernetes master node using kubeadm

 
* Playbook to configure master node alone
    * execute "kubeadm init <cidr block>"
    * copy kubeadm join cmd to locally (This cmd should have a token, used for joining woker node to master node)

* Playbook to join worker nodes to master node
    * Copy and execute the "kubeadm join cmd" in each worker node

---
Now that we have the cluster up & running.. lets setup our custom services.

---

We can deploy them in one of following ways...

1. Deploy kubernetes spec through ansible playbook (this would copy the files to master node, then kubectl applies them)
2. If we want deploy our services as a helm chart, we can deploy it via ansible playbook. Pls, note that we need to have helm available in master node to run `helm install <our-chart>`
3. Deploy an agent pod with (mTLS cert), which can pull latest kubernetes spec files from remote server(ours) and deploys them in the cluster


We can also copy kube.config file locally(from master node), then run `kubectl` or `helm` cmd direclty to deploy.


Note: Based pros & cons we can conclude on one approach which suits best.

#### Other Considerations
* Our service images may need to be pushed to customer's registry and update the image reference in our helm chart.
* Copying images, updating them in our helm chart can be automated as well.

* We may have to use local storage if cloud storage is not an option
  * we could use kubernetes native storage solutions like (GlusterFS, longhorn, and etc..)
  
* We may have to look for solutions/implementations as alternatives to cloud servies like(SQS, IAM, etc..) if any of them are used in our applications