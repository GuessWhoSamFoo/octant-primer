# CI/CD

CI/CD is done completely through Github actions.

Pipelines are responsible for:
 - Testing
 - Linting
 - Building
 - Release

[Github Actions](https://github.com/features/actions) is chosen because it supports building across Windows/MacOS/Linux along with containerized and VM environments.

Dependencies are automatically bumped through Github actions although it requires manual approval. Unless a dependency is required to be pinned, Octant aims to use the latest version whenever possible.

The repository does contain some committed and uncommitted autogenerated code. Be sure to run the generate commands before building locally.

The first time running `npm install` type commands may take some time to download dependencies and generate assets.