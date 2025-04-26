<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# unaryInputCastingDataType

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Resolve the input ndarray casting [data type][@stdlib/ndarray/dtypes] for a unary function.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
unaryInputCastingDataType = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-unary-input-casting-dtype@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var unaryInputCastingDataType = require( 'path/to/vendor/umd/ndarray-base-unary-input-casting-dtype/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-unary-input-casting-dtype@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.unaryInputCastingDataType;
})();
</script>
```

#### unaryInputCastingDataType( idtype, odtype, policy )

Resolves the input ndarray casting [data type][@stdlib/ndarray/dtypes] for a unary function according to a [data type policy][@stdlib/ndarray/input-casting-policies].

```javascript
var dt = unaryInputCastingDataType( 'int32', 'float64', 'promoted' );
// returns 'float64'
```

The function supports the following parameters:

-   **idtype**: input ndarray data type.
-   **odtype**: output ndarray data type.
-   **policy**: input ndarray [casting policy][@stdlib/ndarray/input-casting-policies].

If `policy` is a [data type][@stdlib/ndarray/dtypes], the function always returns the `policy` value (i.e., the third argument).

```javascript
var dt = unaryInputCastingDataType( 'float32', 'float64', 'complex128' );
// returns 'complex128'

dt = unaryInputCastingDataType( 'int32', 'float64', 'complex128' );
// returns 'complex128'

// ...
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-nary-function@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/utils-unzip@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-n-cartesian-product@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-dtypes@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each-map@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-unary-input-casting-dtype@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Get the list of real-valued data types:
var dt = dtypes( 'real' );

// Define a list of casting policies:
var policies = [
    'none',
    'promoted',
    'accumulation',
    'output'
];

// Generate dtype-policy argument groups:
var args = nCartesianProduct( dt, dt, policies );

// Unzip the argument arrays:
args = unzip( args );

// Resolve casting data types:
logEachMap( 'dtypes: (%10s, %10s). policy: %20s. result: %10s.', args[ 0 ], args[ 1 ], args[ 2 ], naryFunction( inputCastingDataType, 3 ) );

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-unary-input-casting-dtype.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-unary-input-casting-dtype

[test-image]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-unary-input-casting-dtype/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-unary-input-casting-dtype?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-unary-input-casting-dtype.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-unary-input-casting-dtype/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-base-unary-input-casting-dtype/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-unary-input-casting-dtype/main/LICENSE

[@stdlib/ndarray/dtypes]: https://github.com/stdlib-js/ndarray-dtypes/tree/umd

[@stdlib/ndarray/input-casting-policies]: https://github.com/stdlib-js/ndarray-input-casting-policies/tree/umd

</section>

<!-- /.links -->
