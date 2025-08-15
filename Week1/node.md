# Node.js

## What is Node.js?

- "Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine."
- "Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient."
- "Node.js' package ecosystem, npm, is the largest ecosystem of open source libraries in the world."

## Usage

Running js script:

```bash
node my-script.js
```

### Exercise

Create a folder `node-test`. In the folder create file `script.js` that logs 'This is JavaScript' to console, and run it.

## npm

- npm (Node Package Manager) is the package manager for Node.js
- Used to install, share, and manage dependencies in Node.js projects
- Has the most modules of any package manager for any language
- Comes along with Node.js
- Available on command line with npm command
- [npm registry](https://www.npmjs.com/) let you [search](https://docs.npmjs.com/searching-for-and-choosing-packages-to-download) for existing package
- Can update itself with
  ```bash
  npm install -g npm
  ```
  or short version:
  ```bash
  npm i -g npm
  ```

## Package.json

- JSON file to define a [npm project](https://docs.npmjs.com/creating-a-package-json-file)
- Contains all the dependencies and metadata for the project
- Can [contain](https://docs.npmjs.com/files/package.json):
  - Project name, description, version, license etc.
  - Dependencies
  - Required node version (engines)
  - npm scripts (covered later)
  - etc.
- When installing a package, npm will automatically update the `package.json` file
  - Make sure to double check the `package.json` file after installing a package

## Dependencies

- Multiple types of dependencies:
  - dependencies for actual run-time dependencies
  - devDependencies for development-time dependencies such as test frameworks and bundlers
  - peerDependencies for requiring certain versions of other modules to be installed when used (used for example for plugins)
- Dependencies can point to npm registry, Git repository, tar ball, local path
- Dependency versions can be specified as specific, greater/lower than, ranges, etc.

## Initializing new project

Run `npm init` and answer all the interactive questions to populate simple package.json (hint: first create a remote git repository (in gitlab or github or ...), clone it locally and run the `npm init` in that cloned directory).

## Installing dependencies

Install all dependencies (dependencies & devDependencies):

```bash
npm install
```

Install dependencies only:

```bash
npm install --production
```

All dependencies are stored to node_modules folder.

## Adding new dependencies

To add a new dependency for your project, you can use

```bash
npm install --save express
```

or shorter:

```bash
npm i express
```

which installs the new package to `node_modules` and adds it to the `package.json`

`--save-dev` or `-D` to save in `devDepencencies`

Using the dependencies: `const express = require('express');`

## Custom npm scripts

`scripts` field in `package.json` can contain custom scripts

```json
{
  "scripts": {
    "build": "tsc",
    "create-some-folder": "mkdir some && cd some && mkdir other"
  }
}
```

To run these, use:

```bash
npm run build
npm run create-some-folder
```

Certain scripts (e.g. `start` and `test`) are available without the `run`, for example:

```bash
npm start
npm run start
```
