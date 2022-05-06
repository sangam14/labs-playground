tenablized logo 

Detect compliance and security violations across Infrastructure as Code to mitigate risk before provisioning cloud native infrastructure

# Introduction

Terrascan is a static code analyzer for Infrastructure as Code. Terrascan allows you to:

- Seamlessly scan infrastructure as code for misconfigurations. <br>
- Monitor provisioned cloud infrastructure for configuration changes that introduce posture drift, and enables reverting to a secure posture. <br>
- Detect security vulnerabilities and compliance violations. <br>
- Mitigate risks before provisioning cloud native infrastructure. <br>
- Offers flexibility to run locally or integrate with your CI\CD. <br>

# Key features

- 500+ Policies for security best practices <br>
- Scanning of Terraform (HCL2) <br>
- Scanning of Kubernetes (JSON/YAML), Helm v3, and Kustomize <br>
- Scanning of Dockerfiles <br>
- Support for AWS, Azure, GCP, Kubernetes, Dockerfile, and GitHub <br>
- Integrates with docker image vulnerability scanning for AWS, Azure, GCP, Harbor container registries.<br>
- Integrates with GitHub Actions to run scans on pull requests.<br>

# Quick Start 

# install terrascan 

 Install

Terrascan supports multiple ways to install and is also available as a Docker image. See Terrascan's [releases](https://github.com/accurics/terrascan/releases) page for the latest version of builds in all supported platforms. Select the correct binary for your platform.

Install as a native executable

```
$ curl -L "$(curl -s https://api.github.com/repos/accurics/terrascan/releases/latest | grep -o -E "https://.+?_Darwin_x86_64.tar.gz")" > terrascan.tar.gz
$ tar -xf terrascan.tar.gz terrascan && rm terrascan.tar.gz
$ install terrascan /usr/local/bin && rm terrascan
$ terrascan
```
