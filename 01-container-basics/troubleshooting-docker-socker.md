This environment uses Rancher Desktop to provide a local Kubernetes cluster and Docker-compatible container runtime. The system runs on Windows with WSL2 enabled to provide a Linux-compatible execution environment.
Docker commands are executed from a terminal that communicates with the Docker daemon running inside the Rancher Desktop virtual machine.

## Problem Encountered

When attempting to run a Docker container using the Docker CLI, the following error was encountered:

[failed to connect to the Docker API at unix://var/run/docker.sock]

This error indicates that the Docker client was unable to communicate with the Docker daemon through the expected Unix socket. At this point, Docker was installed, but the container runtime was not accessible.

## Investigation and Root Cause

After reading a few reddit blog posts I found myself running down a Rancher Desktop manages container runtimes. Rancher Desktop supports both `containerd` and `dockerd` as runtime options. While `containerd` is Kubernetes-native, it does not expose a Docker-compatible socket by default.
As a result, Docker CLI commands fail when the runtime is set to `containerd`.

Additionally, WSL integration must be explicitly enabled for the Linux distribution being used. Without this integration, the Docker socket is not visible to the terminal environment.

## Resolution

The issue was resolved by configuring Rancher Desktop to use the `dockerd (moby)` runtime, enabling WSL integration for the active Linux distribution, and restarting Rancher Desktop to apply the changes. After these steps, the Docker daemon became accessible through the Docker socket.

Docker functionality was verified by running the following command:

```bash
docker run hello-world
