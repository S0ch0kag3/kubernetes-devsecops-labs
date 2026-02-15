Kubernetes Security: RBAC, Network Policies, and Pod Hardening

This lab focuses on securing Kubernetes workloads through role-based access control, network segmentation, and container hardening. The goal of this lab is to demonstrate how security controls reduce blast radius and prevent unauthorized access within a cluster.

## NAMESPACES
- Organise resources by namespaces,

## Role-Based Access Control

Kubernetes RBAC was used to restrict access to cluster resources by defining roles with limited permissions. A role was created that allowed read-only access to Pod resources, and a role binding was used to associate this role with a specific user or service account.

Access attempts outside the granted permissions were denied, demonstrating least-privilege enforcement.

## Network Segmentation

NetworkPolicies were applied to control east-west traffic between Pods. A default deny policy was implemented to block all traffic, followed by an allow policy that permitted communication only between explicitly approved namespaces.

This approach mirrors firewall rule design and zero-trust networking principles.

## Pod Security Hardening

Pods were configured to run as non-root users with reduced Linux capabilities and read-only root filesystems. These controls limit the impact of container compromise and reduce the likelihood of privilege escalation.

## Professional Relevance

This lab demonstrates security-first thinking in Kubernetes environments. These practices are directly applicable to cloud security engineering, DevSecOps, and compliance-driven infrastructure roles.
