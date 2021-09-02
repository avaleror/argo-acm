# Demonstrate aplication deployment using argo throught RHACM
## Tool Requirements
- OpenShift CLI Version >= 4.3.0<br>_Needed for kustomize_
```bash
oc version
```

## Summary
This provides an application deployer for ArgoCD using RHACM. 

## Prerequisite
- 1+ managed-clusters
- ArgoCD installed in the cluster (RH GitOps Operator) you want to deploy pacman app

## How to use the repo
- Clone the repo 
- Log in an OpenShift cluster
- Execute this command from inside the folder argo-acm ```oc apply -k acm-resources```

## How to add a new app
- Copy the application file pacman-app.yaml
- Change the file's name
- Inside the new file add all the info regarding the new app (Argo project, git repo, etc...)
- In the namespace.yaml file add the namespace definition in yaml that you want to use for deploying your app and add the next label: "argocd.argoproj.io/managed-by: openshift-gitops" if you do not add this label you'll get a sync error on ArgoCD and the app won't be deployed. In this article you have the explanation: https://developers.redhat.com/articles/2021/08/03/managing-gitops-control-planes-secure-gitops-practices#application_delivery_with_openshift_gitops
