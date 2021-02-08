# Architecture

The overall architecture of Octant is simple because it can be deployed as a standalone binary.

The server is responsible for 

```
+------------------+
|Kubernetes Cluster|
+------+-+---------+
       ^ |
       | |
       | |
       | |
       | |
       | v
    +--+-----+                                        +---------------------------+
    | Server +--------------------------------------> | Client (Angular/Electron) |
    +--------+   ws://localhost:7777/api/v1/stream    +---------------------------+
```

> Not shown are plugin(s) which is another extension of the server.

The codebase is divided into two portions: an internal portion under `internal/` and public code for imports under `pkg/` (technically three if the client side under `web/` is included since the project is a monorepo). The server looks for a kubeconfig on the local filesystem and uses it to autheticate with the cluster. This allows viewing a cluster locally without the need to handle security concerns unlike the Kubernetes dashboard running in cluster. Then Octant creates UI components for objects found in the cluster and streams it to a client to show changes in real time.

Some terminology for neophytes:
 - object: a programming paradigm. In Octant and Kubernetes, this refers to a resource in the cluster. See [Kubernetes object](https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/)
 - client-go: a Golang library for taking to a Kubernetes cluster. See [client-go](https://github.com/kubernetes/client-go)
 - event: some message that Octant sends to the client
 - kubeconfig: file used to access a cluster. See [kubeconfig](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)

```
internal
├── api - Web server and websocket
├── cluster - Clients from client-go
├── commands - Flags for configurations on the command line
├── config - Configuration for getting the current state of Octant
├── context - Request specific data using context
├── conversion - Helpers to convert from types
├── describer - Creates UI components given a Kubernetes object
├── errors - Typed errors used to handle special error cases
├── event - Generators for events
├── generator - Creates components sent to client over websocket
├── gvk - Support Kubernetes objects in Octant
├── kubeconfig - Consolidates data from one or more kubeconfigs
├── link - Utility to create an URL link from an object
├── loading - Checks if an object is loading
├── log - Structure logs for output
├── mime - Sets MIME type
├── module - A group of paths for an object(s). Effectively an internal plugin
├── modules - List of internal modules
├── objectstatus - Sets a status for a given object (Ok, warning, error)
├── objectstore - Internal object store of Kubernetes objects
├── objectvisitor - Visitors used to create a graph of Kubernetes objects
├── octant - Methods for how Octant can interact with the cluster
├── portforward - Maintains port forwards
├── printer - Decides what components should be shown given an object
├── queryer - Handles finding relationships between objects in Kubernetes
├── resourceviewer - Graph of the relationship between objects
├── terminal - Creates a terminal to run commains in a container
├── testutil - Helpers for unit testing
└── util - DRYness goodness
```

```
pkg
├── action - Allow clients to perform some operation on a cluster
├── cluster - Interface for cluster and namespace information
├── config - Configure gRPC message sizes
├── dash - Coordinate the start of the event loop
├── event - List of event types
├── icon - Names of icons
├── log - Logger interface
├── navigation - Generates data for the navigation bar
├── octant - Sets up handlers for the server
├── plugin - Support for plugins in Golang or Typescript
├── store - CRUD operators for objects in a cluster
└── view - UI component schemas and interface
```
