## VM and container things to Notice 

<img src="vm1.png">

### OCP / k8s architecture basic points 

<img src="vm2.png">

### IN ocp master / control plane Node -- Apiserver and scheduler 

<img src="vm3.png">

### worker Node components in Openshift nodes 

<img src="vm4.png">

### KUbelet component in ocp / k8s worker nodes 

<img src="vm5.png">

### OCP architecture 

<img src="vm6.png">

### info about POD in ocp 

<img src="pod1.png">

## lets connect to student workstation machine and test client side tools 

### kubectl 

```
kubectl version 
```

### oc 

```
oc version 
```

## checking project details 

<img src="ns1.png">

### creating pod using oc 

```
oc run ashupod1 --image quay.io/jay1123/nginx:codev1 

===> to check 
oc get pods
```

## Kubelet to connect any Hypervisor and create vm inside POd ENV 

<img src="kvm1.png">


### kubelet to KVM

<img src="kvm2.png">

### Info about Libvirtd 

<img src="kvm3.png">

### kubevirt visual look 

<img src="kvm4.png">

# kubevirt architecture 

<img src="kvm5.png">

## Components of kubevirt project 

### Virt-controller

<img src="kvm6.png">

### virt-handler -- managing vm on its own worker machine only

<img src="kvm7.png">

### virt-launcher --  A pod that wraps and runs actual VM using KVM /libvirtd

<img src="kvm8.png">