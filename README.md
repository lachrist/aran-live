# aran-live
Simpler live API for http://npmjs.com/aran

## Simplified Live API

This simpler interface is provided by [live.js](live.js) which is a simple wrapper around the regular Aran interface.
It forces live instrumentation and use the keys of the advice as pointcut.

### `aranlive = require("aran/live")(advice, options)`

Create a new AranLive instance.
* `advice ::  object`: the object containing the traps.
  If `options.sandbox` is truthy, `advice.SANDBOX` will be used as the top frame of every environment.
* `options :: object | falsy`: regular aran's options; see `require("aran")(options)`

### `output = aranlive.instrument(script, scope, options)`

Desugar and insert calls to traps present in the advice.
* `script :: string`: the target code to instrument.
* `scope :: array | string | falsy | object | string`: cf the `scope` parameter of `aran.weave(script, pointcut, scope)`.
* `options :: object | falsy`: acorn's parsing options.
* `output :: string`: the instrumented code (contains trap calls).

### `node = aranlive.node(serial)`

Retrieve a node from its serial number; same as `aran.node(serial)`.
* `serial :: number`
* `node :: object | undefined`

### `root = aranlive.root(serial)`

Retrieve the ESTree Program node that contains the node at the given serial number; same as `aran.root(serial)`.
* `serial :: number`
* `root :: object | undefined`

### `namespace = aranlive.namespace`

The name of the global variable holding the advice; same as `aran.namespace`
* `namespace :: string`
