---
title: Rule arrow-body-style
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->

# Require braces in arrow function body (arrow-body-style)

Arrow functions can omit braces when there is a single statement in the body. This rule enforces the consistent use of braces in arrow functions.

## Rule Details

This rule can enforce the use of braces around arrow function body.

## Options

The rule takes one option, a string, which can be:

* `"always"` enforces braces around the function body
* `"as-needed"` enforces no braces where they can be omitted (default)

### "always"

```json
"arrow-body-style": ["error", "always"]
```

When the rule is set to `"always"` the following patterns are considered problems:

```js
/*eslint arrow-body-style: ["error", "always"]*/
/*eslint-env es6*/
let foo = () => 0;
```

The following patterns are not considered problems:

```js
let foo = () => {
    return 0;
};
let foo = (retv, name) => {
    retv[name] = true;
    return retv;
};
```

### "as-needed"

When the rule is set to `"as-needed"` the following patterns are considered problems:

```js
/*eslint arrow-body-style: ["error", "as-needed"]*/
/*eslint-env es6*/

let foo = () => {
    return 0;
};
```

The following patterns are not considered problems:

```js
/*eslint arrow-body-style: ["error", "as-needed"]*/
/*eslint-env es6*/

let foo = () => 0;
let foo = (retv, name) => {
    retv[name] = true;
    return retv;
};
let foo = () => { bar(); };
let foo = () => {};
let foo = () => { /* do nothing */ };
let foo = () => {
    // do nothing.
};
```

## Version

This rule was introduced in ESLint 1.8.0.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/arrow-body-style.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/arrow-body-style.md)
