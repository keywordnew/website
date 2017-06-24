---
title: array-element-newline - Rules
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->

# enforce line breaks between array elements (array-element-newline)

(fixable) The `--fix` option on the [command line](../user-guide/command-line-interface#fix) can automatically fix some of the problems reported by this rule.

A number of style guides require or disallow line breaks between array elements.

## Rule Details

This rule enforces line breaks between array elements.

## Options

This rule has either a string option:

* `"always"` (default) requires line breaks between array elements
* `"never"` disallows line breaks between array elements

Or an object option (Requires line breaks if any of properties is satisfied. Otherwise, disallows line breaks):

* `"multiline": <boolean>` requires line breaks if there are line breaks inside elements. If this is false, this condition is disabled.
* `"minItems": <number>` requires line breaks if the number of elements is at least the given integer. If this is 0, this condition will act the same as the option `"always"`. If this is `null` (the default), this condition is disabled.

### always

Examples of **incorrect** code for this rule with the default `"always"` option:

```js
/*eslint array-element-newline: ["error", "always"]*/

var c = [1, 2];
var d = [1, 2, 3];
var e = [
    function foo() {
        dosomething();
    }, function bar() {
        dosomething();
    }
];
```

Examples of **correct** code for this rule with the default `"always"` option:

```js
/*eslint array-element-newline: ["error", "always"]*/

var a = [];
var b = [1];
var c = [1,
    2];
var d = [1,
    2,
    3];
var e = [
    function foo() {
        dosomething();
    },
    function bar() {
        dosomething();
    }
];
```

### never

Examples of **incorrect** code for this rule with the default `"never"` option:

```js
/*eslint array-element-newline: ["error", "never"]*/

var c = [
    1,
    2
];
var d = [
    1,
    2,
    3
];
var e = [
    function foo() {
        dosomething();
    },
    function bar() {
        dosomething();
    }
];
```

Examples of **correct** code for this rule with the `"never"` option:

```js
/*eslint array-element-newline: ["error", "never"]*/

var a = [];
var b = [1];
var c = [1, 2];
var d = [1, 2, 3];
var e = [
    function foo() {
        dosomething();
    }, function bar() {
        dosomething();
    }
];
```

### multiline

Examples of **incorrect** code for this rule with the `{ "multiline": true }` option:

```js
/*eslint array-element-newline: ["error", { "multiline": true }]*/

var d = [1,
    2, 3];
var e = [
    function foo() {
        dosomething();
    }, function bar() {
        dosomething();
    }
];
```

Examples of **correct** code for this rule with the `{ "multiline": true }` option:

```js
/*eslint array-element-newline: ["error", { "multiline": true }]*/

var a = [];
var b = [1];
var c = [1, 2];
var d = [1, 2, 3];
var e = [
    function foo() {
        dosomething();
    },
    function bar() {
        dosomething();
    }
];
```

### minItems

Examples of **incorrect** code for this rule with the `{ "minItems": 3 }` option:

```js
/*eslint array-element-newline: ["error", { "minItems": 3 }]*/

var c = [1,
    2];
var d = [1, 2, 3];
var e = [
    function foo() {
        dosomething();
    },
    function bar() {
        dosomething();
    }
];
```

Examples of **correct** code for this rule with the `{ "minItems": 3 }` option:

```js
/*eslint array-element-newline: ["error", { "minItems": 3 }]*/

var a = [];
var b = [1];
var c = [1, 2];
var d = [1,
    2,
    3];
var e = [
    function foo() {
        dosomething();
    }, function bar() {
        dosomething();
    }
];
```

### multiline and minItems

Examples of **incorrect** code for this rule with the `{ "multiline": true, "minItems": 3 }` options:

```js
/*eslint array-element-newline: ["error", { "multiline": true, "minItems": 3 }]*/

var c = [1,
2];
var d = [1, 2, 3];
var e = [
    function foo() {
        dosomething();
    }, function bar() {
        dosomething();
    }
];
```

Examples of **correct** code for this rule with the `{ "multiline": true, "minItems": 3 }` options:

```js
/*eslint array-element-newline: ["error", { "multiline": true, "minItems": 3 }]*/

var a = [];
var b = [1];
var c = [1, 2];
var d = [1,
    2,
    3];
var e = [
    function foo() {
        dosomething();
    },
    function bar() {
        dosomething();
    }
];
```


## When Not To Use It

If you don't want to enforce linebreaks between array elements, don't enable this rule.

## Compatibility

* **JSCS:** [validateNewlineAfterArrayElements](http://jscs.info/rule/validateNewlineAfterArrayElements)

## Related Rules

* [array-bracket-spacing](array-bracket-spacing)
* [array-bracket-newline](array-bracket-newline)
* [object-property-newline](object-property-newline)
* [object-curly-spacing](object-curly-spacing)
* [object-curly-newline](object-curly-newline)
* [max-statements-per-line](max-statements-per-line)
* [block-spacing](block-spacing)
* [brace-style](brace-style)

## Version

This rule was introduced in ESLint 4.0.0-rc.0.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/array-element-newline.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/array-element-newline.md)