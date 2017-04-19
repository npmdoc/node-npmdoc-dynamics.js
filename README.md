# npmdoc-dynamics.js

#### api documentation for  [dynamics.js (v1.1.5)](http://dynamicsjs.com)  [![npm package](https://img.shields.io/npm/v/npmdoc-dynamics.js.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-dynamics.js) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-dynamics.js.svg)](https://travis-ci.org/npmdoc/node-npmdoc-dynamics.js)

#### Javascript library to create physics-related animations

[![NPM](https://nodei.co/npm/dynamics.js.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/dynamics.js)

- [https://npmdoc.github.io/node-npmdoc-dynamics.js/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Michael Villar",
        "url": "http://twitter.com/michaelvillar"
    },
    "bugs": {
        "url": "https://github.com/michaelvillar/dynamics.js/issues"
    },
    "dependencies": {},
    "description": "Javascript library to create physics-related animations",
    "devDependencies": {
        "chai": "3.0.0",
        "coffee-script": "1.7.1",
        "jsdom": "3.x.x",
        "mocha": "2.2.5",
        "mocha-jsdom": "0.4.0",
        "uglify-js": "2.4.14"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "b90bdc33605cefe652b8416e701f79bf6eefce32",
        "tarball": "https://registry.npmjs.org/dynamics.js/-/dynamics.js-1.1.5.tgz"
    },
    "gitHead": "c82261d09309157f9567c4119cd3474e2af6148c",
    "homepage": "http://dynamicsjs.com",
    "keywords": [
        "animation",
        "javascript",
        "requestAnimationFrame",
        "spring",
        "physic"
    ],
    "license": "MIT",
    "main": "lib/dynamics.js",
    "maintainers": [
        {
            "name": "michaelvillar"
        }
    ],
    "name": "dynamics.js",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/michaelvillar/dynamics.js.git"
    },
    "scripts": {
        "build": "coffee -c -o ./lib/ ./src/dynamics.coffee && ./node_modules/uglify-js/bin/uglifyjs ./lib/dynamics.js -m -c -o ./lib/dynamics.min.js",
        "build:watch": "coffee -w -c -o ./lib/ ./src/dynamics.coffee",
        "prepublish": "npm run build",
        "test": "mocha --compilers coffee:coffee-script/register"
    },
    "title": "Dynamics.js",
    "version": "1.1.5"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
