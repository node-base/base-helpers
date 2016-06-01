# base-helpers [![NPM version](https://img.shields.io/npm/v/base-helpers.svg?style=flat)](https://www.npmjs.com/package/base-helpers) [![NPM downloads](https://img.shields.io/npm/dm/base-helpers.svg?style=flat)](https://npmjs.org/package/base-helpers) [![Build Status](https://img.shields.io/travis/node-base/base-helpers.svg?style=flat)](https://travis-ci.org/node-base/base-helpers)

Adds support for managing template helpers to your base application.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install base-helpers --save
```

## Usage

Register the plugin with your [base](https://github.com/node-base/base) application:

```js
var Base = require('base');
var helpers = require('base-helpers');
base.use(helpers());
```

## API

### [.helper](index.js#L46)

Register a template helper.

**Params**

* `name` **{String}**: Helper name
* `fn` **{Function}**: Helper function.

**Example**

```js
app.helper('upper', function(str) {
  return str.toUpperCase();
});
```

### [.helpers](index.js#L67)

Register multiple template helpers.

**Params**

* `helpers` **{Object|Array}**: Object, array of objects, or glob patterns.

**Example**

```js
app.helpers({
  foo: function() {},
  bar: function() {},
  baz: function() {}
});
```

### [.asyncHelper](index.js#L86)

Register an async helper.

**Params**

* `name` **{String}**: Helper name.
* `fn` **{Function}**: Helper function

**Example**

```js
app.asyncHelper('upper', function(str, next) {
  next(null, str.toUpperCase());
});
```

### [.asyncHelpers](index.js#L107)

Register multiple async template helpers.

**Params**

* `helpers` **{Object|Array}**: Object, array of objects, or glob patterns.

**Example**

```js
app.asyncHelpers({
  foo: function() {},
  bar: function() {},
  baz: function() {}
});
```

### [.getHelper](index.js#L124)

Get a previously registered helper.

**Params**

* `name` **{String}**: Helper name
* `returns` **{Function}**: Returns the registered helper function.

**Example**

```js
var fn = app.getHelper('foo');
```

### [.getAsyncHelper](index.js#L141)

Get a previously registered async helper.

**Params**

* `name` **{String}**: Helper name
* `returns` **{Function}**: Returns the registered helper function.

**Example**

```js
var fn = app.getAsyncHelper('foo');
```

### [.hasHelper](index.js#L160)

Return true if sync helper `name` is registered.

**Params**

* `name` **{String}**: sync helper name
* `returns` **{Boolean}**: Returns true if the sync helper is registered

**Example**

```js
if (app.hasHelper('foo')) {
  // do stuff
}
```

### [.hasAsyncHelper](index.js#L178)

Return true if async helper `name` is registered.

**Params**

* `name` **{String}**: Async helper name
* `returns` **{Boolean}**: Returns true if the async helper is registered

**Example**

```js
if (app.hasAsyncHelper('foo')) {
  // do stuff
}
```

### [.helperGroup](index.js#L201)

Register a namespaced helper group.

**Params**

* `helpers` **{Object|Array}**: Object, array of objects, or glob patterns.

**Example**

```js
// markdown-utils
app.helperGroup('mdu', {
  foo: function() {},
  bar: function() {},
});

// Usage:
// <%= mdu.foo() %>
// <%= mdu.bar() %>
```

## Related projects

You might also be interested in these projects:

* [base-engines](https://www.npmjs.com/package/base-engines): Adds support for managing template engines to your base application. | [homepage](https://github.com/node-base/base-engines)
* [base-option](https://www.npmjs.com/package/base-option): Adds a few options methods to base, like `option`, `enable` and `disable`. See the readme… [more](https://www.npmjs.com/package/base-option) | [homepage](https://github.com/node-base/base-option)
* [base-task](https://www.npmjs.com/package/base-task): base plugin that provides a very thin wrapper around [https://github.com/doowb/composer](https://github.com/doowb/composer) for adding task methods to… [more](https://www.npmjs.com/package/base-task) | [homepage](https://github.com/node-base/base-task)
* [base](https://www.npmjs.com/package/base): base is the foundation for creating modular, unit testable and highly pluggable node.js applications, starting… [more](https://www.npmjs.com/package/base) | [homepage](https://github.com/node-base/base)

## Contributing

This document was generated by [verb](https://github.com/verbose/verb), please don't edit directly. Any changes to the readme must be made in [.verb.md](.verb.md). See [Building Docs](#building-docs).

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/node-base/base-helpers/issues/new).

## Building docs

Generate readme and API documentation with [verb](https://github.com/verbose/verb):

```sh
$ npm install -g verb verb-readme-generator && verb
```

## Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

## Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](https://github.com/node-base/base-helpers/blob/master/LICENSE).

***

_This file was generated by [verb](https://github.com/verbose/verb), v0.9.0, on June 01, 2016._