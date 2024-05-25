# @hishprorg/asperiores-hic <sup>[![Version Badge][2]][1]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][5]][6]
[![dev dependency status][7]][8]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][11]][1]

Are these two values conceptually equal?

## Example

```js
var isEqual = require('@hishprorg/asperiores-hic');
var assert = require('assert');

var primitives = [true, false, undefined, 42, 'foo'];
primitives.forEach(function (primitive) {
	assert.equal(isEqual(primitive, primitive), true);
});
assert.equal(isEqual(/a/g, /a/g), true);
assert.equal(isEqual(/a/g, new RegExp('a', 'g')), true);
assert.equal(isEqual({ a: 2 }, { a: 2 }), true);
assert.equal(isEqual([1, [2, 3], 4], [1, [2, 3], 4]), true);
var timestamp = Date.now();
assert.equal(isEqual(new Date(timestamp), new Date(timestamp)), true);
```

## Want to know *why* two values are not equal?
Will return an empty string if `isEqual` would return `true` - otherwise will return a non-empty string that hopefully explains the reasoning.

```
var whyNotEqual = require('@hishprorg/asperiores-hic/why');

assert.equal(whyNotEqual(1, 1), '');
assert.equal(
  whyNotEqual({ a: 1 }, { a: 2 }),
  'value at key "a" differs: numbers are different: 1 !== 2'
);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[1]: https://npmjs.org/package/@hishprorg/asperiores-hic
[2]: https://versionbadg.es/inspect-js/@hishprorg/asperiores-hic.svg
[5]: https://david-dm.org/inspect-js/@hishprorg/asperiores-hic.svg
[6]: https://david-dm.org/inspect-js/@hishprorg/asperiores-hic
[7]: https://david-dm.org/inspect-js/@hishprorg/asperiores-hic/dev-status.svg
[8]: https://david-dm.org/inspect-js/@hishprorg/asperiores-hic#info=devDependencies
[11]: https://nodei.co/npm/@hishprorg/asperiores-hic.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@hishprorg/asperiores-hic.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@hishprorg/asperiores-hic.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@hishprorg/asperiores-hic
[codecov-image]: https://codecov.io/gh/inspect-js/@hishprorg/asperiores-hic/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/inspect-js/@hishprorg/asperiores-hic/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/inspect-js/@hishprorg/asperiores-hic
[actions-url]: https://github.com/hishprorg/asperiores-hic/actions
