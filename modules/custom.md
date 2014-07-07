### Create custom modules


Create a subfolder in the modules/addons folder of your cockpit installation (e.g. _MyModule_).

**In general a module just needs two files:**

1. Manifest file _modules/addons/MyModule/module.json_.
2. Bootstrap file _modules/addons/MyModule/bootstrap.php_.


---

#### module.json

This manifest file contains your module's metadata (name, version, license etc).

````
{
    "name"       : "MyModule",
    "version"    : "1.0",
    "description": "MyModule description",
    "homepage"   : "",
    "license"    : "MIT"
}
````


#### bootstrap.php

This file contains all the code to bootstrap your module.