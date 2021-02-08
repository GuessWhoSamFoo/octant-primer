# Octant Components

A major difference with Octant and similar projects is how it is built with a component library. 

Components are building blocks in the UI. Octant uses [Clarity](https://clarity.design/) to build its front end components.

To disambiguate the difference between an Octant and Clarity component, an Octant component is a wrapper around a Clarity component. Octant adds additional code around Clarity to highlight the parameters of each component that matters in this use case and help developers avoid knowing anything about Clarity to start coding.

This means not all components in Clarity are Octant components. In fact, an Octant component does not have to use Clarity at all. If there is some UI component that appears to be missing in Octant, the first place to look would be Clarity's documentation for that component. If it exists, it can be added with relative ease to Octant as most concerns such as CSS, accessibility, and performance are already addresses. If not, a discussion on Github or Slack should be raised about adding such a component along with the use case.

As Octant matures, the available components will grow to meet use cases that are not currently known.
