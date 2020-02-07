# lib-cn_simmanager - Tests - Read Me

lib-cn_simmanager uses [Siesta](http://bryntum.com) for Unit/UI testing.

Make sure you set the paths to the resources properly in the files index.html.template and
tests.config.js.template, then rename them:

```
index.html.template -> index.html
tests.config.js.template -> tests.config.js
```

The tests require [lib-cn_core](https://github.com/coon-js/lib-cn_core). Make sure you adjust the paths to
this library in the index.js if both packages are not part of a regular local
package directory layout in a sencha workspace.


## Using Modern/ Classic Toolkit for the tests
 - Code is universal so no specific toolkit is required for running the tests
 
 *Example-URL:*
 `http://localhost:1841/packages/local/lib-cn_simmanager/tests