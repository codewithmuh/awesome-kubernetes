# kubernetes Learning - Zero To Hero
Just look at the structure.
![kube (1)](https://github.com/user-attachments/assets/bcb216df-28a1-405e-b18a-3f76022adeb9)

Learn Kubernetes in an Easy Way. Key Concepts and Hands-On Labs.

### Table of Content

1. Analogy of Kubernetes
2. What is k8s
3. K8s Main Key Components
4. what is Mini Kube and kubectl?
5. mini Kube and kubectl - Local Step
6. kubectl Commands - Hands On
7. K8s YAML configuration
8. Demo Project - Hands On
9. K8s Namespace
10. K8s Ingress
11. Helm - Package Manager
12. Presenting data in k8s with volume
13. Deploying Stateful apps with SatefulSet
14. K8s Service
15. AWS EKS Hands-On Project
16. Google Cloud GKE hands-on Project
17. AZure AZK Hands-On Project

# 1. Analogy of Kubernetes
![3](https://github.com/user-attachments/assets/f65c55b2-b293-47d2-8858-6a615e4b2b66)
![4](https://github.com/user-attachments/assets/984345d3-4144-4d31-9128-d9d3f1470c3a)
![kube (2)](https://github.com/user-attachments/assets/1b3798b3-c073-46bf-a36d-396ae9defcb3)
![5](https://github.com/user-attachments/assets/dff40fcf-31bb-4dba-a0c6-46fe47dc09be)
![6](https://github.com/user-attachments/assets/15f10de4-c88b-4659-9d50-362997cf57b3)
![7](https://github.com/user-attachments/assets/ad140b14-f10d-462a-8cad-9ee9255a1a3e)
![8](https://github.com/user-attachments/assets/dbd3f474-bcde-4f85-b5ad-3c70d3868968)
![9](https://github.com/user-attachments/assets/05d3220d-6849-4f0b-b050-e46bc11fc633)
![10](https://github.com/user-attachments/assets/5343fd2a-925a-43ba-8b9d-05e363461d17)
![11](https://github.com/user-attachments/assets/d0fda546-5d2c-49ee-8c75-dc0476e2a4cc)
![12](https://github.com/user-attachments/assets/d9a71acf-f295-47cb-a3f7-72a64111bc4d)
![14](https://github.com/user-attachments/assets/e5358ced-e77f-4e9a-87de-78c62eb67775)
![15](https://github.com/user-attachments/assets/73825792-ff21-4b48-afc4-4e21f1c1d529)
![16](https://github.com/user-attachments/assets/55e9ccf5-6b23-417b-a405-3e928ec8a264)
![17](https://github.com/user-attachments/assets/7ea01e76-2841-4d2b-b545-238202a221da)
![18](https://github.com/user-attachments/assets/eb65a5a0-0efd-4f6e-99b4-de0e37a72c8c)
![19](https://github.com/user-attachments/assets/ac67f579-edbd-45c4-a48f-e5814c2778ad)
![20](https://github.com/user-attachments/assets/902c470c-c6c4-475a-9d89-0bc959023136)
![21](https://github.com/user-attachments/assets/1117a2e1-2e38-43f0-9a29-8f2c94165edc)
![22](https://github.com/user-attachments/assets/1b8c4727-cfc9-4119-beb6-91602eb43ca4)
![23](https://github.com/user-attachments/assets/0962232a-ead3-4247-acbc-1687e6059872)
![24](https://github.com/user-attachments/assets/786d0cf0-2800-4b38-bc4d-50ef4b2eb86c)
![25](https://github.com/user-attachments/assets/2bbf75b8-38e3-430d-804c-2a184d4a89b5)
![26](https://github.com/user-attachments/assets/65d7a9f2-590a-44c1-8f37-ce6d6a6fd966)
![27](https://github.com/user-attachments/assets/a387b18b-80f5-4bbc-a3e9-8dd73c8654bb)
![28](https://github.com/user-attachments/assets/818d5b2f-6ac3-4a84-9513-11620d548ef7)

![29](https://github.com/user-attachments/assets/7d8a0030-c61f-47af-81ca-1b680e2f47bf)


# 2. What is k8s

K8s, short for Kubernetes, is an open-source platform designed to automate the deployment, scaling, and operation of containerized applications. Originally developed by Google, Kubernetes helps manage and orchestrate large clusters of containers, ensuring that they run smoothly and efficiently.

## Key Features of Kubernetes (K8s):
**1. Container Orchestration**: Kubernetes automates the deployment and scaling of containerized applications across clusters of machines, managing workloads to ensure that they run consistently.

**2. Self-Healing**: Kubernetes can automatically restart failed containers, replace containers, and reschedule them on available nodes if a node fails.

**3. Load Balancing and Service Discovery**: Kubernetes can expose containers using DNS names or their own IP addresses and automatically balance the load between containers.

**4. Storage Orchestration**: Kubernetes allows you to automatically mount a storage system of your choice, like local storage, public cloud providers, or network storage systems.

**5. Automated Rollouts and Rollbacks**: Kubernetes can manage updates to your applications or its configuration, rolling out changes gradually while monitoring application health to ensure the updates don’t cause issues.

**6. Secret and Configuration Management**: Kubernetes can store and manage sensitive information, such as passwords, OAuth tokens, and SSH keys, allowing you to deploy and update secrets and application configuration without rebuilding your container images.

**7. Horizontal Scaling**: With Kubernetes, you can scale your applications up and down easily using a command, a user interface, or automatically based on CPU usage.

## Why Use Kubernetes?
**Portability**: Kubernetes works with various container runtimes and can be used across different cloud providers and on-premises environments.

**Resource Efficiency**: It optimizes resource usage by efficiently packing containers onto nodes.

**Scalability**: Kubernetes can handle large-scale, complex applications with ease, making it suitable for both small and enterprise-level deployments.

## Kubernetes (K8s) Main Key Components
**1. Nodes**:

- **Master Node (Control Plane)**: Manages the Kubernetes cluster, making decisions about scheduling, responding to cluster events, and managing the desired state of the cluster. Key components include:
 
- **API Server**: The front-end for the Kubernetes control plane. It exposes the Kubernetes API.

- **Scheduler**: Assigns workloads to nodes based on resource availability and other constraints.

- **Controller Manager**: Manages various controllers that handle different aspects of the cluster, such as node and pod lifecycle, endpoints, and more.

- **etcd**: A distributed key-value store used for storing cluster configuration data, state, and metadata.

- **Cloud Controller Manager**: Manages interactions with the underlying cloud providers (e.g., load balancers, storage, networking).

**Worker Nodes**: Run the actual application workloads. They include:

- **Kubelet**: An agent that runs on each node in the cluster, ensuring that containers are running in pods as expected.

- **Kube Proxy**: Maintains network rules on nodes, allowing communication between Pods and services within the cluster.

- **Container Runtime**: The software responsible for running the containers (e.g., Docker, containerd, CRI-O).

 **2.Pods**:

- The smallest and simplest Kubernetes object, a pod represents a single instance of a running process in your cluster. It can contain one or more containers that share the same network and storage resources.

**3. Services**:

- A stable, reliable endpoint that provides a way to expose an application running on a set of Pods as a network service. Services enable load balancing and service discovery.

**4. Deployments**:

- Manages the deployment and scaling of a set of Pods. It allows declarative updates to applications and manages the desired state for Pods and ReplicaSets.

**5. ReplicaSets**:

- Ensures that a specified number of identical Pods are running at any given time. It’s often used by Deployments to maintain a stable set of replicas of Pods running at all times.

**6. ConfigMaps and Secrets**:

- **ConfigMaps**: Used to store configuration data in key-value pairs that can be consumed by Pods.

- **Secrets**: Similar to ConfigMaps but intended for storing sensitive information like passwords, tokens, and keys.

**7. Volumes**:

- Provide a way to store and persist data generated by and used by containers. Kubernetes supports different types of volumes, such as persistent volumes, emptyDir, hostPath, etc.

**8. Namespaces**:

Provide a way to divide cluster resources between multiple users or teams. They are useful for managing environments (e.g., development, testing, production) within a single Kubernetes cluster.
**9. Ingress**:

- Manages external access to services in a cluster, typically HTTP/HTTPS routes, providing load balancing, SSL termination, and name-based virtual hosting.

## MiniKube
MiniKube is a tool that enables you to run Kubernetes locally on your personal computer. It creates a single-node Kubernetes cluster on your machine, which is useful for development, testing, and learning purposes. MiniKube can run on various operating systems like macOS, Linux, and Windows.

### Key Features of MiniKube:
- Provides a local Kubernetes cluster for testing and development.
- Supports different Kubernetes features and add-ons.
- Easy to set up and start using Kubernetes without needing a full-scale cluster.
  
## kubectl
kubectl is the command-line tool used to interact with Kubernetes clusters. It communicates with the Kubernetes API server and allows you to deploy applications, inspect and manage cluster resources, and view logs.

### Common kubectl Commands:

- kubectl get pods: Lists all Pods in a specific namespace.

- kubectl apply -f <file.yaml>: Applies the configuration specified in a YAML file to create or update Kubernetes resources.

- kubectl describe pod <pod-name>: Provides detailed information about a specific Pod.

- kubectl delete service <service-name>: Deletes a specific service.

Both MiniKube and kubectl are essential tools for developers and system administrators working with Kubernetes, especially in local development environments.

## 1. MiniKube and kubectl - Local Setup

**MiniKube** allows you to create a local Kubernetes cluster on your personal computer, which is perfect for development and testing. **kubectl** is the command-line tool that interacts with your Kubernetes cluster, helping you manage and deploy applications.

# More Coming Soon (I am working on this Repo)



