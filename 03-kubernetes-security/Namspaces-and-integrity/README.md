This lab demonstrates namespace-based isolation and a controlled promotion model for Kubernetes workloads. 
Resources are deployed in a non-public namespace, validated for configuration integrity, and redeployed into a public namespace only after approval. 


In the video the recording stopped before the valid deployment out could be shown. This output can be view viewed below

========================================================================

zoe@DESKTOP-D2KVGL8:/mnt/c/Users/EmanservicesLLC/Desktop/kubernetes-devsecops-labs/03-kubernetes-security/Namspaces-and-integrity$ kubectl get deployments
NAME            READY   UP-TO-DATE   AVAILABLE   AGE
validated-web   2/2     2            2           57m


===========================================================================


Kubernetes environments are secured after a workload is proven functional. Instead of allowing unrestricted access and open networking, the validated namespace is protected using role-based access control
network isolation, and a formal deployment checklist. This mirrors how real organizations enforce separation of duties, limit blast radius, and prevent accidental or malicious changes in higher environments.
