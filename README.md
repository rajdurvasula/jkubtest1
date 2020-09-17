# jkubtest1

This is a simple Spring boot application developed with JKube plugin. The pom.xml has plugin configuration to deploy on OpenShift cluster.

## How to test this project

### Prerequisites
- OpenShift Cluster (Alternatively, you can run Red Hat CodeReady Containers)

### Preparation
- Clone this Project
- Start OpenShift Cluster
- Login as 'kubeadmin'
- Create a Project

### Build and Deploy
- Navigate to directory: jkubtest1/greeting
- Issue Maven commands in the order given below:
  - Clean and Generate OpenShift Resources
```
mvn clean oc:resource -Popenshift
```
  - Compile and Generate Build Configuration
```
mvn package oc:build -Popenshift
```
  - Deploy OpenShift resources
```
mvn oc:deploy -Popenshift
```

### Test the Application URL
- Get the exposed route for this application
```
oc get route greeting
```

- Verify the Application URL on web browser
```
http://<route_of_application>
```
