# 0.8.0

_Note: Major version 0 releases are for initial development, and backwards compatible changes may be introduced at any time._

## Docs
- Added documentation to the [docs folder](https://github.com/angular/protractor/tree/master/docs).

- ([08ef244](https://github.com/angular/protractor/commit/08ef244217fb83206c818c84cbe8f07999116ee3)) Adding debugging tests showing different types of timeouts, and fixing
a bug where scheduled tasks from a previous it block would run into
the next in case of a timeout.

## Features

- ([1c7eae0](https://github.com/angular/protractor/commit/1c7eae0c09f13b7068f81324f24967709e264241)) Updating the binary script to understand debug, so that
protractor debug conf.js works.

- ([7a59479](https://github.com/angular/protractor/commit/7a594791b5ac6616de9c98dcd7d44ecaffb0e8a3)) Adding a 'debug' function to protractor. This schedules a debugger pause
within the webdriver control flow.

- ([679c82d](https://github.com/angular/protractor/commit/679c82d510ea016690fba259db50b4afa36154cc)) Mixing in all webdriver exports to protractor. This means that webdriver
classes such as ActionSequence and Keys are accessible on the global
protractor.

- ([3c76246](https://github.com/angular/protractor/commit/3c76246a01e584bc30da645a36e75920b5397251)) Added nested angular app (ng-app on an element other than `<html>` or `<body>`) capability via conf file.

## Bug fixes

- ([1c9b98d](https://github.com/angular/protractor/commit/1c9b98d0464bbe57194cf340c6e5942cbe7c8385)) Fixed Sauce issues: low timeouts, shutdown and init order.

## Breaking Changes

- Now running selenium 2.25. Requires updating WebDriverJS and the selenium standalone binary and chromedriver binary.

- ([a54abfb](https://github.com/angular/protractor/commit/a54abfbbfd3b13be5144e64e52a267c73d409a81)) Spec paths in configuration files are now resolved from the location of the spec file instead of the current working directory when the command line is run.



# 0.7.0

_Note: Major version 0 releases are for initial development, and backwards compatible changes may be introduced at any time._

## Features

- ([7966912](https://github.com/angular/protractor/commit/796691205795d93fe12c998d20a58c8220ac6fb7)) Updating to Selenium 2.24.

- ([90f0a94](https://github.com/angular/protractor/commit/90f0a942b09faff5924674a20ce7705b6d685eba)) Instead of having tests run with the protractor runner need to require()
the protractor library, publish it to the global namespace. This insures
the instance of protractor used within the tests is the same as the
one used on the command line. Closes #36. Version bump for incompatible
API changes.

- ([cb373c9](https://github.com/angular/protractor/commit/cb373c99a7e33c5514bf1d2728a64f631ec8784c)) Adding glob matching to the spec files from the config. Closes #29.


## Breaking changes

- Now running on selenium 2.24. Requires updating WebDriverJS and the selenium standalone binary.

- The protractor runner now publishes `protractor` to the global namespace and sets up the Jasmine-WebDriver adapter. Tests run with this should no longer include

````javascript
// var protractor = require('protractor'); // No longer needed!
// require('protractor/jasminewd'); // No longer needed!

var ptor = protractor.getInstance(); // This should just work now.
````
