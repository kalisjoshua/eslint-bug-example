# Example of Potential ESLint Options Bug

The "new" option `newline-before-return` is not preventing errors from being
reported for `padded-blocks`.

The code being lint-ed:

```js
(function test() {

  return true;
}());
```

The eslint config:

```json
{
  "rules": {
    "newline-before-return": "off",
    "padded-blocks": "error"
  }
}
```

The output:

```bash
$ npm test

> eslint-bug-example@1.0.0 test ~/eslint-bug-example
> eslint index.js


~/eslint-bug-example/index.js
  4:1  error  Block must not be padded by blank lines  padded-blocks

  ✖ 1 problem (1 error, 0 warnings)

  npm ERR! Test failed.  See above for more details.
```
