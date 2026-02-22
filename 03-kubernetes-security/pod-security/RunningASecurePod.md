Running a secure pods is a critical hurdle that must be address. We can run into issue where pods are not talking with each other securely. This is address with using encrypted traffic.

secureconn.yml will show how this is done.


=================================================================

Or that a pod is running as root. This can be harmful since this could give permission to add unwanted application to our running environment. This is a vulenerabily that can 
be address by assigning a userID that's not root in the deployment file. Applying secutiy controls, like access controls was considered OWASP top 10 Broken Access Control. Allowing root control 
of a pod by default can lead to unauthorized information discloseure, modification or destruction of data. 

In this lab we will show how this deployment is secure. will allow access to a specific user, by informing Docker Containers to run as a non-root user, by referencing the userID in the yaml pod deployment.

securityContext:
    runAsUser: 1000    # Reuire use to have this userID

Under the containers attributes we can also run  
    
    - name: microservice
      image: docker.io/library/app
      imagePullPolicy:  "IfNotPresent"
      securityContext:
        allowPrivilegeEscalation: false #where sudo is not permitted
        runAsNonRoot: true  #Prevention privilege escalation
        readOnlyRootFilesystem: true    # Reduces the attack surface to completly prevent RemoteCodeExecution continuing to reduce attack surface
        capabilities:
            drop:
             - ALL



