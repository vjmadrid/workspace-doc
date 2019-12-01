# Configuration Minikube

Tool that runs a single-node Kubernetes cluster in a virtual machine on local computer

[install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install](#install)
- [Use](#use)






## <a name="check-prerequisites">Check Prerequisites</a>

* Verify that the virtualization is supported (Depends SO)
* Verify that kubectl is installed
* Verify that Hypervisor is installed





## <a name="install">Install</a>

1. Execute the following instructions

[Install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

2. Verify installation

```bash
kubectl version
```




## <a name="use">Use</a>

```bash
# start minikube
$ minikube start

# explore options
$ minikube --help

# check config options
$ minikube config --help

# open dashboard
$ minikube dashboard

# stop minikube
$ minikube stop

# delete minikube
$ minikube delete
```





## Authors

* **Víctor Madrid**
