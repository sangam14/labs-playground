refrences 

- [](https://kubernetes.io/docs/tutorials/security-context/pod-security-context/)
- [](https://kubernetes.io/docs/tutorials/security-context/container-security-context/)

# clone bad pod repo 
```
git clone http://github.com/sangam14/badpod.git
cd baseline/

```
# basline pod security context
```
controlplane $ ls
disallow-capabilities     disallow-host-ports        disallow-privileged-containers  kustomization.yaml          restrict-sysctls
disallow-host-namespaces  disallow-host-ports-range  disallow-proc-mount             restrict-apparmor-profiles
disallow-host-path        disallow-host-process      disallow-selinux                restrict-seccomp
controlplane $ cd disallow-capabilities/
controlplane $ ls
badpod.yaml  disallow-capabilities.md  goodpod.yaml  resource.yaml  test.yaml
controlplane $ kubectl apply -f resource.yaml --namespace=my-baseline-namespace
pod/goodpod01 created
pod/goodpod02 created
pod/goodpod03 created
pod/goodpod04 created
pod/goodpod05 created
pod/goodpod06 created
Warning: would violate PodSecurity "baseline:latest": non-default capabilities (container "container01" must not include "NET_RAW" in securityContext.capabilities.add)
deployment.apps/baddeployment01 created
deployment.apps/baddeployment02 created
deployment.apps/baddeployment03 created
Warning: would violate PodSecurity "baseline:latest": non-default capabilities (container "initcontainer01" must not include "NET_RAW" in securityContext.capabilities.add)
deployment.apps/baddeployment04 created
Warning: would violate PodSecurity "baseline:latest": non-default capabilities (container "initcontainer02" must not include "NET_RAW" in securityContext.capabilities.add)
deployment.apps/baddeployment05 created
Warning: would violate PodSecurity "baseline:latest": non-default capabilities (containers "initcontainer01", "container01" must not include "NET_RAW", "SYS_ADMIN" in securityContext.capabilities.add)
deployment.apps/baddeployment06 created
deployment.apps/gooddeployment01 created
deployment.apps/gooddeployment02 created
deployment.apps/gooddeployment03 created
deployment.apps/gooddeployment04 created
deployment.apps/gooddeployment05 created
deployment.apps/gooddeployment06 created
cronjob.batch/badcronjob01 created
cronjob.batch/badcronjob02 created
cronjob.batch/badcronjob03 created
cronjob.batch/badcronjob04 created
cronjob.batch/badcronjob05 created
cronjob.batch/badcronjob06 created
cronjob.batch/goodcronjob01 created
cronjob.batch/goodcronjob02 created
cronjob.batch/goodcronjob03 created
cronjob.batch/goodcronjob04 created
cronjob.batch/goodcronjob05 created
cronjob.batch/goodcronjob06 created
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod01" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (container "container01" must not include "NET_RAW" in securityContext.capabilities.add)
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod02" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (container "container01" must not include "NET_RAW" in securityContext.capabilities.add)
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod03" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (container "container01" must not include "NET_RAW" in securityContext.capabilities.add)
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod04" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (container "initcontainer01" must not include "NET_RAW" in securityContext.capabilities.add)
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod05" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (container "initcontainer02" must not include "NET_RAW" in securityContext.capabilities.add)
Error from server (Forbidden): error when creating "resource.yaml": pods "badpod06" is forbidden: violates PodSecurity "baseline:latest": non-default capabilities (containers "initcontainer01", "container01" must not include "NET_RAW", "SYS_ADMIN" in securityContext.capabilities.add)
controlplane $ 

```

if you see in above multi yaml file contain padpods the pod security admission controller will not allow the pod to be created.

