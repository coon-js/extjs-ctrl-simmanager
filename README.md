# @coon-js/extjs-app-simmanager
NPM package providing functionality for Sencha ExtJS applications to properly initialize  `Ext.ux.ajax.SimManager` 
with a `null` `defaultSimlet` so that requests not intercepted by orther simlets still trigger regular
XMLHttpRequests. This package should be used whenever specific packages for intercepting 
requests are used in projects.

## Installation
```
npm install --save-dev @coon-js/extjs-lib-core
```

## Usage
### Requirements
This package requires the [extjs-lib-core](https://github.com/coon-js/extjs-lib-core) package of the [coon.js](https://github.com/coon-js) project.

### ExtJS Installation
Simply update the app.json of your application by specifying this package in the `uses`-property in either the `development` and/or `prodution` section:

*Example:*
````javascript
"development": {
        "uses" : [
            "extjs-app-simmanager"
        ]
},
"production": {
        "uses" : [
            "extjs-app-simmanager"
        ]
}
````

When the `init()`-method of the `PackageController` of thi package gets called, the `defaultSimlet` of `Ext.ux.ajax.SimManager` will
automatically get set to `null`.



## Post-Install
[@coon-js/extjs-link](https://npmjs.org/coon-js/extjs-link) will start once the package was installed and guide you
through the process of creating symlinks to an existing ExtJS sdk installation.
This is only required if you want to run the tests (`./tests`), as [Siesta](https//npmjs.org/siesta-lite) relies on
an existing ExtJS installation.

## Dev
### Naming
The following naming conventions apply:

#### Namespace
`coon.simmanager.*`
#### Package name
`extjs-app-simmanager`
#### Shorthand to be used with providing aliases
`cn_simmanager`

## Tests
Tests are written with [Siesta](https://bryntum.com/siesta)