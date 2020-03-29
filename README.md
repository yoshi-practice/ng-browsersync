<h3 align="center">ng-browsersync</h3>
<p align="center">Sample application as Angular with Browsersync .</p>

## Steps

### Setup angular project

```
$ ng new <APPLICATION_NAME>
```

### Install browsersync and dependencies

```
$ npm install --save-dev browsersync npm-run-all rimraf wait-on
```

### Create Browsersync config

```
$ browser-sync init
```

### Edit config

```javascript:bs-config.js
module.exports = {
  server: {
    baseDir: "dist/ng-browser-sync",
    watch: "true",
    middleware: [require("connect-history-api-fallback")()],
    routes: {
      "/node_modules": "node_modules"
    }
  }
};
```

### Edit start script

```json:json
    "prestart": "npm run clean",
    "start": "run-p build serve",
    "build": "ng build --watch",
    "serve": "wait-on dist/index.html && browser-sync start --config bs-config.js",
    "clean": "rimraf dist"
```

## Run

### Start with browsersync

```
$ npm run start
```

### Only build

```
$ npm run build
```

### Only start browsersync

```
$ npm run serve
```
