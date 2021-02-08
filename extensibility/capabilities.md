# Capabilities

Capabilities is an internal concept used within Octant to describe what sorts of things a plugin is allowed to do.

For example, a plugin could add an additional tab given one more more object types.

A plugin could also be declared as a module. 

Modules mean that plugin can create a new entry on the navigation bar and will be responsible for defining paths/routes for various pages that the plugin will show.

Lastly, actions can be added to a plugin. The action can be an API call, invoke some change to the UI, or whatever code the plugin author wants to run.
