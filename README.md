# api documentation for  [dynamics.js (v1.1.5)](http://dynamicsjs.com)  [![npm package](https://img.shields.io/npm/v/npmdoc-dynamics.js.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-dynamics.js) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-dynamics.js.svg)](https://travis-ci.org/npmdoc/node-npmdoc-dynamics.js)
#### Javascript library to create physics-related animations

[![NPM](https://nodei.co/npm/dynamics.js.png?downloads=true)](https://www.npmjs.com/package/dynamics.js)

[![apidoc](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-dynamics.js_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-dynamics.js/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Michael Villar",
        "email": "me@michaelvillar.com",
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
            "name": "michaelvillar",
            "email": "me@michaelvillar.com"
        }
    ],
    "name": "dynamics.js",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module dynamics.js](#apidoc.module.dynamics.js)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>animate (el)](#apidoc.element.dynamics.js.animate)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>bezier (options)](#apidoc.element.dynamics.js.bezier)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>bounce (options)](#apidoc.element.dynamics.js.bounce)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>clearTimeout (id)](#apidoc.element.dynamics.js.clearTimeout)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>css (el)](#apidoc.element.dynamics.js.css)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>easeIn (options)](#apidoc.element.dynamics.js.easeIn)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>easeInOut (options)](#apidoc.element.dynamics.js.easeInOut)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>easeOut (options)](#apidoc.element.dynamics.js.easeOut)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>forceWithGravity (options)](#apidoc.element.dynamics.js.forceWithGravity)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>gravity (options)](#apidoc.element.dynamics.js.gravity)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>linear ()](#apidoc.element.dynamics.js.linear)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>setTimeout (fn, delay)](#apidoc.element.dynamics.js.setTimeout)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>spring (options)](#apidoc.element.dynamics.js.spring)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>stop (el)](#apidoc.element.dynamics.js.stop)
1.  [function <span class="apidocSignatureSpan">dynamics.js.</span>toggleSlow ()](#apidoc.element.dynamics.js.toggleSlow)



# <a name="apidoc.module.dynamics.js"></a>[module dynamics.js](#apidoc.module.dynamics.js)

#### <a name="apidoc.element.dynamics.js.animate"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>animate (el)](#apidoc.element.dynamics.js.animate)
- description and source-code
```javascript
animate = function (el) {
  var args, i, res;
  if (el instanceof Array || el instanceof NodeList || el instanceof HTMLCollection) {
    res = (function() {
      var _i, _ref, _results;
      _results = [];
      for (i = _i = 0, _ref = el.length; 0 <= _ref ? _i < _ref : _i > _ref; i = 0 <= _ref ? ++_i : --_i) {
        args = Array.prototype.slice.call(arguments, 1);
        args.splice(0, 0, el[i]);
        _results.push(fn.apply(this, args));
      }
      return _results;
    }).apply(this, arguments);
    return res;
  }
  return fn.apply(this, arguments);
}
```
- example usage
```shell
...
Include 'dynamics.js' into your page:
'''html
<script src="dynamics.js"></script>
'''
You can animate CSS properties of any DOM element.
'''javascript
var el = document.getElementById("logo")
dynamics.animate(el, {
translateX: 350,
scale: 2,
opacity: 0.5
}, {
type: dynamics.spring,
frequency: 200,
friction: 200,
...
```

#### <a name="apidoc.element.dynamics.js.bezier"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>bezier (options)](#apidoc.element.dynamics.js.bezier)
- description and source-code
```javascript
bezier = function (options) {
  var Bs, fn, points;
  if (options == null) {
    options = {};
  }
  points = options.points;
  Bs = (function() {
    var i, k, _fn;
    Bs = [];
    _fn = function(pointA, pointB) {
      var B2;
      B2 = function(t) {
        return Bezier(t, pointA, pointA.cp[pointA.cp.length - 1], pointB.cp[0], pointB);
      };
      return Bs.push(B2);
    };
    for (i in points) {
      k = parseInt(i);
      if (k >= points.length - 1) {
        break;
      }
      _fn(points[k], points[k + 1]);
    }
    return Bs;
  })();
  fn = function(t) {
    if (t === 0) {
      return 0;
    } else if (t === 1) {
      return 1;
    } else {
      return yForX(t, Bs, this.returnsToSelf);
    }
  };
  fn.returnsToSelf = points[points.length - 1].y === 0;
  return fn;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.bounce"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>bounce (options)](#apidoc.element.dynamics.js.bounce)
- description and source-code
```javascript
bounce = function (options) {
  var A, fn, frequency, friction;
  if (options == null) {
    options = {};
  }
  applyDefaults(options, dynamics.bounce.defaults);
  frequency = Math.max(1, options.frequency / 20);
  friction = Math.pow(20, options.friction / 100);
  A = function(t) {
    return Math.pow(friction / 10, -t) * (1 - t);
  };
  fn = function(t) {
    var At, a, angle, b;
    b = -3.14 / 2;
    a = 1;
    At = A(t);
    angle = frequency * t * a + b;
    return At * Math.cos(angle);
  };
  fn.returnsToSelf = true;
  return fn;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.clearTimeout"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>clearTimeout (id)](#apidoc.element.dynamics.js.clearTimeout)
- description and source-code
```javascript
clearTimeout = function (id) {
  return cancelTimeout(id);
}
```
- example usage
```shell
...
### dynamics.setTimeout(fn, delay)
Dynamics.js has its own 'setTimeout'. The reason is that 'requestAnimationFrame' and 'setTimeout' have different behaviors. In most
 browsers, 'requestAnimationFrame' will not run in a background tab while 'setTimeout' will. This can cause a lot of problems while
 using 'setTimeout' along your animations. I suggest you use Dynamics's 'setTimeout' and 'clearTimeout' to handle these scenarios
.
- 'fn' is the callback
- 'delay' is in milliseconds

Returns a unique id

### dynamics.clearTimeout(id)
Clears a timeout that was defined earlier
- 'id' is the timeout id

### dynamics.toggleSlow()
Toggle a debug mode to slow down every animations and timeouts.
This is useful for development mode to tweak your animation.
This can be activated using 'Shift-Control-D' in the browser.
...
```

#### <a name="apidoc.element.dynamics.js.css"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>css (el)](#apidoc.element.dynamics.js.css)
- description and source-code
```javascript
css = function (el) {
  var args, i, res;
  if (el instanceof Array || el instanceof NodeList || el instanceof HTMLCollection) {
    res = (function() {
      var _i, _ref, _results;
      _results = [];
      for (i = _i = 0, _ref = el.length; 0 <= _ref ? _i < _ref : _i > _ref; i = 0 <= _ref ? ++_i : --_i) {
        args = Array.prototype.slice.call(arguments, 1);
        args.splice(0, 0, el[i]);
        _results.push(fn.apply(this, args));
      }
      return _results;
    }).apply(this, arguments);
    return res;
  }
  return fn.apply(this, arguments);
}
```
- example usage
```shell
...
  - 'change' (optional) is called at every change. Two arguments are passed to the function. 'function(el, progress)'
    - 'el' is the element it's animating
    - 'progress' is the progress of the animation between 0 and 1

### dynamics.stop(el)
Stops the animation applied on the element

### dynamics.css(el, properties)
This is applying the CSS properties to your element with the correct browser prefixes.
- 'el' is a DOM element
- 'properties' is an object of the CSS properties

### dynamics.setTimeout(fn, delay)
Dynamics.js has its own 'setTimeout'. The reason is that 'requestAnimationFrame' and 'setTimeout' have different behaviors. In most
 browsers, 'requestAnimationFrame' will not run in a background tab while 'setTimeout' will. This can cause a lot of problems while
 using 'setTimeout' along your animations. I suggest you use Dynamics's 'setTimeout' and 'clearTimeout' to handle these scenarios
.
- 'fn' is the callback
...
```

#### <a name="apidoc.element.dynamics.js.easeIn"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>easeIn (options)](#apidoc.element.dynamics.js.easeIn)
- description and source-code
```javascript
easeIn = function (options) {
  var friction, _ref;
  if (options == null) {
    options = {};
  }
  friction = (_ref = options.friction) != null ? _ref : dynamics.easeIn.defaults.friction;
  return dynamics.bezier({
    points: [
      {
        x: 0,
        y: 0,
        cp: [
          {
            x: 0.92 - (friction / 1000),
            y: 0
          }
        ]
      }, {
        x: 1,
        y: 1,
        cp: [
          {
            x: 1,
            y: 1
          }
        ]
      }
    ]
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.easeInOut"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>easeInOut (options)](#apidoc.element.dynamics.js.easeInOut)
- description and source-code
```javascript
easeInOut = function (options) {
  var friction, _ref;
  if (options == null) {
    options = {};
  }
  friction = (_ref = options.friction) != null ? _ref : dynamics.easeInOut.defaults.friction;
  return dynamics.bezier({
    points: [
      {
        x: 0,
        y: 0,
        cp: [
          {
            x: 0.92 - (friction / 1000),
            y: 0
          }
        ]
      }, {
        x: 1,
        y: 1,
        cp: [
          {
            x: 0.08 + (friction / 1000),
            y: 1
          }
        ]
      }
    ]
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.easeOut"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>easeOut (options)](#apidoc.element.dynamics.js.easeOut)
- description and source-code
```javascript
easeOut = function (options) {
  var friction, _ref;
  if (options == null) {
    options = {};
  }
  friction = (_ref = options.friction) != null ? _ref : dynamics.easeOut.defaults.friction;
  return dynamics.bezier({
    points: [
      {
        x: 0,
        y: 0,
        cp: [
          {
            x: 0,
            y: 0
          }
        ]
      }, {
        x: 1,
        y: 1,
        cp: [
          {
            x: 0.08 + (friction / 1000),
            y: 1
          }
        ]
      }
    ]
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.forceWithGravity"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>forceWithGravity (options)](#apidoc.element.dynamics.js.forceWithGravity)
- description and source-code
```javascript
forceWithGravity = function (options) {
  if (options == null) {
    options = {};
  }
  applyDefaults(options, dynamics.forceWithGravity.defaults);
  options.returnsToSelf = true;
  return dynamics.gravity(options);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.gravity"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>gravity (options)](#apidoc.element.dynamics.js.gravity)
- description and source-code
```javascript
gravity = function (options) {
  var L, bounciness, curves, elasticity, fn, getPointInCurve, gravity;
  if (options == null) {
    options = {};
  }
  applyDefaults(options, dynamics.gravity.defaults);
  bounciness = Math.min(options.bounciness / 1250, 0.8);
  elasticity = options.elasticity / 1000;
  gravity = 100;
  curves = [];
  L = (function() {
    var b, curve;
    b = Math.sqrt(2 / gravity);
    curve = {
      a: -b,
      b: b,
      H: 1
    };
    if (options.returnsToSelf) {
      curve.a = 0;
      curve.b = curve.b * 2;
    }
    while (curve.H > 0.001) {
      L = curve.b - curve.a;
      curve = {
        a: curve.b,
        b: curve.b + L * bounciness,
        H: curve.H * bounciness * bounciness
      };
    }
    return curve.b;
  })();
  getPointInCurve = function(a, b, H, t) {
    var c, t2;
    L = b - a;
    t2 = (2 / L) * t - 1 - (a * 2 / L);
    c = t2 * t2 * H - H + 1;
    if (options.returnsToSelf) {
      c = 1 - c;
    }
    return c;
  };
  (function() {
    var L2, b, curve, _results;
    b = Math.sqrt(2 / (gravity * L * L));
    curve = {
      a: -b,
      b: b,
      H: 1
    };
    if (options.returnsToSelf) {
      curve.a = 0;
      curve.b = curve.b * 2;
    }
    curves.push(curve);
    L2 = L;
    _results = [];
    while (curve.b < 1 && curve.H > 0.001) {
      L2 = curve.b - curve.a;
      curve = {
        a: curve.b,
        b: curve.b + L2 * bounciness,
        H: curve.H * elasticity
      };
      _results.push(curves.push(curve));
    }
    return _results;
  })();
  fn = function(t) {
    var curve, i, v;
    i = 0;
    curve = curves[i];
    while (!(t >= curve.a && t <= curve.b)) {
      i += 1;
      curve = curves[i];
      if (!curve) {
        break;
      }
    }
    if (!curve) {
      v = options.returnsToSelf ? 0 : 1;
    } else {
      v = getPointInCurve(curve.a, curve.b, curve.H, t);
    }
    return v;
  };
  fn.returnsToSelf = options.returnsToSelf;
  return fn;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.linear"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>linear ()](#apidoc.element.dynamics.js.linear)
- description and source-code
```javascript
linear = function () {
  return function(t) {
    return t;
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.setTimeout"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>setTimeout (fn, delay)](#apidoc.element.dynamics.js.setTimeout)
- description and source-code
```javascript
setTimeout = function (fn, delay) {
  return addTimeout(fn, delay * slowRatio);
}
```
- example usage
```shell
...
Stops the animation applied on the element

### dynamics.css(el, properties)
This is applying the CSS properties to your element with the correct browser prefixes.
- 'el' is a DOM element
- 'properties' is an object of the CSS properties

### dynamics.setTimeout(fn, delay)
Dynamics.js has its own 'setTimeout'. The reason is that 'requestAnimationFrame' and 'setTimeout' have different behaviors. In most
 browsers, 'requestAnimationFrame' will not run in a background tab while 'setTimeout' will. This can cause a lot of problems while
 using 'setTimeout' along your animations. I suggest you use Dynamics's 'setTimeout' and 'clearTimeout' to handle these scenarios
.
- 'fn' is the callback
- 'delay' is in milliseconds

Returns a unique id

### dynamics.clearTimeout(id)
...
```

#### <a name="apidoc.element.dynamics.js.spring"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>spring (options)](#apidoc.element.dynamics.js.spring)
- description and source-code
```javascript
spring = function (options) {
  var A1, A2, decal, frequency, friction, s;
  if (options == null) {
    options = {};
  }
  applyDefaults(options, dynamics.spring.defaults);
  frequency = Math.max(1, options.frequency / 20);
  friction = Math.pow(20, options.friction / 100);
  s = options.anticipationSize / 1000;
  decal = Math.max(0, s);
  A1 = function(t) {
    var M, a, b, x0, x1;
    M = 0.8;
    x0 = s / (1 - s);
    x1 = 0;
    b = (x0 - (M * x1)) / (x0 - x1);
    a = (M - b) / x0;
    return (a * t * options.anticipationStrength / 100) + b;
  };
  A2 = function(t) {
    return Math.pow(friction / 10, -t) * (1 - t);
  };
  return function(t) {
    var A, At, a, angle, b, frictionT, y0, yS;
    frictionT = (t / (1 - s)) - (s / (1 - s));
    if (t < s) {
      yS = (s / (1 - s)) - (s / (1 - s));
      y0 = (0 / (1 - s)) - (s / (1 - s));
      b = Math.acos(1 / A1(yS));
      a = (Math.acos(1 / A1(y0)) - b) / (frequency * (-s));
      A = A1;
    } else {
      A = A2;
      b = 0;
      a = 1;
    }
    At = A(frictionT);
    angle = frequency * (t - s) * a + b;
    return 1 - (At * Math.cos(angle));
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.dynamics.js.stop"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>stop (el)](#apidoc.element.dynamics.js.stop)
- description and source-code
```javascript
stop = function (el) {
  var args, i, res;
  if (el instanceof Array || el instanceof NodeList || el instanceof HTMLCollection) {
    res = (function() {
      var _i, _ref, _results;
      _results = [];
      for (i = _i = 0, _ref = el.length; 0 <= _ref ? _i < _ref : _i > _ref; i = 0 <= _ref ? ++_i : --_i) {
        args = Array.prototype.slice.call(arguments, 1);
        args.splice(0, 0, el[i]);
        _results.push(fn.apply(this, args));
      }
      return _results;
    }).apply(this, arguments);
    return res;
  }
  return fn.apply(this, arguments);
}
```
- example usage
```shell
...
  - 'duration' is in milliseconds (default: '1000')
  - 'delay' is in milliseconds (default: '0')
  - 'complete' (optional) is the completion callback
  - 'change' (optional) is called at every change. Two arguments are passed to the function. 'function(el, progress)'
    - 'el' is the element it's animating
    - 'progress' is the progress of the animation between 0 and 1

### dynamics.stop(el)
Stops the animation applied on the element

### dynamics.css(el, properties)
This is applying the CSS properties to your element with the correct browser prefixes.
- 'el' is a DOM element
- 'properties' is an object of the CSS properties
...
```

#### <a name="apidoc.element.dynamics.js.toggleSlow"></a>[function <span class="apidocSignatureSpan">dynamics.js.</span>toggleSlow ()](#apidoc.element.dynamics.js.toggleSlow)
- description and source-code
```javascript
toggleSlow = function () {
  slow = !slow;
  if (slow) {
    slowRatio = 3;
  } else {
    slowRatio = 1;
  }
  return typeof console !== "undefined" && console !== null ? typeof console.log === "function" ? console.log("dynamics.js: slow
 animations " + (slow ? "enabled" : "disabled")) : void 0 : void 0;
}
```
- example usage
```shell
...

Returns a unique id

### dynamics.clearTimeout(id)
Clears a timeout that was defined earlier
- 'id' is the timeout id

### dynamics.toggleSlow()
Toggle a debug mode to slow down every animations and timeouts.
This is useful for development mode to tweak your animation.
This can be activated using 'Shift-Control-D' in the browser.

## Dynamics and properties
### dynamics.spring
- 'frequency' default is 300
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
