# @lionbridgeai/rei-node-package

![rei package](https://img.shields.io/badge/rei%20package-always%20green-brightgreen)

This is an rei (example) package.

## Install

```
$ npm install @lionbridgeai/rei-node-package
```

## Usage

```js
const rei = require("@lionbridgeai/rei-node-package");

rei();
//=> "You have succesfull installed and ran lionbridgeai's rei package"
```

# Publishing your own node(npm) packages

## Publishing/Testing from local
1. create a personal github token with following permissions: `repo`, `write:packages`
1. Do `npm login` using your github username as username and personal access token as password.
    ```bash
    npm login --scope=@lionbridgeai --registry=https://npm.pkg.github.com 
    ```
1. create a new repo for your package `<package-name>`. It is recommended to have same name for repo and package. Copy over all the files from here to your repo and edit files as necessary. You should, at least, update your `package.json` file with your package's info
1. publish your package (CI -- GH Actions should handle publishing, but you can test as follow)
    ```sh
    # run tests -- we are using jest
    npm test
    # update major, minor or patch version
    npm version major
    # publish it -- should automatically be done using GH action once you push to master
    npm publish
    ```

## Installing Packages
1. login to github packages or add corresponding entries in your `.npmrc` file
1. `.npmrc` should include line(s) specifying github package URL(s) like:
    ```sh
    @lionbridgeai:registry=https://npm.pkg.github.com
    ```
1. npm install @lionbridgeai/rei-node-package # or your package.json file
