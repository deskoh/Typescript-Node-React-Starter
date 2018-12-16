# Typescript Node React Starter

Starter project for Node and React written in Typescript.

## Install Dependencies

* Install dependencies for server (backend)

  ```
  npm install
  ```

* Install dependencies for client (frontend)

  ```
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

### Debug TS

Runs `npm debug` script and attach debugger. TS code will be transpiled in memory.

### Debug TS (Watch)

Runs `npm debug:watch` script and attach debugger.
TS code will be transpiled in memory.
For backend code, `nodemon` is used to cause server to restart when backend source has changed.
The `restart` flag in `launch.json` will relaunch debug session automatically when source has changed.
For frontend code, `webpack-dev-server` is used and browser will be automatically reload when frontend source has changed.
> Note: Pressing the Stop button stops the debug session and disconnects from Node.js, but nodemon (and Node.js) will continue to run. To stop nodemon, you will have to kill it from the command line (which is easily possible due to the `integratedTerminal` in `launch.json`).

## NPM Scripts

| Npm Script | Description |
| ------------------------- | ------------------------------------------------------------------------------------------------- |
| `start`                   | Runs node on `dist/server.js` which is the apps entry point                                       |
| `dev`                     | Runs project in watch mode.  Backend TS files are transpiled in memory, frontend TS files are served from memory |
| `build`                   | Full build. Runs ALL build tasks for backend and frontend                                         |
| `build:watch`             | Builds backend TS file in watch mode                                                              |
| `lint`                    | TSLint frontend and backend TS files                                                              |
| `debug`                   | Transpiles backend TS files in memory and runs with the --inspect-brk flag so that debugger can be attached |
| `debug:watch`             | The same as `debug` but in watch mode.                                                            |
