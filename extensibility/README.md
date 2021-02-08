# Extensibility

When describing Octant as extensible through plugins, it is useful to describe what that means in terms of changes to a view.

There are a list of existing plugins to show various ways to enchance Octant: https://github.com/topics/octant-plugin

> If you have Go installed, there is a sample plugin that can be built via `go run build.go install-test-plugin` from the project root directory.

Generally plugins do one or more:
 - Add existing data to an existing view
 - Create a new module and entirely new pages to show
 - Run some custom code based on interaction with UI
