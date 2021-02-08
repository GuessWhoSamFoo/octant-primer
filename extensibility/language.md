# Typescript vs Golang

There are two languages supported for plugins: Typscript and Golang.

Golang is supported because a lot of the Kubernetes ecosystem is written in Go. This allows importing libraries rather than building projects from scratch. However, there are a few drawbacks. The first is that each plugin must be compiled for a specific OS. This presents a challenge as plugin authors will also have to consider distribution of a plugin.

The second drawback is the lack of hot reloading during development. A Go plugin needs to shutdown and restart if a plugin author made a code change.

Typescript solves this problem as it does not need to be compiled. In addition, there is a scaffolding tool available on npm to bootstrap a new plugin:

https://www.npmjs.com/package/@project-octant/generator-octant-plugin

Octant is committed to supporting both although Typescript will receive primary development efforts. Choosing which language for a plugin will depend on the use case.
