## Revision & key points to remember 

### ocp in pod container context 

<img src="rev1.png">

### To login into ocp cluster from a client machine one of the way is 

```
oc login -u admin -p redhatocp  https://api.ocp4.example.com:6443
```

### verify ocp virtualization operator status 

<img src="rev2.png">

### checking ocp console url details 

<img src="rev3.png">

### in OCP we can create VM using 2 resources in OCP  

<img src="vm1.png">

### VMI vs VM 

<img src="vm2.png">

## accessing vm in ocp env 

<img src="vm3.png">

### using virtct to manage vm 

<img src="vm4.png">

## virt-lancher pod can also handle vm using -- tool -- virsh

<img src="vm5.png">

### accessing using virt-launcher pod 

<img src="vm6.png">

# Networking in OCP 

### POD networking using CNI 

<img src="cni1.png">

## by default pod can communicate but its not a good idea to do communication using pod IP

<img src="cni2.png">

### service in openshift ENV 

<img src="cni3.png">

### creating clusterIP type service 

<img src="cni4.png">

### clusterip vs Nodeport/Loadbalancer 

<img src="cni5.png">

### checking default network of service and pod ranges in OCP cluster 

<img src="cni6.png">

### service name with internal DNS in ocp 


<img src="cni7.png">

### to create service in OCP 

```
virtctl expose  / oc expose 

```
<img src="cni8.png">

### creating and verify service 


<img src="cni9.png">