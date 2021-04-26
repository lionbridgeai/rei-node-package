Let's publish some packages

## to publish/test from local
1. create a personal github token with following permissions: `repo`, `write:packages`
1. npm login --scope=@lionbridgeai --registry=https://npm.pkg.github.com 
1. create a folder `<package-name>` for your package and add `package.json` file with following minimum attr
  ```json
  {
   "name": "@lionbridgeai/<package-name>",
    "version": "<version>",
    "repository": "https://github.com/lionbridgeai/node-packages",
    "main": "<package-entrypoint>",
    "publishConfig": {
      "registry": "https://npm.pkg.github.com"
    }
  }
  ```
