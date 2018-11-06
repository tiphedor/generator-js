# generator-js
Yeoman generator for a JS boilerplate project

## What will be generated ?

A boilerpate JS project structure, with babel-powered ES8 transpiling, eslint (with amazing settings provided by [yours truly](https://github.com/tiphedor/eslint-config-tiphedor), pm2, nodemon, jest unit tests, ...

## Usage

    yarn add global generator-js-tiphedor 
    # or
    npm i -g generator-js-tiphedor

    yo js-tiphedor

## Project usage

The project ships with a couple of useful scripts that you can invoke with `npm run <script>` or `yarn <script>`. Thoses scripts are: 

- `start` alias to `start:dev`
- `start:dev` Runs the project in dev mode (using `babel-node`, so with sub-optimal perfomances), watched by `nodemon`
- `start:prod` Runs `build:prod` to transpile the code, then serves the app as a pm2 deamon (so with auto-restart, ...), and then attaches the logs of the app to the terminal. `Ctrl-C` will only stop the logging, to stop the app use `stop`


- `stop` alias to `stop:dev`
- `stop:dev` stops the pm2 deamon


- `build` alias to `build:prod`
- `build:prod` transpiles the ES8 code to standard JS, and places the result in the `dist` folder.


- `test` runs `test:lint` and `test:unit`
- `test:lint` runs eslint on the whole project
- `test:unit` runs all the unit tests, located in `./src/*.{test,spec}.js`. Saves the coverage info to `./coverage`
