# @coon-js/extjs-ctrl-simmanager ![MIT](https://img.shields.io/npm/l/@coon-js/extjs-ctrl-simmanager) [![npm version](https://badge.fury.io/js/@coon-js%2Fextjs-ctrl-simmanager.svg)](https://badge.fury.io/js/@coon-js%2Fextjs-ctrl-simmanager)

NPM package providing functionality for Sencha Ext JS applications to properly initialize  `Ext.ux.ajax.SimManager` 
with a `null` `defaultSimlet` so that requests not intercepted by other simlets still trigger regular
XMLHttpRequests. This package should be used whenever specific packages for intercepting 
requests are used in projects.

## Installation
```bash 
$ npm install --save-dev @coon-js/extjs-ctrl-simmanager
```

If you want to develop with `extjs-ctrl-simmanager`, run the `build:dev`-script afterwards:
```bash
$ npm run build:dev
```
Testing environment will then be available via

```bash
$ npm test
```

For using the package as an external dependency in an application, use
```bash
$ npm i @coon-js/extjs-ctrl-simmanager
```
In your `app.json`, add this package as a requirement, and make sure your   `workspace.json`
is properly configured to look up local repositories in the `node_modules`-directory.

Example (`workspace.json`) :
```json 
{
  "packages": {
    "dir": "${workspace.dir}/node_modules/@l8js,${workspace.dir}/node_modules/@conjoon,${workspace.dir}/node_modules/@coon-js,${workspace.dir}/packages/local,${workspace.dir}/packages,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name},${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-treegrid,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-base,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-ios,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-material,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-aria,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neutral,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-classic,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-gray,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-crisp,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-crisp-touch,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neptune,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-neptune-touch,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-triton,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-graphite,${workspace.dir}/node_modules/@sencha/ext-${toolkit.name}-theme-material,${workspace.dir}/node_modules/@sencha/ext-calendar,${workspace.dir}/node_modules/@sencha/ext-charts,${workspace.dir}/node_modules/@sencha/ext-d3,${workspace.dir}/node_modules/@sencha/ext-exporter,${workspace.dir}/node_modules/@sencha/ext-pivot,${workspace.dir}/node_modules/@sencha/ext-pivot-d3,${workspace.dir}/node_modules/@sencha/ext-ux,${workspace.dir}/node_modules/@sencha/ext-font-ios",
    "extract": "${workspace.dir}/packages/remote"
  }
}
```

## Usage
### Ext JS Installation
Simply update the app.json of your application by specifying this package in the `uses`-property in either the `development` and/or `prodution` section:

*Example:*
````json
{
    "development": {
        "uses": [
            "extjs-ctrl-simmanager"
        ]
    },
    "production": {
        "uses": [
            "extjs-ctrl-simmanager"
        ]
    }
}
````

When the `init()`-method of the `PackageController` of this package gets called, the `defaultSimlet` of `Ext.ux.ajax.SimManager` will
automatically get set to `null`.


## Dev
### Naming
The following naming conventions apply:

#### Namespace
`coon.simmanager.*`
#### Package name
`extjs-ctrl-simmanager`
#### Shorthand to be used with providing aliases
`cn_simmanager`

## Tests
Tests are written with [Siesta](https://bryntum.com/siesta). Documentation can be found [here](./tests/README.md).
