## To use the policies on this repo just follow the steps

1. ´´´ oc apply -k subscription/ ´´´  

This will create a namespace called acm-policies and will deploy on it 3 policies the policies can be found here:
https://github.com/avaleror/argo-acm/grc/policies
The most importat policy is the gitops policy which enforces the presence of the openshift-gitops operator to be able to deploy
the pacman application in all the manages clusters where the gitops operator are installed.
