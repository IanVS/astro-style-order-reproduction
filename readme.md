This shows an issue which occurs in Astro.js, but only in production builds.

There are two layouts being used here, both are the same, and both import a `MainHead` component, which in turn imports global css.

There are three pages in this example:

- index: Uses Main layout
- beta: Uses Second layout
- admin: Does not use Main layout, imports `MainHead` itself.

The global css turns buttons green, but the main layout imports a file that wraps a Button component and applies a class to turn it blue.  

When building in dev, the button is blue.

Run `npm run build` then `npm run preview`, and the button will be green. 

Deleting any one of the pages seems to avoid this issue.
