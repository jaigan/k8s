


# Create the helmchart
```
helm create webapp1
```

# Create the manifest files
```
- Create the mainfest files like deployment.yml, values.yml, service.yml, 
- Change the values.yaml as its needed.
```

# Install the first one
```
helm install mywebapp-release webapp1/ --values webapp1/values.yaml
```

# Upgrade after templating
```
helm upgrade mywebapp-release webapp1/ --values mywebapp/values.yaml
```

# Accessing it
```
curl <any one of Node IP>:<Nodeport>
```

# Create dev/prod
```
k create namespace dev
k create namespace prod
helm install mywebapp-release-dev webapp1/ --values webapp1/values.yaml -f webapp1/values-dev.yaml -n dev
helm install mywebapp-release-prod webapp1/ --values webapp1/values.yaml -f webapp1/values-prod.yaml -n prod
helm ls --all-namespaces
```
