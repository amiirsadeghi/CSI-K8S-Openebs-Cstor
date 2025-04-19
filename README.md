# OpenEBS CStor on Kubernetes

This repository provides a step-by-step guide to installing and configuring OpenEBS CStor as a storage solution in a Kubernetes cluster. It's particularly useful for environments where dynamic provisioning of persistent volumes is required.

---

## Prerequisites

- A running Kubernetes cluster (v1.18+ recommended)
- `kubectl` configured to access your cluster
- OpenEBS installed in your cluster

---

## Project Structure

```
.
├── README.md
├── cstorpool.yaml           # CStorPoolCluster configuration
├── storageclass.yaml        # StorageClass definition for CStor
└── statefulset.yaml         # Sample StatefulSet using the CStor StorageClass
```

---

## Installation Steps

### ✅ 1. Deploy CStorPoolCluster

Apply the CStorPoolCluster configuration to set up the storage pool:

```bash
kubectl apply -f cstorpool.yaml
```

### ✅ 2. Create StorageClass

Define a StorageClass that uses the CStorPoolCluster:

```bash
kubectl apply -f storageclass.yaml
```

### ✅ 3. Deploy a Sample StatefulSet

Deploy a sample StatefulSet that utilizes the CStor StorageClass:

```bash
kubectl apply -f statefulset.yaml
```

### ✅ 4. Verify the Deployment

Check the status of the pods and persistent volume claims:

```bash
kubectl get pods
kubectl get pvc
```

---

## Why Use OpenEBS CStor?

- **Dynamic Provisioning**: Automatically provisions persistent volumes as needed.
- **Data Resiliency**: Provides replication and high availability for stateful applications.
- **Flexibility**: Suitable for various environments, including on-premises and cloud.

---

## Resources

- [OpenEBS Documentation](https://openebs.io/docs)
- [Kubernetes Persistent Volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
