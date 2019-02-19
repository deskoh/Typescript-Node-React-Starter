# Typescript Node React Starter

Server:

![dependencies Status](https://img.shields.io/david/deskoh/Typescript-Node-React-Starter.svg?style=flat)
![devDependencies Status](https://img.shields.io/david/dev/deskoh/Typescript-Node-React-Starter.svg?style=flat)

Client:

![dependencies Status](https://img.shields.io/david/deskoh/Typescript-Node-React-Starter.svg?path=src-client&style=flat)
![devDependencies Status](https://img.shields.io/david/dev/deskoh/Typescript-Node-React-Starter.svg?path=src-client&style=flat)

Starter project for Node and React written in Typescript.

## Install Dependencies

* Install dependencies for server (backend)

  ```bash
  npm install
  ```

* Install dependencies for client (frontend)

  ```bash
  cd src-client
  npm install
  ```

## Folder Structure

| Name | Description |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| **.vscode**              | Contains VS Code specific settings                                                         |
| **dist**                 | Contains the output from TypeScript build for server (Node).                               |
| **public**               | Static assets that will be used client side.                                               |
| **public/dist**          | Contains the output from TypeScript build for client (React).                              |
| **node_modules**         | Contains all your npm dependencies                                                         |
| **src**                  | Contains your source code for server (Node) that will be compiled to the dist dir          |
| **src**/server.ts        | Entry point to your express app                                                            |
| tsconfig.json            | Config settings for compiling server code written in TypeScript                            |
| **src-client**           | Contains your source code for client (React) that will be compiled to the public/dist dir  |
| **src-client**/tsconfig.json | Config settings for compiling server code written in TypeScript                     |
| tslint.json              | Config settings for TSLint code style checking                                             |

## VS Code Debug Configuration

### Debug Server

For debugging server / backend Typescript source in `src` folder. No JavaScript files will be transpiled to disk.
If debugger cannot be attached fast enough for entry file, modify `--inspect` flag to `--inspect-brk` in `debug` script in `package.json`.

### Debug Server (Watch)

Same as `Debug Server` configuration but in watch mode. Server will restart and VS code will re-attach when source has changed.
No JavaScript files will be transpiled to disk.
If debugger cannot be attached fast enough for entry file, modify `--inspect` flag to `--inspect-brk` in `debug:watch` script in `package.json`.

For backend code, `nodemon` is used to restart server when backend source has changed.
The `restart` flag in `launch.json` will relaunch debug session automatically when source has changed.
> Note: Pressing the Stop button stops the debug session and disconnects from Node.js, but nodemon (and Node.js) will continue to run. To stop nodemon, you will have to kill it from the command line (which is easily possible due to the `integratedTerminal` in `launch.json`).

### Debug All

Same as `Debug Server` configuration and with frontend / client served using `webpack-dev-server`. This will cause browser to automatically refresh when source in `src-client` changes.

### Debug All (Watch)

Same as `Debug All` configuration but in watch mode. Server will restart and VS code will re-attach when source has changed.
If debugger cannot be attached fast enough for entry file, modify `--inspect` flag to `--inspect-brk` in `debug:watch` script in `package.json`.

> Note: Pressing the Stop button stops the debug session and disconnects from Node.js, but nodemon (and Node.js) will continue to run. To stop nodemon, you will have to kill it from the command line (which is easily possible due to the `integratedTerminal` in `launch.json`).

## NPM Scripts

| Npm Script | Description |
| ------------------- | ------------------------------------------------------------------------------------------------- |
| `start`             | Runs node on `dist/server.js` which is the apps entry point at localhost:3000                     |
| `dev`               | Runs backend server in watch mode at localhost:3000. TS files are transpiled in-memory            |
| `dev-all`           | Runs project (backend at localhost:3000 and frontend at localhost:8080]) in watch mode. TS files are transpiled in-memory |
| `build`             | Runs build tasks for backend                                                                      |
| `build-all`         | Full build. Runs ALL build tasks for backend and frontend                                         |
| `lint`              | Lint backend TS files                                                                             |
| `lint-all`          | Lint frontend and backend TS files                                                                |
| `debug`             | Runs backend server at localhost:3000 with the --inspect flag so that debugger can be attached    |
| `debug-all`         | The same as `debug` but with frontend running at localhost:8080                                   |
| `debug:watch`       | The same as `debug` but in watch mode.                                                            |
| `debug-all:watch`   | The same as `debug-all` but in watch mode.                                                        |
