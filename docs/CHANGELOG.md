# Changelog
All notable changes will be recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased] yyyy-mm-dd

- docs: Add example for loading ESM from CommonJS (#1236)

## v3.0.0-beta.10

- **Breaking:** minimum supported Node.js version is now 12.20.
- **Breaking:** node-fetch is now a pure ESM module.
- Other: update readme to inform users about ESM.
- Other: update dependencies.

## v3.0.0-beta.9

**This is an important security release. It is strongly recommended to update as soon as possible.**

- Fix: honor the `size` option after following a redirect.

## v3.0.0-beta.8

- Enhance: remove string-to-arraybuffer (#882).
- Enhance: remove parted dependency (#883).
- Fix: export package.json (#908).
- Fix: minimum Node.js version (#874).
- Other: fix typo.

## v3.0.0-beta.7

- **Breaking:** minimum supported Node.js version is now 10.17.
- Enhance: update `fetch-blob`.
- Enhance: add insecureHTTPParser Parameter (#856).
- Enhance: drop custom Promises and refactor to `async` functions (#845).
- Enhance: polyfill `http.validateHeaderName` and `http.validateHeaderValue` (#843).
- Enhance: should check body _source_ on redirect (#866).
- Enhance: remove code duplication in custom errors (#842).
- Enhance: implement form-data encoding (#603).
- Fix: improve TypeScript types (#841).
- Fix: data URI handling and drop all URL analysis RegExps (#853).
- Fix: headers import statement (#859).
- Fix: correct Node versions were not installed on test matrix (#846).
- Other: test CommonJS build artifact (#838).
- Other: create Code of Conduct (#849).
- Other: readme update.

## v3.0.0-beta.6-exportfix

- Fix: `fetch` function export & declaration, which broke the previous release.

## v3.0.0-beta.6

- **Breaking:** minimum supported Node.js version is now 10.16.
- **Breaking:** removed `timeout` option.
- **Breaking:** revamp TypeScript declarations.
- Enhance: improve coverage.
- Enhance: drop Babel (while keeping ESM) (#805).
- Enhance: normalize export (#827).
- Enhance: remove guard for Stream.Readable.destroy (#824).
- Enhance: remove custom isArrayBuffer (#822).
- Enhance: use normal class inheritance instead of Body.mixIn (#828).
- Enhance: follow xo linter rules more strictly (#829).
- Enhance: revamp Headers module (#834).
- Fix: export the `AbortError` class.
- Fix: example using `file-type` (#804).
- Fix: settle `consumeBody` promise when the response closes prematurely (#768).
- Fix: disambiguate timeout behavior for response headers and body (#770).
- Fix: make sure the default `highWaterMark` equals 16384.
- Fix: default user agent (#818).
- Other: readme update.
- Other: update copyright information.

## v3.0.0-beta.5

> NOTE: Since the previous beta version included serious issues, such as [#749](https://github.com/node-fetch/node-fetch/issues/749), they will now be deprecated.

- Enhance: use built-in AbortSignal for typings.
- Enhance: compile CJS modules as a seperate set of files.
- Enhance: add more complete stream download example.
- Fix: question mark stripped from url when no params are given.
- Fix: path to tests file in error handling doc.
- Fix: import URL and URLSearchParams in typings.
- Fix: Ensure search parameters are included in URL path (#759).

## v3.0.0-beta.2

- Fix: exporting `main` and `types` at the correct path, oops.

## v3.0.0-beta.1

- **Breaking:** minimum supported Node.js version is now 10.
- Enhance: added new node-fetch-only option: `highWaterMark`.
- Enhance: `AbortError` now uses a w3c defined message.
- Enhance: data URI support.
- Enhance: drop existing blob implementation code and use fetch-blob as dependency instead.
- Enhance: modernise the code behind `FetchError` and `AbortError`.
- Enhance: replace deprecated `url.parse()` and `url.replace()` with the new WHATWG's `new URL()`
- Enhance: allow excluding a `user-agent` in a fetch request by setting it's header to null.
- Fix: `Response.statusText` no longer sets a default message derived from the HTTP status code.
- Fix: missing response stream error events.
- Fix: do not use constructor.name to check object.
- Fix: convert `Content-Encoding` to lowercase.
- Fix: propagate size and timeout to cloned response.
- Other: bundle TypeScript types.
- Other: replace Rollup with @pika/pack.
- Other: introduce linting to the project.
- Other: simplify Travis CI build matrix.
- Other: dev dependency update.
- Other: readme update.


# 2.x release

## v2.6.1

**This is an important security release. It is strongly recommended to update as soon as possible.**

- Fix: honor the `size` option after following a redirect.

## v2.6.0

- Enhance: `options.agent`, it now accepts a function that returns custom http(s).Agent instance based on current URL, see readme for more information.
- Fix: incorrect `Content-Length` was returned for stream body in 2.5.0 release; note that `node-fetch` doesn't calculate content length for stream body.
- Fix: `Response.url` should return empty string instead of `null` by default.

## v2.5.0

- Enhance: `Response` object now includes `redirected` property.
- Enhance: `fetch()` now accepts third-party `Blob` implementation as body.
- Other: disable `package-lock.json` generation as we never commit them.
- Other: dev dependency update.
- Other: readme update.

## v2.4.1

- Fix: `Blob` import rule for node < 10, as `Readable` isn't a named export.

## v2.4.0

- Enhance: added `Brotli` compression support (using node's zlib).
- Enhance: updated `Blob` implementation per spec.
- Fix: set content type automatically for `URLSearchParams`.
- Fix: `Headers` now reject empty header names.
- Fix: test cases, as node 12+ no longer accepts invalid header response.

## v2.3.0

- Enhance: added `AbortSignal` support, with README example.
- Enhance: handle invalid `Location` header during redirect by rejecting them explicitly with `FetchError`.
- Fix: update `browser.js` to support react-native environment, where `self` isn't available globally.

## v2.2.1

- Fix: `compress` flag shouldn't overwrite existing `Accept-Encoding` header.
- Fix: multiple `import` rules, where `PassThrough` etc. doesn't have a named export when using node <10 and `--experimental-modules` flag.
- Other: Better README.

## v2.2.0

- Enhance: Support all `ArrayBuffer` view types
- Enhance: Support Web Workers
- Enhance: Support Node.js' `--experimental-modules` mode; deprecate `.es.js` file
- Fix: Add `__esModule` property to the exports object
- Other: Better example in README for writing response to a file
- Other: More tests for Agent

## v2.1.2

- Fix: allow `Body` methods to work on `ArrayBuffer`-backed `Body` objects
- Fix: reject promise returned by `Body` methods when the accumulated `Buffer` exceeds the maximum size
- Fix: support custom `Host` headers with any casing
- Fix: support importing `fetch()` from TypeScript in `browser.js`
- Fix: handle the redirect response body properly

## v2.1.1

Fix packaging errors in v2.1.0.

## v2.1.0

- Enhance: allow using ArrayBuffer as the `body` of a `fetch()` or `Request`
- Fix: store HTTP headers of a `Headers` object internally with the given case, for compatibility with older servers that incorrectly treated header names in a case-sensitive manner
- Fix: silently ignore invalid HTTP headers
- Fix: handle HTTP redirect responses without a `Location` header just like non-redirect responses
- Fix: include bodies when following a redirection when appropriate

## v2.0.0

This is a major release. Check [our upgrade guide](https://github.com/node-fetch/node-fetch/blob/master/docs/v2-UPGRADE-GUIDE.md) for an overview on some key differences between v1 and v2.

### General changes

- Major: Node.js 0.10.x and 0.12.x support is dropped
- Major: `require('node-fetch/lib/response')` etc. is now unsupported; use `require('node-fetch').Response` or ES6 module imports
- Enhance: start testing on Node.js v4.x, v6.x, v8.x LTS, as well as v9.x stable
- Enhance: use Rollup to produce a distributed bundle (less memory overhead and faster startup)
- Enhance: make `Object.prototype.toString()` on Headers, Requests, and Responses return correct class strings
- Other: rewrite in ES2015 using Babel
- Other: use Codecov for code coverage tracking
- Other: update package.json script for npm 5
- Other: `encoding` module is now optional (alpha.7)
- Other: expose browser.js through package.json, avoid bundling mishaps (alpha.9)
- Other: allow TypeScript to `import` node-fetch by exposing default (alpha.9)

### HTTP requests

- Major: overwrite user's `Content-Length` if we can be sure our information is correct (per spec)
- Fix: errors in a response are caught before the body is accessed
- Fix: support WHATWG URL objects, created by `whatwg-url` package or `require('url').URL` in Node.js 7+

### Response and Request classes

- Major: `response.text()` no longer attempts to detect encoding, instead always opting for UTF-8 (per spec); use `response.textConverted()` for the v1 behavior
- Major: make `response.json()` throw error instead of returning an empty object on 204 no-content response (per spec; reverts behavior changed in v1.6.2)
- Major: internal methods are no longer exposed
- Major: throw error when a `GET` or `HEAD` Request is constructed with a non-null body (per spec)
- Enhance: add `response.arrayBuffer()` (also applies to Requests)
- Enhance: add experimental `response.blob()` (also applies to Requests)
- Enhance: `URLSearchParams` is now accepted as a body
- Enhance: wrap `response.json()` json parsing error as `FetchError`
- Fix: fix Request and Response with `null` body

### Headers class

- Major: remove `headers.getAll()`; make `get()` return all headers delimited by commas (per spec)
- Enhance: make Headers iterable
- Enhance: make Headers constructor accept an array of tuples
- Enhance: make sure header names and values are valid in HTTP
- Fix: coerce Headers prototype function parameters to strings, where applicable

### Documentation

- Enhance: more comprehensive API docs
- Enhance: add a list of default headers in README


# 1.x release

## Backport releases (v1.7.0 and beyond)

See [changelog on 1.x branch](https://github.com/node-fetch/node-fetch/blob/1.x/CHANGELOG.md) for details.

## v1.6.3

- Enhance: error handling document to explain `FetchError` design
- Fix: support `form-data` 2.x releases (requires `form-data` >= 2.1.0)

## v1.6.2

- Enhance: minor document update
- Fix: response.json() returns empty object on 204 no-content response instead of throwing a syntax error

## v1.6.1

- Fix: if `res.body` is a non-stream non-formdata object, we will call `body.toString` and send it as a string
- Fix: `counter` value is incorrectly set to `follow` value when wrapping Request instance
- Fix: documentation update

## v1.6.0

- Enhance: added `res.buffer()` api for convenience, it returns body as a Node.js buffer
- Enhance: better old server support by handling raw deflate response
- Enhance: skip encoding detection for non-HTML/XML response
- Enhance: minor document update
- Fix: HEAD request doesn't need decompression, as body is empty
- Fix: `req.body` now accepts a Node.js buffer

## v1.5.3

- Fix: handle 204 and 304 responses when body is empty but content-encoding is gzip/deflate
- Fix: allow resolving response and cloned response in any order
- Fix: avoid setting `content-length` when `form-data` body use streams
- Fix: send DELETE request with content-length when body is present
- Fix: allow any url when calling new Request, but still reject non-http(s) url in fetch

## v1.5.2

- Fix: allow node.js core to handle keep-alive connection pool when passing a custom agent

## v1.5.1

- Fix: redirect mode `manual` should work even when there is no redirection or broken redirection

## v1.5.0

- Enhance: rejected promise now use custom `Error` (thx to @pekeler)
- Enhance: `FetchError` contains `err.type` and `err.code`, allows for better error handling (thx to @pekeler)
- Enhance: basic support for redirect mode `manual` and `error`, allows for location header extraction (thx to @jimmywarting for the initial PR)

## v1.4.1

- Fix: wrapping Request instance with FormData body again should preserve the body as-is

## v1.4.0

- Enhance: Request and Response now have `clone` method (thx to @kirill-konshin for the initial PR)
- Enhance: Request and Response now have proper string and buffer body support (thx to @kirill-konshin)
- Enhance: Body constructor has been refactored out (thx to @kirill-konshin)
- Enhance: Headers now has `forEach` method (thx to @tricoder42)
- Enhance: back to 100% code coverage
- Fix: better form-data support (thx to @item4)
- Fix: better character encoding detection under chunked encoding (thx to @dsuket for the initial PR)

## v1.3.3

- Fix: make sure `Content-Length` header is set when body is string for POST/PUT/PATCH requests
- Fix: handle body stream error, for cases such as incorrect `Content-Encoding` header
- Fix: when following certain redirects, use `GET` on subsequent request per Fetch Spec
- Fix: `Request` and `Response` constructors now parse headers input using `Headers`

## v1.3.2

- Enhance: allow auto detect of form-data input (no `FormData` spec on node.js, this is form-data specific feature)

## v1.3.1

- Enhance: allow custom host header to be set (server-side only feature, as it's a forbidden header on client-side)

## v1.3.0

- Enhance: now `fetch.Request` is exposed as well

## v1.2.1

- Enhance: `Headers` now normalized `Number` value to `String`, prevent common mistakes

## v1.2.0

- Enhance: now fetch.Headers and fetch.Response are exposed, making testing easier

## v1.1.2

- Fix: `Headers` should only support `String` and `Array` properties, and ignore others

## v1.1.1

- Enhance: now req.headers accept both plain object and `Headers` instance

## v1.1.0

- Enhance: timeout now also applies to response body (in case of slow response)
- Fix: timeout is now cleared properly when fetch is done/has failed

## v1.0.6

- Fix: less greedy content-type charset matching

## v1.0.5

- Fix: when `follow = 0`, fetch should not follow redirect
- Enhance: update tests for better coverage
- Enhance: code formatting
- Enhance: clean up doc

## v1.0.4

- Enhance: test iojs support
- Enhance: timeout attached to socket event only fire once per redirect

## v1.0.3

- Fix: response size limit should reject large chunk
- Enhance: added character encoding detection for xml, such as rss/atom feed (encoding in DTD)

## v1.0.2

- Fix: added res.ok per spec change

## v1.0.0

- Enhance: better test coverage and doc


# 0.x release

## v0.1

- Major: initial public release

[Unreleased]: https://github.com/node-fetch/node-fetch/compare/v3.0.0-beta.10...HEAD
