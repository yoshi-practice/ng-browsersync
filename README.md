<h3 align="center">ng-browsersync</h3>
<p align="center">Sample application as Angular with Browsersync .</p>

## Steps

### Setup angular project

```
$ ng new <APPLICATION_NAME>
```

### Install browsersync

```
$ npm install --save-dev browsersync
```

### Create Browsersync config

```
$ npx browser-sync init
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
