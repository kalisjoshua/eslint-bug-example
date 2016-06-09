# Example of Potential ESLint Bug

Using the [Airbnb](https://www.npmjs.com/package/eslint-config-airbnb) ESLint
config and adding the option to relax the `whitespace-after-return`, the
`padded-blocks` errror still reports.

The code being lint-ed:

```js
(function test() {

  return true;
}());
```

The eslint config:

```json
{
  "extends": "airbnb",
  "rules": {
    "newline-before-return": 0
  }
}
```

The output:

```bash
$ npm test

> eslint-bug-example@1.0.0 test ~/eslint-bug-example
> eslint index.js


~/eslint-bug-example/index.js
  1:18  error  Block must not be padded by blank lines  padded-blocks

  ✖ 1 problem (1 error, 0 warnings)

  npm ERR! Test failed.  See above for more details.
```
