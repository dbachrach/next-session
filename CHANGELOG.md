# Changelog

## 2.0.1

### Patches

- Documentation: Fix View Count examples and add document middleware implementation in README. (#27)

Special thanks to @dbachrach (for pointing out `document middleware`) and @dorinesinenco for fixing the View Count example.

## 2.0.0

### Major

- :boom: default import `session()` is replaced with named import `withSession()`:

  ```javascript
  //  BEFORE
  import session from 'next-session';
  //  AFTER
  import { withSession } from 'next-session';

  //  BEFORE
  export session(handler);
  //  AFTER
  export withSession(handler);
  ```

### Minor

- :sparkles: withSession now supports getInitialProps for `_app`, `_document`, and pages. (#20)

## 1.2.1

This version drops `Bluebird`. If you care deeply about performance. Please use `Bluebird` to promisify `next-session`.

### Minor

- Remove `Babel` and rewrite with CommonJS (#18)
- Remove `Bluebird` and use native Promise (#19)

## 1.1.0

### Minor

- Add support for `getIntialProps` (#12)

## 1.0.0

:tada: **Stable release** :tada:

### Major

- Add **StorePromisify**, which provides support for `callback` stores (31c6de4233ece17de54d88b444392cd2f6574223)
- Add tests, coverages, Travis CI
- Babel now targets **Node 6+**

### Minor

- Remove `lodash.merge` dependency and to use `Object.assign`.
- Add listener for store readiness.
- Store is abstracted into `session/store.js`.

### Patches

- Correct touch() arguments (3bffc16dd566127440e3716956dc0dd7c583b710).
- Fix memoryStore not working: memoryStore must extends Store (5c9741a87bdf34c659566bc3e26b4863d8c831ec).

## 0.2.0

### Minor

- Add session touch: Extend session lifetime despite no modification. (#4)
- Add rolling option: Force cookie to be set on every request. (#4)
- Add parseToMs to parse keywords `Years`, `Months`, `Days`, etc. (f487b1c)

## 0.1.1

### Minor

- Remove lodash.isequal and lodash.omit. `next-session` now compare object hash instead of deep compare. (436feff)
- Documentation: Add global middleware usage and fix MemoryStore link. (91f03a7)

## 0.1.0

## Major

- Rewrite with **Promise**, backed by [Bluebird](https://github.com/petkaantonov/bluebird). (7fbb337, 9ab6313)

## Minor

- Change `MemoryStore` to use **Promise**. (a178ee0)
- Add global middleware approach to using `next-session`. (91f03a7)

## 0.0.2

When installing from `npm`, release **0.0.1** does not work since **node** does not support `ES6 Import/Export`. This release add babel to transpile ES6 to ES5.

Moving source code to `/src`. (f5cd9fe)
Add and config Babel 7 to transpile from `/src` to `/lib` using `@babel/preset-env`. (fd2012e)
Add a detailed example on how to use `next-session` in README.md: 1f112dc. (1f112dc)

## 0.0.1

**This release is broken**

- Add core functionalities: set, get, and destroy sessions.
- Add the ability for custom ID generating function.
- Add Cookie attribute options including Secure, httpOnly, Path, Domain, SameSite, Max-Age. (No Expires yet)
- Add the ability to implement custom Session store.
- Session store: Add Memory Store (Not for production environment).
