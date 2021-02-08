# Prerequisites

> Some knowledge of Kubernetes is helpful, but not required. The process of installing Octant can be useful for someone new to Kubernetes. However, comfort with the command line and usage of containers is useful.

## Install [kind](https://github.com/kubernetes-sigs/kind)

KinD (Kubernetes in Docker) is a tool to run a locally using Docker. This is useful for having a sandbox to experiment with tools without using a cloud service where there might be concerns of racking up unexpected charges.

## Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

`kubectl` allows running commands on a cluster from the command line. It is helpful to see the motivations behind Octant by using `kubectl` to get information about the cluster.

## Install [Octant](https://github.com/vmware-tanzu/octant/releases)

Finally, download Octant. As of writing this, Octant exists as a binary and an Electron application. The long term vision is moving to Electron entirely, but it is fine to run the binary `./octant` which opens a tab in the browser.

At this point, the best way to understand Octant is to apply some resources and see what shows up in the browser. Example of things to try out are:
 - [Guestbook application](https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-app/deploy-interactive/)
 - [nginx Deployment](https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/)

 Theses examples are mostly copy/paste and useful to get acquainted with Kubernetes resources.