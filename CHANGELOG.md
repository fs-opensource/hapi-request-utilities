# Changelog


## [4.1.1](https://github.com/futurestudio/hapi-request-utilities/compare/v4.1.0...v4.1.1) - 2020-08-17

### Updated
- removed badge link in Readme


## [4.1.0](https://github.com/futurestudio/hapi-request-utilities/compare/v4.0.0...v4.1.0) - 2020-08-17

### Added
- `request.ip()` method retrieving the client’s IP address
- add full TypeScript definitions for all request utility methods
- add support to check multiple keys as separate strings without using an array on
  - `only`, `except`, `has`, `filled`, `missing`
  - Example:

  ```js
  // before: use an array when checking multiple values
  request.has(['email', 'password'])

  // now: use array or individual strings, both are supported
  request.has('email', 'password')
  request.has(['email', 'password'])
  ```

### Updated
- test Node.js v14
- bump dependencies
- move TypeScript definitions to `typings` directory


## [4.0.0](https://github.com/futurestudio/hapi-request-utilities/compare/v3.0.0...v4.0.0) - 2020-01-10

### Breaking Changes
- require Node.js v12
  - this change aligns with the hapi ecosystem requiring Node.js v12 with the release of hapi 19


## [3.0.0](https://github.com/futurestudio/hapi-request-utilities/compare/v2.2.0...v3.0.0) - 2019-11-15

### Added
- `request.missing(keys)` as the inverse of `request.has(keys)` to determine whether the request input contains all given keys
  - Use it like this: `request.missing('email')` or `request.missing(['email', 'password'])`
- `request.root()`: returns the requests’s root domain
  - For example, requesting `https://user:pass@sub.example.com/posts?filter=withVideo` returns `https://sub.example.com`.
- `request.uri()`: returns the requests’s URL with path, without query strings
  - For example, requesting `https://user:pass@example.com/posts?filter=withVideo` returns `https://example.com/posts`
  - I couldn’t use `request.url()` because hapi provides a getter for `request.url`
- `request.fullUrl()` (or aliased `request.fullUri()`): returns the requests’s full URL with query strings and hashes
  - For example, requesting `https://user:pass@example.com/posts?filter=withVideo` returns `https://example.com/posts?filter=withVideo`.

### Updated
- bump dependencies
- require hapi v18

### Breaking Changes
- require hapi v18

This release requires hapi v18. Hapi migrated the `request.url` property to a WHATWG URL in v18. The new methods in `hapi-request-utilities` build on top of a WHATWG URL instance.


## [2.2.0](https://github.com/futurestudio/hapi-request-utilities/compare/v2.1.1...v2.2.0) - 2019-10-17

### Added
- basic TypeScript declarations in `lib/index.d.ts`


## [2.1.2](https://github.com/futurestudio/hapi-request-utilities/compare/v2.1.1...v2.1.2) - 2019-10-12

### Updated
- bump dependencies


## [2.1.1](https://github.com/futurestudio/hapi-request-utilities/compare/v2.1.0...v2.1.1) - 2019-08-08

### Fixed
- `request.user` stores the authenticated credentials


## [2.1.0](https://github.com/futurestudio/hapi-request-utilities/compare/v2.0.0...v2.1.0) - 2019-07-29

### Added
- `request.input('key')` to retrieve an input item from the `request`
- `request.isAuthenticated()` is a shortcut for `request.auth.isAuthenticated`. It returns a boolean whether the request is authenticated:
  - `true`: successfully authenticated the request via an auth strategy
  - `false`: unauthenticated request that hasn't passed an auth strategy

### Updated
- bump dependencies


## [2.0.0](https://github.com/futurestudio/hapi-request-utilities/compare/v1.3.0...v2.0.0) - 2019-04-24

### Updated
- `request.user` returns the authenticated credentials, was previously a function `request.user()`
- updating to the scoped hapi dependencies
- bump dependencies


## [1.3.0](https://github.com/futurestudio/hapi-request-utilities/compare/v1.2.1...v1.3.0) - 2019-02-28

### Added
- `request.has(keys)`: determine whether the request includes the given input `keys`
- `request.filled(keys)`: determines whether the request includes a non-empty value for the input `keys`


## [1.2.1](https://github.com/futurestudio/hapi-request-utilities/compare/v1.2.0...v1.2.1) - 2019-02-18

### Updated
- bump dependencies
- fix badges in Readme


## [1.2.0](https://github.com/futurestudio/hapi-request-utilities/compare/v1.1.1...v1.2.0) - 2019-01-26

### Added
- `request.user()`: returns the authenticated request credentials. It's a shortcut for `request.auth.credentials`

### Updated
- Readme: rename GitHub references `futurestudio -> futurestudio`


## [1.1.1](https://github.com/futurestudio/hapi-request-utilities/compare/v1.1.0...v1.1.1) - 2019-01-22

### Added
- add Greenkeeper Badge to Readme

### Updated
- test plugin for hapi 18
- Readme: link to detailed documentation in Boost docs
- bump dependencies


## [1.1.0](https://github.com/futurestudio/hapi-request-utilities/compare/v1.0.4...v1.1.0) - 2018-11-23

### Added
- `bearerToken` method to get the bearer token from request headers

### Updated
- Doc blocks on methods: added param and return types
- Dependencies


## [1.0.4](https://github.com/futurestudio/hapi-request-utilities/compare/v1.0.3...v1.0.4) - 2018-11-07

### Updated
- Readme: add logo
- Run tests for Node versions 8, 10, and 11
- Dependencies


## [1.0.3](https://github.com/futurestudio/hapi-request-utilities/compare/v1.0.2...v1.0.3) - 2018-08-21

### Updated
- Readme: quick navigation and fix logo size on small screens


### [1.0.2](https://github.com/futurestudio/hapi-request-utilities/compare/v1.0.1...v1.0.2) - 2018-08-02

### Updated
- add contributors
- update readme


### [1.0.1](https://github.com/futurestudio/hapi-request-utilities/compare/v1.0.0...v1.0.1) - 2018-07-30

### Updated
- move `husky` to `devDependencies` (was accidentally installed in `dependencies`)


## 1.0.0 - 2018-07-30

### Added
- `1.0.0` release 🚀 🎉
