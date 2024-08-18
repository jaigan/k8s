# Argo CD for Continuous Deployment

## Introduction

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes. It helps you automate the deployment of Kubernetes applications based on Git repositories.

### Prerequisites
- Kubernetes cluster setup
- Argo CD installed [Official Documentation](https://argo-cd.readthedocs.io/en/stable/getting_started/)

### Steps to Setup Argo CD
1. **Install Argo CD:**
   ```bash
   kubectl create namespace argocd
   kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
