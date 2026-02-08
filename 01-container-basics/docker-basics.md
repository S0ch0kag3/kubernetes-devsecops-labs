DOCKER BASICS

Theres a few ways we can deploy docker, Im currently using Rancher for my deployments. Theres also Docker Desktop which uses a 
a hidden virtual machine or subsytem to run and isolated instance for Docker. Once fully installed you can have a cli of different docker instances at your
finger tips.

Once Docker is installed this setups a container runtime that in turn, uses Containerd and run to to run containers. Docker is lightweight scalable and can be 
used with automation to have resources allocated at all times.

Containers images are bundles of dependencites and software allowing us to run software conststiently across different compute environments. We should rely on OCI
compliant image create which can be used in Kubernetes Docker and AWS EKS. Now how does container images and containers work together is Container deploy OCI images to containers
and containers can run replicas of the same image or multiple instances of the image depending on the customer needs.

Images are hosted and shared with outhers on a containers registry, Docker has its own registry Docker-hub and redhat user quay.io

docker pull docker.io/  

Aboce will pull images to the container 

docker run [image] 

Here are some commands that we can run in DOCKER

docker ps  This will show you running docker instances



