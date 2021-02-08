# Feature Overview

> This section goes over some of the features in Octant in more detail than described in the project's README.

Approaching the context behind building these features is best understood by attempting the same `kubectl` commands. Having Octant open side by side with a terminal gives a good idea on what problem it is solving and potentially ways to further extend the feature.

It is also worth mentioning that `kubectl` also has plugins. There are `kubectl` plugins which can fit nicely into Octant's model of plugins or even part of the core library.

See https://github.com/ishantanu/awesome-kubectl-plugins#kubectl-plugins for some potential ideas.

Examples in the rest of this section will use the YAML below:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 3
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.7.9
        ports:
        - containerPort: 80
        - containerPort: 443
```

It should create three [pods](https://kubernetes.io/docs/concepts/workloads/pods/) running an nginx server.

> There are also features that improve the usability of Octant such as quick switcher, dark theme, and various key bindings which can be found in the help menu on the top right corner.
