# What is this?
- An OpenShift template for deploying a containerized deployment of [Grouper's](https://incommon.org/software/grouper/#:~:text=Software%3A%20An%20enterprise%20group%20and,as%20a%20person's%20role%20changes.) quickstart mode


# How to use?
1) Create a blank OCP project
```
oc new-project grouper
```

2) Deploy the resources
```
oc apply -f grouper_quickstart.yml
```

3) Navigate to the URL exposed by the "grouper" route created and log in with the username "GrouperSystem" and the password found in the grouper/groupersystem-quickstart-pass secret. (Ensure your browser is using http and not defaulting to https)


# ToDo
- Look into generating a random string instead of hardcoding the password in the yml.
