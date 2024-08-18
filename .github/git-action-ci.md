```markdown
# GitHub Actions for Continuous Integration

## Introduction

GitHub Actions allows you to automate, customize, and execute your software development workflows right in your GitHub repository.

### Prerequisites
- GitHub repository
- Create `.github/workflows/ci.yml`

### Sample GitHub Action for CI

1. **CI Workflow:**
   ```yaml
   name: CI

   on:
     push:
       branches:
         - main

   jobs:
     build:
       runs-on: ubuntu-latest

       steps:
       - name: Checkout code
         uses: actions/checkout@v2

       - name: Set up Node.js
         uses: actions/setup-node@v2
         with:
           node-version: '14'

       - name: Install dependencies
         run: npm install

       - name: Run tests
         run: npm test
