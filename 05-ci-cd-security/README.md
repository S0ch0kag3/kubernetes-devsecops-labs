I/CD Security and Container Image Scanning

This lab demonstrates how security controls can be integrated into continuous integration pipelines to prevent vulnerable workloads from reaching production environments.

## Pipeline Overview

A GitHub Actions workflow was created to build a container image and scan it for known vulnerabilities. The pipeline was configured to fail when critical vulnerabilities were detected.

## Security Impact

By enforcing security checks during the build process, vulnerabilities are identified early in the development lifecycle. This approach reduces remediation cost and prevents insecure images from being deployed.

This lab demonstrates  security controls directly into delivery pipelines rather than relying on manual review processes.

