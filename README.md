# lib-cn_simmanager
This **Sencha ExtJS** package provides functionality to initialize the Ext.ux.ajax.SimManager 
with a `null` `defaultSimlet` so that requests not intercepted by orther simlets still trigger regular
XMLHttpRequests. This package should be used whenever specific packages for intercepting 
requests are used in projects.

## Naming
The following naming conventions apply:

#### Namespace
`coon.simmanager.*`
#### Package name
`lib-cn_simmanager`
#### Shorthand to be used with providing aliases
`cn_simmanager`

## Tests
Tests are written with [Siesta](https://bryntum.com/siesta)

# Usage
## Requirements
This package requires the [lib-cn_core](https://github.com/coon-js/lib-cn_core) package of the [coon.js](https://github.com/coon-js) project.

### Installation
Simply update the app.json of your application by specifying this package in the `uses`-property in either the `development` and/or `prodution` section:

*Example:*
````javascript
"development": {
        "uses" : [
            "lib-cn_simmanager"
        ]
},
"production": {
        "uses" : [
            "lib-cn_simmanager"
        ]
}
````

When the `init()`-method of the `PackageController` of thi package gets called, the `defaultSimlet` of `Ext.ux.ajax.SimManager` will 
automatically get set to `null`.

