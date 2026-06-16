# What is this?
- An OpenShift template for deploying a containerized deployment of [Grouper's](https://incommon.org/software/grouper/)

- This will deploy the following resources
    - 1x project "grouper"
    - Postgresql pod(s) with a 1gb PVC
    - Grouper app pod
    - 2x secrets
    - 2x services
    - 1x route

# How to use?
1) Deploy the resources
```
oc apply -k base
```

2) Navigate to the URL exposed by the "grouper" route created and log in with the username "GrouperSystem" and the password found in the grouper/groupersystem-quickstart-pass secret.

3) Optionally demonstrate how you can make customizations per environment by layering in the production requirements to have redundant database pods. This will increase the replica count to 2 for postgresql
```
oc apply -k overlays/production
```
