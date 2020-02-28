# Removing tests from dev build

When you run
```
ember b
```

or 

```
ember s
```
the build is run on `development` environment until you mark it as production build by default.

But internally, ember-cli adds the test files as well with your development build since, you can access them using `http://localhost:4200/tests`. But most of the times, we generally run
```
ember test
```
for validating test cases. In development build scenario, we would not require test files. In order to eliminate unnecessary set of test files being part of the dev build and slowing things down, you can remove them by using the following configuration

```javascript
let app = new EmberApp(defaults, {
  tests: false,
  ...
});
```
