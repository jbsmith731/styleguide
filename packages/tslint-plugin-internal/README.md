# @ueno/tslint-plugin-internal

[![npm](https://img.shields.io/npm/v/@ueno/tslint-plugin-internal.svg)](https://www.npmjs.com/package/@ueno/tslint-plugin-internal)

## Why?

We needed some customs rules to add to our lint config, to align with our code style. This package is used in the [@ueno/tslint-config](https://github.com/ueno-llc/styleguide/tree/master/packages/tslint-config) to add two custom rules to our config.

## Rules

* @ueno/internal/decorator-line-break: Force a line break after the decorator statement
* @ueno/internal/padded-blocks: Force a blank line after the class declaration

## @ueno/internal/decorator-line-break

This rule has one option, which can be a string option.

String option:

- `"always"` (default) requires a line break after a decorator statement
- `"never"` disallows line break after a decorator statement

Example:

**`'@ueno/internal/decorator-line-break': 2` Will requires to add a line break after a decorator declaration**

Wrong 👎

```js
@observable myValue = true;
```

Good 👍

```js
@observable
myValue = true;
```

## @ueno/internal/padded-blocks

This rule has two options, which can be a string option or an object option.

String option:

- `"always"` (default) requires empty lines at the beginning and ending of blocks, classes and switches statements
- `"never"` disallows empty lines at the beginning and ending of blocks, classes and switches statements
- `"top"` requires empty lines only at the beginning of blocks, classes and switches statements
- `"bottom"` disallows empty lines only at the ending of blocks, classes and switches statements

Object option:

- `"blocks"` require or disallow padding within blocks statements
- `"classes"` require or disallow padding within classes statements
- `"switches"` require or disallow padding within switch statements

Examples:

**`'@ueno/internal/padded-blocks': 2` Will requires empty lines only at the beginning and ending of blocks, classes and switches statements**

Wrong 👎

```js
class A {
  constructor() {
  }
}
```

Good 👍

```js
class A {

  constructor() {
  }

}
```

**`'@ueno/internal/padded-blocks': ['error', { classes: 'top' }]` Will requires empty lines only at the beginning of classes statements**

Wrong 👎

```js
class A {
  constructor() {
  }
}
```

Good 👍

```js
class A {

  constructor() {
  }
}
```

## License

MIT &copy; [ueno.](http://ueno.co)
