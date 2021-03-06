# Change log

## 4.2.1

- FIX: Fix issue where `e.cause` was assumed to be a function, causing
  serializer to fail.

## 4.2.0

- FIX: Use safe-json-stringify module to to do JSON serialization of objects
  with circular objects.

## 4.1.0

- NEW: add bunyan serializer for handling the new `context` property on errors
  created by restify-errors.


## 4.0.0

- NEW: Error constructor now takes `options.context`, which is a bucket of
  random properties that are saved to the Error object being created.
- NEW: All Errors now have `toString()` and `toJSON()` methods. These are
  overridable via `makeConstructor()`.
- BREAKING: `code` and `restCode` properties were normalized across all
  classes. `code` property now has a value of 'Error' for HttpError and
  RestError. Any subclass will have the name of the error, minus 'Error',
  i.e., GatewayTimeoutError has a code of GatewayTimeout. All code and
  restCode properties are now overridable.

## 3.1.0
- rev dependencies

## 3.0.0
- restify/node-restify#844 Errors now live in its own repo and npm module.
- all error constructors now support [VError](https://github.com/davepacheco/node-verror) constructor args.
- Support subclass and custom error types via `makeConstructor()`
- Support creating errors using HTTP status codes via `makeErrFromCode()`. Was
  previously a private method used to create internal error types, this is now
  exposed publicly for user consumption.

