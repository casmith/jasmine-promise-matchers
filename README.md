Jasmine Promise Matchers
================

Custom matchers for **[Angular promises](http://docs.angularjs.org/api/ng/service/$q)** and **[Jasmine 1.3 - 2.x](https://jasmine.github.io/)**.

# Overview

Tests often require simple assertions about Promise resolution/rejection. This could be accomplished by spying on the Promise object *or* by chaining on another Promise (complete with *expects* statements)- but this is a lot of work. The following matchers allow basic assertions to be made about Promises via a brief expectation.

(Note that each of the below matchers triggers a `$rootScope` digest so that their resolve/reject methods will be triggered. You do not need to trigger this digest yourself but should be aware of it in case it impacts other asynchronous portions of your test.)


# Installation

```
bower install jasmine-promise-matchers --save-dev
npm install jasmine-promise-matchers --save-dev
```

To use this library in your Jasmine tests, simply install it like so:

```
beforeEach(function() {
  installPromiseMatchers();
});
```

Be sure to call [`angular.mock.module`](https://docs.angularjs.org/api/ngMock/function/angular.mock.module) before installing the promise matcher library (because the promise matcher installer uses the `injector`).


# Sublime Plugin

[@Hyzual](https://github.com/Hyzual) has created a Sublime plugin for this library. Find our more info about that plugin [here](https://packagecontrol.io/packages/Jasmine%20Promise%20Matchers).


# Matchers

### toBeRejected
Verifies that a Promise is (or has been) rejected.
```js
expect(promise).toBeRejected();
```

### toBeRejectedWith
Verifies that a Promise is (or has been) rejected with the specified parameter.
```js
expect(promise).toBeRejectedWith('something');

// Asymmetric matching is also supported for objects:
expect(promise).toBeRejectedWith(jasmine.objectContaining({partial: 'match'}));
```

### toBeResolved
Verifies that a Promise is (or has been) resolved.
```js
expect(promise).toBeResolved();
```

### toBeResolvedWith
Verifies that a Promise is (or has been) resolved with the specified parameter.
```js
expect(promise).toBeResolvedWith('something');

// Asymmetric matching is also supported for objects:
expect(promise).toBeResolvedWith(jasmine.objectContaining({partial: 'match'}));
```
