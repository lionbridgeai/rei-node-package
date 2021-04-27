Let's publish some packages

## Publishing/Testing from local
1. create a personal github token with following permissions: `repo`, `write:packages`
1. npm login --scope=@lionbridgeai --registry=https://npm.pkg.github.com 
1. create a new repo for your package `<package-name>`. It is recommended to have same name for repo and package. Your package would have `package.json` file with following minimum attr
    ```json
    {
      "name": "@lionbridgeai/<package-name>",
      "version": "<version>",
      "repository": "https://github.com/lionbridgeai/<repo-name>",
      "main": "<package-entrypoint>",
      "publishConfig": {
        "registry": "https://npm.pkg.github.com"
      }
    }
    ```
1. publish your package (CI -- GH Actions or Jenkins should handle publishing :), but you can test as follows)
    ```sh
    npm version major # or update your package.json manually
    npm publish # that's it
    ```


## Installing Packages
1. login to github packages or add corresponding entries in your `.npmrc` file
1. `.npmrc` should include line(s) specifying github package URL(s) like:
    ```sh
    @lionbridgeai:registry=https://npm.pkg.github.com
    ```
1. npm install @lionbridgeai/rei-node-package # or your package.json file