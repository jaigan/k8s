## Introduction

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes. It helps you automate the deployment of Kubernetes applications based on Git repositories.

### Prerequisites
- Kubernetes cluster setup
- Argo CD installed [Official Documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/) or Check helm repository 

### Steps to Setup Argo CD
1. **Install Argo CD with helm:**
   ```bash
   helm install argocd argo/argo-cd --namespace default
   ```
2. **Check the admin password:**
   ```bash
    kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
   ```
3. **Check Agrocd pods status:**

   ![image](https://github.com/user-attachments/assets/e86efa7a-7147-4d40-810a-4fae4f4b4d46)

4. **Access argocd and project setup:**
   ```
   <any one of the node ip>:<Nodeport> 

![image](https://github.com/user-attachments/assets/610583dd-1154-4ebd-a1d7-2093f9d149d0)

5. **check the status of deployment**

   ![image](https://github.com/user-attachments/assets/af104e2f-bc10-4692-8312-27a6d7e610cd)

   
