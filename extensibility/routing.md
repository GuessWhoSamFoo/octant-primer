# Routing

The concept of routing should be familiar to any web developer.

If a plugin starts at `/plugin`, there needs to be an associated set of components to generate that view.

Then such as plugin could have additional routes like `/plugin/foo` and `/plugin/bar` which will need to be handled in a similar fashion.

Look for `router.HandleFunc` in some of the existing plugins to see different ways this can be done.
