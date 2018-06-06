# aran-live

This npm module is a simplified API for http://npmjs.com/aran which forces live instrumentation and use the keys of the advice as pointcut.
It also uses [acorn](http://npmjs.com/acorn) for parsign and [astring](http://npmjs.com/astring) for generation.

```
instrument = require("aran-live")(aran, advice);
```

Creates an instrumentation function.
* `aran :: Aran.aran`: an Aran instance.
* `advice ::  object`: the object containing the traps and an optional sandbox.
* `script2 = instrument(script1, scope, options)`: insert traps to a script.
  * `script1 :: string`: original script.
  * `scope :: array` passed to `aran.weave(estree, scope)`.
  * `options :: object` passed to `Acorn.parse(script, options)`.
  * `script2 :: string`: instrumented script.
