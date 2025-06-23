# ✅ OpenShift Virtualization – Post-Installation Verification Guide

This guide helps verify every component of **OpenShift Virtualization (KubeVirt)** after installation to ensure a stable and production-ready environment.

---

## 🧾 Table of Contents

- [1. HyperConverged Custom Resource](#1-hyperconverged-custom-resource-hco)
- [2. Component Verification](#2-component-verification)
- [3. CRDs and API Resource Check](#3-crds-and-api-resource-check)
- [4. VM Functional Test](#4-vm-functional-test)
- [5. Troubleshooting Quick Hits](#5-troubleshooting-quick-hits)

---

## 1. HyperConverged Custom Resource (HCO)

**Purpose**: Central controller that deploys and manages virtualization components.

```bash
oc get hyperconverged -n openshift-cnv
oc describe hyperconverged kubevirt-hyperconverged -n openshift-cnv
```

---

## 2. Component Verification

### 2.1 virt-operator

```bash
oc get deployment virt-operator -n openshift-cnv
oc logs deployment/virt-operator -n openshift-cnv
```

### 2.2 virt-api

```bash
oc get deployment virt-api -n openshift-cnv
oc logs deployment/virt-api -n openshift-cnv
```

### 2.3 virt-controller

```bash
oc get deployment virt-controller -n openshift-cnv
oc logs deployment/virt-controller -n openshift-cnv
```

### 2.4 virt-handler

```bash
oc get daemonset virt-handler -n openshift-cnv
oc get pods -l kubevirt.io=virt-handler -n openshift-cnv -o wide
oc logs <virt-handler-pod> -n openshift-cnv
```

### 2.5 virt-launcher (only when VM is running)

```bash
oc get pods -n default | grep virt-launcher
oc logs <virt-launcher-pod> -n default
```

### 2.6 CDI (Containerized Data Importer)

```bash
oc get pods -n openshift-cnv | grep cdi
oc get deployment cdi-deployment -n openshift-cnv
oc logs deployment/cdi-deployment -n openshift-cnv
```

### 2.7 HostPath Provisioner (Optional)

```bash
oc get deployment hostpath-provisioner-operator -n openshift-cnv
oc get pods -n openshift-cnv | grep hostpath
```

### 2.8 Network Addons (CNAO)

```bash
oc get pods -n openshift-cluster-network-addons
oc get networkaddonsconfigs.operator.openshift.io cluster -o yaml
```

### 2.9 Templates / SSP

```bash
oc get templates -n openshift
```

---

## 3. CRDs and API Resource Check

### 3.1 Verify CRDs

```bash
oc get crd | grep kubevirt.io
oc get crd | grep cdi.kubevirt.io
oc get crd | grep hostpathprovisioner.kubevirt.io
oc get crd | grep ssp.kubevirt.io
```

### 3.2 Check API Resources

```bash
oc api-resources | grep -E 'virtualmachine|virtualmachineinstance|datavolume'
```