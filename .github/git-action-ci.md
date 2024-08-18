# GitHub Actions for Continuous Integration

## Introduction

GitHub Actions allows you to automate, customize, and execute your software development workflows right in your GitHub repository.

### Prerequisites
- GitHub repository
- Create `.github/workflows/ci.yml`


### Sample GitHub Action for CI

1. **CI Workflow:**
```
name: Helm Lint, Diff, and Dry-Run

on:
  pull_request:
    branches:
      - main

jobs:
  lint-and-test-helm:
    runs-on: ubuntu-latest

    env:
      HELM_VERSION: v3.9.0
      K8S_NAMESPACE: default

    steps:
    # Step 1: Checkout the code
    - name: Checkout code
      uses: actions/checkout@v2

    # Step 2: Install Helm
    - name: Install Helm
      run: |
        curl https://get.helm.sh/helm-${{ env.HELM_VERSION }}-linux-amd64.tar.gz -o helm.tar.gz
        tar -zxvf helm.tar.gz
        sudo mv linux-amd64/helm /usr/local/bin/helm
        helm version

    # Step 3: Helm Lint
    - name: Helm Lint
      run: |
        helm lint webapp1/

    # Step 4: Setup kubeconfig (using GitHub Secrets)
    - name: Setup kubeconfig
      run: |
        mkdir -p $HOME/.kube
        echo "${{ secrets.KUBECONFIG }}" > $HOME/.kube/config

    # Step 5: Install Helm Diff Plugin
    - name: Install Helm Diff Plugin
      run: |
        helm plugin install https://github.com/databus23/helm-diff
```
