# What is this?
- An OpenShift template for deploying a containerized deployment of [Grouper's](https://incommon.org/software/grouper/) quickstart mode

- This will deploy the following resources
    - Postgresql pod(s) with a 1gb PVC
    - Grouper app pod
    - 2x secrets
    - 2x services
    - 1x route

# How to use?
1) Create a blank OCP project
```
oc new-project grouper
```

2) Deploy the resources
```
oc apply -k base
```

3) Navigate to the URL exposed by the "grouper" route created and log in with the username "GrouperSystem" and the password found in the grouper/groupersystem-quickstart-pass secret. (Ensure your browser is using http and not defaulting to https.)

4) Optionally demonstrate how you can make customizations per environment by layering in the production requirements to have redundant database pods. This will increase the replica count to 2 for postgresql
```
oc apply -k overlays/production
```

# Troubleshooting
- The grouper app doesn't very gracefully handle a failed DB connection. If it errors out or displays Tomcat warnings kill the pod and let it rebuild it likely lost it's race condition with Postgresql being available.

# ToDo
- Look into generating a random string instead of hardcoding the password in the yml.
