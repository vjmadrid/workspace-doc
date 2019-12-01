# Configuration Kubectl

Tool that runs a single-node Kubernetes cluster in a virtual machine on local computer

[install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install](#install)
- [Use](#use)
- [Plugins](#plugins)






## <a name="check-prerequisites">Check Prerequisites</a>

* Verify that the virtualization is supported (Depends SO)
* Verify that kubectl is installed
* Verify that Hypervisor is installed





## <a name="install">Install</a>

1. Execute the following instructions

[Install Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)





## <a name="use">Use</a>

```bash

```


kubectl run --generator=run-pod/v1  --image=vjmadrid/node:latest teest

kubectl run --generator=run-pod/v1 --dry-run --image=vjmadrid/node:latest teest -o yaml >> test.yaml



## <a name="plugins">Plugins</a>

https://github.com/junegunn/fzf
https://github.com/jonmosco/kube-ps1
https://github.com/ahmetb/kubectx
 





## Authors

* **Víctor Madrid**
