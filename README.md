# Sample project for 'wdio-allure-ts'
------------
[![Build Status](https://travis-ci.org/cloudinary/wdio-allure-ts-example.svg?branch=master)](https://travis-ci.org/cloudinary/wdio-allure-ts-example)

A sample project with a quick introduction to the `wdio-allure-ts` framework and its usage on a real-world application.  
The project contains examples for the following:
* [Tests](https://github.com/cloudinary/wdio-allure-ts-example/tree/master/src/tests) for implementation
* [Page Object Model](https://github.com/cloudinary/wdio-allure-ts-example/tree/master/src/pages)
* [Allure Reporter](http://allure.qatools.ru), integrated and [configured](https://github.com/cloudinary/wdio-allure-ts-example/blob/0edb5c064cee25ecd41cc85b41aa1cc7caca7ae0/wdio.conf.js#L159) for attaching screenshots, [browser logs](https://github.com/cloudinary/wdio-allure-ts-example/blob/0edb5c064cee25ecd41cc85b41aa1cc7caca7ae0/wdio.conf.js#L260), and [HTML source](https://github.com/cloudinary/wdio-allure-ts-example/blob/0edb5c064cee25ecd41cc85b41aa1cc7caca7ae0/wdio.conf.js#L268) on test failures
* Configurations for [local](https://github.com/cloudinary/wdio-allure-ts-example/blob/master/wdio.dev.conf.js) and [CI execution](https://github.com/cloudinary/wdio-allure-ts-example/blob/master/wdio.ci.conf.js)
* [Selenium grid](https://github.com/angular/webdriver-manager) setup for test execution

## Getting Started
Use the commands below to get a copy of the project up and running on your local machine for development and testing purposes.
### Prerequisites

* [NodeJs](https://nodejs.org/en/ "NodeJs") runtime engine
* [Chrome](https://www.google.com/chrome/ "Chrome") and [FireFox](https://www.mozilla.org/en-US/ "FireFox")  for tests execution and display allure reporter
* [Java](http://www.oracle.com/technetwork/java/index.html "Java") for selenium grid and report generation 

------------
**Install packages:**
> npm install

**Start Selenium grid in separate terminal window:**
> npm run grid

**Execute test suite:** *(npm test)
> npm run suite todoMvcTestSuite

**Execute single test:**
> npm run spec ./lib/tests/TodoAngularTest.js

**Show report:** *require installed java and firefox*
> npm run report


**Additional commands can be found in the package.json**
## Code Structure

### Tests
Test are located under the **/test** folder. File names end with `Test.ts` <br/>
**Suggestion**: Use only one test to keep it more readable. In case of failure, only one test re-runs rather than all tests in the  class (Mocha limitation)

##### Test naming conventions:
`describe` should hold the name of the tests suite. This ensures that it will be represented in the report as one suite.
<br/> Each test should hold the file name of the test class.

**Example** where `TodoAngularTest` is a suite name and test file name is `TodoAngularTest.ts`
 ```javascript
   describe('TodoAngularTest', () => {
        it('Check URL', () => {
            //some test implementation
        });
    });
```
### Pages
The Page Object Model is used for tests and all page classes located under the `/pages` folder. Each class represents a UI object or functionality.
For example: `TodoAngularPage.ts` holds the main functionality of the page, while the `Button.ts` class holds basic functionality of the button component.

### Utils
TestHelperUtils class with that wraps all tests and has a common `describe` method that applies to all tests.

### Report example
[Click here](https://cloudinary.github.io/wdio-allure-ts-example/allure-report/index.html "Click")  for a report example.

### Related project
[wdio-allure-ts](https://github.com/cloudinary/wdio-allure-ts)
