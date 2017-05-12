This example shows how to create an explicit vendor chunk as well as a common chunk for code shared among entry points. 

In this example, we have 2 entry points: `index`, `index2`. 

Those entry points share some of the same utility modules, but not others. 

This configuration will pull out any modules common to at least 2 bundles and place it it the `common` bundle instead.

To better understand, here are the entry points and which utility modules they depend on:

- `index`
  - `axios`
  - `util/util1`
- `index2`
  - `axios`
  - `util/util1`
  - `util/util2`

Given this configuration, webpack will produce the following bundles:

- `common`
  - webpack runtime
  - `axios`
  - `util/util1`
- `index`
  - 
- `index2`
  - `util/util2`