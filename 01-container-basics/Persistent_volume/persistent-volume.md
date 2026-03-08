PERSISTENT VOLUMES

Containers are ephemeral and when a container stops or is removed, any data written inside it disappears. This works well for stateless applications, but databases, file uploads, configuration files, and application state need to survive container restarts. 
Docker volumes solve this problem by providing persistent storage that lives independently of container lifecycles.

This lab demonstrates the separation between version control and runtime environments. 
Although application files were tracked in Git, they were not available to the container until explicitly mounted using a Kubernetes volume
A bind-mounted volume was used to demonstrate persistent storage. The host directory exists inside the Git repository for documentation purposes, while runtime data is excluded from version control to prevent accidental leakage of stateful or sensitive information.
