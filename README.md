# aran-live

This npm module is a simplified API for [aran](http://npmjs.com/aran) which forces live instrumentation and uses the keys of the advice as pointcut.
It also uses [acorn](http://npmjs.com/acorn) for parsign and [astring](http://npmjs.com/astring) for generation.

```
instrument = require("aran-live")(aran, advice);
```

Creates an instrumentation function from an Aran instance and an advice.
* `aran :: Aran.aran`: An Aran instance.
* `advice ::  object`: The object containing the traps and an optional sandbox.
* `script2 = instrument(script1, scope, options)`: Insert traps to a script.
  * `script1 :: string`: Original script.
  * `scope :: array`: Passed to `aran.weave(estree, scope)`.
  * `options :: object`: Passed to `Acorn.parse(script, options)`.
  * `script2 :: string`: Instrumented script.
