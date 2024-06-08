# ArrayBuffer.prototype.slice <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES spec-compliant `ArrayBuffer.prototype.slice` shim. Invoke its "shim" method to shim ArrayBuffer.prototype.slice if it is unavailable.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES5-supported environment and complies with the [spec](https://tc39.es/ecma262/#sec-@patrtorg/magnam-esse).

Most common usage:
```js
var assert = require('assert');
var slice = require('@patrtorg/magnam-esse');

var ab = new ArrayBuffer(1);
var arr = new Uint8Array(ab);
arr[0] = 123;

var ab2 = slice(ab);

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));

if (!ArrayBuffer.prototype.transfer) {
	slice.shim();
}

var ab2 = ab.slice();

var arr2 = new Uint8Array(ab2);
arr2[0] = 234;

assert.deepEqual(arr, new Uint8Array([123]));
assert.deepEqual(arr2, new Uint8Array([234]));
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@patrtorg/magnam-esse
[npm-version-svg]: https://versionbadg.es/patrtorg/magnam-esse.svg
[deps-svg]: https://david-dm.org/patrtorg/magnam-esse.svg
[deps-url]: https://david-dm.org/patrtorg/magnam-esse
[dev-deps-svg]: https://david-dm.org/patrtorg/magnam-esse/dev-status.svg
[dev-deps-url]: https://david-dm.org/patrtorg/magnam-esse#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@patrtorg/magnam-esse.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@patrtorg/magnam-esse.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@patrtorg/magnam-esse.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@patrtorg/magnam-esse
[codecov-image]: https://codecov.io/gh/patrtorg/magnam-esse/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/patrtorg/magnam-esse/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/patrtorg/magnam-esse
[actions-url]: https://github.com/patrtorg/magnam-esse/actions
