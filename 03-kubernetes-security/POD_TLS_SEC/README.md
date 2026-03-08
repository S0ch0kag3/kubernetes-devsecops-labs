This lab demonstrates how Kubernetes enforces workload identity and runtime security using Service Accounts and Pod Security controls. The purpose of this exercise is to show how to securely allow workloads to access Kubernetes resources while preventing privilege escalation, root execution, and uncontrolled API access.

In Kubernetes, a Service Account represents the identity of a workload running inside a Pod. Without proper configuration, Pods may inherit excessive permissions, which increases the attack surface of the cluster.

This lab shows how to:

Create a dedicated Service Account
    

Grant minimal RBAC permissions to that account
    This is completed with the role.yaml where we name a role, provide specific resources and actions that pod-reader can access. 
    
Enforce Pod Security Standards (restricted level)

Deploy a Pod that uses the Service Account securely

Validate that access is controlled and enforced



These controls align with guidance from:

The National Institute of Standards and Technology NIST SP 800-53 (AC-6 Least Privilege, CM-6 Configuration Management)

The Center for Internet Security CIS Kubernetes Benchmark (Sections 5.1 and 5.2)

The MITRE ATT&CK for Containers (Privilege Escalation and Defense Evasion mitigation)

Zero Trust Architecture principles (identity-based access control)


