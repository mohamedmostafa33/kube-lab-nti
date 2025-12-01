# kube-lab

A comprehensive Kubernetes training lab containing practical examples and various scenarios for learning and testing Kubernetes concepts.

## 📁 Project Structure

### Root Level Files

Contains examples of all fundamental Kubernetes resource types:

#### **1- Pod & Service (Related)**
- `1-pod.yml` - Simple pod using nginx in `web-ns` namespace
- `1-service.yaml` - Service to route traffic to the pod

#### **2- ReplicaSet**
- `2-replicaset.yml` - ReplicaSet with 2 replicas and CPU/Memory resource limits

#### **3- Deployment**
- `3-deployment.yml` - Deployment with nodeSelector, tolerations, and readinessProbe

#### **4- StatefulSet & Service (Related)**
- `4-statefulset.yaml` - StatefulSet for MySQL database with Persistent Volumes
- `4-service.yml` - Headless Service for the StatefulSet

#### **5- Job**
- `5-job.yml` - Job to run a one-time task with initContainer

#### **6- CronJob**
- `6-cron-job.yml` - CronJob that runs every 10 minutes

#### **7- DaemonSet**
- `7-daemonset.yml` - DaemonSet to run log agent on every node

#### **8- Sidecar Pattern**
- `8-sidecar.yml` - Pod with sidecar container for logging

#### **9- RBAC Role**
- `9-role.yml` - Role allowing read-only access to Pods

#### **10- Network Policy**
- `10-network-policy.yml` - Network Policy to allow traffic from frontend to backend

#### **11- Ingress**
- `11-ingress.yml` - Ingress with TLS/SSL for domain routing

#### **12- Network Policy (Deny All)**
- `12-cni.yml` - Network Policy to deny all incoming traffic

#### **13- Static Pod**
- `13-static-pod.yml` - Pod with hostPath volume to access node files

#### **14- Custom Resource Definition**
- `14-crd.yml` - CRD to create custom resources (Widget)

#### **15- Deployment Strategy**
- `15-drd.yml` - Deployment with RollingUpdate strategy

---

## 🎯 Scenarios (scenarios/)

The `scenarios/` directory contains 17 practical scenarios with organized YAML files:

### **Scenario 1 - Basic Web Pod**
- `web-pod.yml` - Simple pod using nginx
- Use case: Basic example of running a pod

### **Scenario 2 - Multi-Container Pod**
- `multi-container-pod.yml` - Pod with 3 containers (nginx, redis, sidecar)
- Use case: Learn to run multiple containers in a single pod

### **Scenario 3 - Namespace & Deployment**
- `dev-namespace.yml` - Create namespace for development
- `app-deployment.yml` - Deployment with 3 replicas
- Use case: Isolate resources using namespaces

### **Scenario 4 - Resource Limits**
- `resource-limited-pod.yml` - Pod with CPU/Memory limits and requests
- Use case: Resource management to prevent excessive consumption

### **Scenario 5 - ConfigMap & Secret**
- `app-configmap.yml` - ConfigMap to store application settings
- `app-deployment.yml` - Deployment using ConfigMap
- Use case: Separate configuration from code

### **Scenario 6 - Deployment & Service**
- `web-deployment.yml` - Deployment for web application
- `web-service.yml` - LoadBalancer Service
- Use case: Connect Deployment with Service

### **Scenario 7 - Persistent Volume**
- `mysql-pv-pvc-pod.yml` - MySQL Pod with PersistentVolume and PersistentVolumeClaim
- Use case: Store data persistently

### **Scenario 8 - Init Container**
- `init-container-pod.yml` - Pod with initContainer to verify conditions before running
- Use case: Prepare environment before application starts

### **Scenario 9 - StatefulSet & Headless Service**
- `db-headless-service.yml` - Headless Service
- `db-statefulset.yml` - StatefulSet with 3 replicas
- Use case: Run stateful applications like databases

### **Scenario 10 - Liveness & Readiness Probes**
- `probes-pod.yml` - Pod with liveness, readiness, and startup probes
- Use case: Verify application health and auto-restart

### **Scenario 11 - Job**
- `backup-job.yml` - Job for taking backups
- Use case: Run one-time tasks

### **Scenario 12 - CronJob**
- `scheduled-backup-cronjob.yml` - CronJob running daily at 2 AM
- Use case: Schedule periodic tasks

### **Scenario 13 - DaemonSet**
- `monitoring-daemonset.yml` - DaemonSet to run monitoring agent on every node
- Use case: Run services on all nodes

### **Scenario 14 - Network Policies**
- `allow-frontend-netpol.yml` - Network Policy to allow traffic from frontend
- `deny-all-netpol.yml` - Network Policy to deny all traffic
- Use case: Secure network and control traffic

### **Scenario 15 - RBAC (ServiceAccount, Role, RoleBinding)**
- `monitoring-namespace.yml` - Namespace for monitoring
- `monitoring-serviceaccount.yml` - ServiceAccount
- `pod-reader-role.yml` - Role to allow reading Pods
- `monitoring-rolebinding.yml` - RoleBinding to link Role with ServiceAccount
- Use case: Manage permissions and access control

### **Scenario 16 - Node Affinity**
- `node-affinity-pod.yml` - Pod with node affinity to run on specific nodes
- Use case: Control Pod distribution across Nodes

### **Scenario 17 - Multi-Tier Application (Frontend + Backend + Ingress)**
- `backend-deployment.yml` - Backend deployment
- `backend-service.yml` - Backend service
- `frontend-deployment.yml` - Frontend deployment
- `frontend-service.yml` - Frontend service
- `app-ingress.yml` - Ingress for request routing
- Use case: Complete multi-tier application

---

## 🚀 How to Use

### Apply a single file:
```bash
kubectl apply -f 1-pod.yml
```

### Apply a complete scenario:
```bash
kubectl apply -f scenarios/Scenario1/
```

### Apply all files in a directory:
```bash
kubectl apply -f scenarios/ --recursive
```

### Delete resources:
```bash
kubectl delete -f scenarios/Scenario1/
```

---

## 📝 Notes

- Each scenario contains a `.txt` file explaining the objective and steps
- Files with the same number (e.g., `1-pod.yml` and `1-service.yaml`) are related
- Ensure you have a Kubernetes cluster before applying

---

## 🎓 Learning Tips

1. Start with basic scenarios (1-5)
2. Try modifying files and observe the impact
3. Use `kubectl describe` and `kubectl logs` to check status
4. Read `.txt` files in each scenario to understand the objective

---

**Happy Learning! 🎉**