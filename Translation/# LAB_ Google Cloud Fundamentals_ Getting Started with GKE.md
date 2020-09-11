# # LAB: Google Cloud Fundamentals: Getting Started with GKE

# # #Objective 

In this lab, you learn how to perform the following tasks:

.Provision a kubernetes cluster using Kubernetes Engine

.Deploy and mange Docker containers using kubectl



# # #Steps

1. Start a Kubernetes cluster managed by Kubernetes Engine. Name the cluster  webfronted and configure it to run 2 nodes:

       gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2

   - After the cluster is created, check your installed version of Kubernetes using the `kubectl version` command:

         kubectl version

2. Run and deploy a container 

     1.launch a single instance of the nginx container

       kubectl create deploy nginx --image=nginx:1.17.10

   -View the pod running the nginx container

       kubectl get services

   -Expose the nginx container to the Internet

       kubectl expose deployment nginx --port 80 --type LoadBalancer

   -View the new service

       kubectl get services

    -Scale up the number of pods running on your service:

       kubectl scale deployment nginx --replicas 3

   -Confirm that Kubernetes has updated the number of pods:

       kubectl get pods

   -Confirm that your external IP address has not changed:

       kubectl get services



