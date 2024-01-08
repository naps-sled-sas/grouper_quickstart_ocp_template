# What is this?
- An OpenShift template for deploying a containerized deployment of [Grouper's](https://incommon.org/software/grouper/#:~:text=Software%3A%20An%20enterprise%20group%20and,as%20a%20person's%20role%20changes.) quickstart mode


# How to use?
1) Create a blank OCP project
```
oc new-project grouper
```

2) Create the project using the provided grouper_quickstart_template.yml
```
oc create -f grouper_quickstart_template.yml
```

3) Instantiate the template
Web UI
Project Page -> "+Add" -> "All Services" -> search "grouper-quickstart"
Accept the defaults unless you have a good reason not to

4) Navigate to the URL exposed by the "grouper" route created and log in with the username "GrouperSystem" and the generated password found in the grouper/groupersystem-quickstart-pass secret.
