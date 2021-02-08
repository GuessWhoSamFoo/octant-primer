# How to use Storybook

## What is Storybook?

[Storybook](https://github.com/storybookjs/storybook) is a tool that helps front end libraries document their UI components. UI components composed of modular and reusable code that allows programmers to create a standardized UI across one or more projects.

A tool available to understand what UI capabilities are possible in Octant is through: https://reference.octant.dev/

There is an expandable list of components on the side bar showing all the components available as well as usage patterns. After selecting a component, the `Docs` tab also has a code snippet.

Another way to explore ways to tune these components is through the `Knobs` tab on the bottom under `Canvas`. It allows directly editing the JSON stream sent from the server to show what a component might look like.

For example, given the `text` component:

```
{
  "metadata": {
    "type": "text"
  },
  "config": {
    "value": "hello world",
    "isMarkdown": false
  }
}
```

We can see `value` holds the text to be displayed and a flag that allows representing the value as Markdown. Try changing `isMarkdown` to `true` and the value to `**hello world**`.

It is also possible to display multiple nested components in this way as well.
