# Installation - Configuration Kubectl

Tool that runs a single-node Kubernetes cluster in a virtual machine on local computer

[install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Install](#install)
- [Concepts](#concepts)
- [Use](#use)
- [Plugins](#plugins)





## <a name="check-prerequisites">Check Prerequisites</a>

* Verify that the virtualization is supported (Depends SO)
* Verify that kubectl is installed
* Verify that Hypervisor is installed





## <a name="install">Install</a>

1. Execute the following instructions

[Install Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)





## <a name="concepts">Concepts</a>


- [Kubectl](#kubectl)
- [Cluster](#cluster)
  - [Context](#context)
  - [Kubeconfig](#kubeconfig)
- [Master](#master)
- [Nodes](#nodes)
  - [Proxy](#proxy)
- [Pod](#pod)
- [Service](#service)




### <a name="kubectl">Kubectl</a>

Kubernetes Control Tool -> Program que lets us : 

* Interact and management with multiples Kubernetes clusters 
* Interact, manage and deploy applications

Optional : Use alias (For example : "k")

Check the installation

```bash
kubectl version

or

k version
```

Show Help

```bash
kubectl --help
```

Check cluster info

```bash
kubectl cluster-info
```

Check API versions

```bash
kubectl api-versions
```

#### Syntax

```bash
kubectl <command> <type> <name> <flags>
```

* command : The command or operation to perform -> "apply", "create", "delete", "get" , "describe", "logs" ...
* type : The resource type or object
* name : The name of the resource or object
* flags [Optional] : Flags to pass to the command

**Syntax "create" command**

```bash
# Basic
kubectl create <type> <flags>

# With Manifest
kubectl create -f <path_manifest>
```




### <a name="cluster">Cluster</a>

Master + Nodes (Minions) -> The Master decides what will run
* Series of nodes connected together

#### <a name="context">Context</a>

Combination of cluster, namespace and user

* cluster : A friendly name, server address, and certificate for the Kubernetes cluster
* namespace [Optional] : The logical cluster or environment to use
  * If none is provided, it will use the default default namespace
* user : The credentials used to connect to the cluster
  * This can be a combination of client certificate and key, username/password, or token

These contexts are stored in a local yaml based config file referred to as the kubeconfig. For *nix based systems, the kubeconfig is stored in $HOME/.kube/config for Windows, it can be found in %USERPROFILE%/.kube/config

This config is viewable without having to view the file directly

Understanding and being able to switch between contexts is a base fundamental skill required by every Kubernetes user. As more clusters and namespaces are added, this can become unwieldy. Installing a helper application such as kubectx can be quite helpful. Kubectx allows a user to quickly switch between contexts and namespaces without having to use the full kubectl config use-context command.

List context and show the current context

```bash
kubectl config get-contexts
```

List context and show the current context

```bash
kubectl config current-context
```

Create context

```bash
kubectl config set-context <context_name> --cluster=<cluster_name> --user=<user_name> --namespace=<namesapace_name>
```

Switch current context

```bash
kubectl config use-context <context_name>
```

List all the namespaces

```bash
kubectl get namespaces
```

#### <a name="kubeconfig">Kubeconfig</a>





### <a name="master">Master</a>

A node or nodes that are in charge of managing the Kubernetes cluster state





### <a name="nodes">Nodes</a>

Worker machine (virtual or a physical machine -> depending on the cluster)

Each Node is managed by the Master

A Node can have multiple PODs

Show Nodes available to do work

```bash
kubectl get nodes
```

Each Node execute at least a : 

* Kube proxy : main interface for communications between nodes
* Kubelet : responsible for the POD specification and talks to the cri interface
* Container runtime (Docker , Rocket) : responsible for pulling the container image from a registry, unpackaking the container and running the application

#### <a name="proxy">Proxy</a>

1. Open a new terminal and execute the following command

```bash
kubectl proxy
```
For example :  Starting to serve on 127.0.0.1:8001

This command says that exist an API that you can query with HTTP request


2. Open a new terminal and execute the following command


* Show all endpoints -> Kubernetes proxy routes

```bash
curl http://127.0.0.1:8001
```

* Select "version" endopoint -> Similar to use command version

```bash
curl http://127.0.0.1:8001/version
```

```bash
curl http://localhost:8001/api/v1/namespaces/default/pods/$POD_NAME

or

curl http://localhost:8001/api/v1/namespaces/<namespaces>/pods/<pod_name>/proxy
```

<pod_name> : Use command get pods

You can get your machine’s IP address by using this:

```bash
curl https://ipv4.icanhazip.com
```

Then, using that IP address, run our application such as in this example:


kubectl exec $POD_NAME env

kubectl exec -ti $POD_NAME bash


kubectl run --generator=run-pod/v1  --image=vjmadrid/node:latest teest

kubectl run --generator=run-pod/v1 --dry-run --image=vjmadrid/node:latest teest -o yaml >> test.yaml




### <a name="pod">POD</a>

Smallest deployable unit / atomic unit that constists of one o many containers
Use differente containers : docker, crio, etc

hold one or more containers. Containers that share the same pod also share resources and network. Pod can be in charge of containers on different nodes- different physical machines or virtual machine(VM). It serves as unit of deployment, horizontal scaling, and replication

Kubernetes API - Server (REST) that runs on the master node and speaks directly with the kubelets running on the nodes.

Resources :

* Shared storage : Volumes
* Networking : unique cluster IP address
* Information : how to run each container -> Image + port

Pods run in a private isolated network 
Pods are visible from other Pods and services -> Can't be acceses outside the network (for example no use curl command)

A Pod always execute on Node

* 

The containers in a POD :
* share an IP addres an space port
* always co-located
* co-scheduled

Exist diferente ways to expose the appllication to the outside world


List all the pods

```bash
kubectl get pods
```

A POD has lifecycle
* Is Workes node dies, the PODs running on the Nodo are also lost

kubectl describe {pod/service/node} {name of pod/service/node}

kubectl logs {name of node}


kubectl delete --all pods
kubectl delete --all pods --namespace=value





#### PodSpec

Yaml or JSON file that describes the pod spec. It is used by kubelet to make sure that the containers are healthy and running according to expectations

This yaml file describe to K8s, pods and kubelet how we want our app to run, what is the deployments and the services in use. Each deploy component in our file starts with apiVersion followd by kind, metadata and spec In our file we have one service named- azure-spring-kotlin-front-virtual-service
and one deployment named: azure-spring-kotlin-front-virtual.
Under deployment and under spec -> template -> spec we have the configuration for the node selector, we might have many nodes in our cluster, and we would like this app to be deployed to our virtual node one and not to the rest





### <a name="service">Service</a>

A ReplicaSet is a high-level artifact that can drive the cluster back to desired state via the creation of new Pods to keep your application running

```bash
kubectl get services
```





### <a name="deployment">Deployment</a>

XXX

```bash
kubectl get deployment
```










## <a name="use">Use</a>





## <a name="plugins">Plugins</a>

* Autocompletion
  * https://thorsten-hans.com/autocompletion-for-kubectl-and-aliases-using-oh-my-zsh
  * https://danielkorn.io/post/kubectl-autocomplete/
https://github.com/junegunn/fzf
https://github.com/jonmosco/kube-ps1
https://github.com/ahmetb/kubectx

 



## Authors

* **Víctor Madrid**
