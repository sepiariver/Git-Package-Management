Define build options here.

**Wrapper:** build
```json
{
    "build":{}
}
```

#### Available properties:
* **resolver** (optional) - Resolver options
* **readme** (optional, default: docs/readme.txt) - Path to readme file
* **license** (optional, default: docs/license.txt) - Path to license file
* **changelog** (optional, default: docs/changelog.txt) - Path to change log file
* **schemaPath** (optional, default: /core/components/$lowCaseName$/model/schema/$lowCaseName$.mysql.schema.xml) - Path to the XML schema file
* **setupOptions** (optional) - Setup options object

#### Example
```json
{
    "build":{
        "readme": "docs/readme.txt",        
        "schemaPath": "_build/schema/mypackage.mysql.schema.xml"
    }
}
```

## Resolver part
Define resolver options here

**Wrapper:** resolver
```json
{
    "resolver":{}
}
```

#### Available properties:
* **resolversDir** (optional, default: resolvers) - Directory for custom resolvers
* **before** (optional, default: empty array) - Array with paths to resolvers, which will be executed before assets & core file resolvers
* **after** (optional, default: empty array) - Array with paths to resolvers, which will be executed after assets & core file resolvers
* **files** (optional, default: empty array) - Array with source and target, used to create a file resolver. (File resolvers for assets & core are created automatically)
    * Available placeholders for source item: [[+assetsPath]], [[+corePath]], [[+packagePath]]

#### Example
```json
{
    "resolver":{
        "resolversDir": "resolvers",
        "after": ["resolve.customresolver.php"],
        "files": [{
            "source": "[[+packagePath]]/move_under_assets",
            "target": "return MODX_ASSETS_PATH . 'components/';"
        }]
    }
}
```

## Setup options part
Define setup options here

**Wrapper:** resolver
```json
{
    "setupOptions":{}
}
```

#### Available properties:
* **source** (required if setup options are used) - Script that will handle setup options, must be placed in _build folder

#### Example
```json
{
    "setupOptions":{
        "source": "setup.options.php",
    }
}
```
