# Setup

## Framework

In accordance with the React devs suggestion, we're going to use [Jest](http://facebook.github.io/jest/) to run our tests. However, if you want to try a different test framework, there's nothing stopping you! Don't get confused between React and Jest -they're entirely different and independent. If you like Jest, it could be your go to  all purpose test suite..

## Warning

Jest doesn't play well with version 0.12 of Node. If you experience errors (e.g. Segmentation Fault), you may need to install npm packages ```n``` or ```nvm``` to roll back your version of node to 0.10.x.  Version 0.10.33 seems to work well.

If using an older version of node, you may get an error message requiring you to use ```--harmony``` command line flag when running your tests. You can get around this by installing npm ```harmonize``` Instructions [here](https://www.npmjs.com/package/harmonize).

## Get started with Jest

[Getting Started](http://facebook.github.io/jest/docs/getting-started.html)

There are plenty of complications to come, but here are the basics of getting a Jest test suite up and running.

1. Create a ```__test__``` directory in your project directory.

2. Create a package.json (e.g. use ```npm init```).

3. Install jest-cli and add it to your package.json:   
  ```
  npm install jest-cli --save-dev
  ```

4. In your package.json, set the 'test' script to 'jest':  
```
{
 ...json
 "scripts": {
   "test": "jest"
 }
 ...
}
```

5. Run your tests with ```npm test```.  Jest will find and run all tests in your __test__ dir.


## Run a basic test

1. Create a file with a function you want to test in your project directory, and make sure you export the function. e.g.    

```js
// sum.js
function sum(value1, value2) {
  return value1 + value2;
}
module.exports = sum;
```

2. Create a file for your tests in your ```__tests__``` dir. 

3. Require the file you're testing. Jest different syntax for this, to the usual node 'require'.  Jest mocks functions by default, but we don't want it to mock the code we're actually **testing**. So we write:  

```js
jest.dontMock('../fileToTest.js');
```

4.  Write your tests with in the [Jasmine](http://jasmine.github.io/2.2/introduction.html) 'describe' style (Jest is built on Jasmine). e.g.  

```js
// __tests__/sum-test.js

jest.dontMock('../sum');

describe('sum', function() {
 it('adds 1 + 2 to equal 3', function() {
   var sum = require('../sum');
   expect(sum(1, 2)).toBe(3);
 });
});
```


## Jasmine

A typical Jasmine test takes this form:  

```js
describe("A test suite name", function() {
  
  it("A description of your expectation", function() {
    expect(true).toBe(true);
  });
});
```

1. **describe()** opens a new test block. 
  *The first parameter is a string describing the suite of tests. It's for your benefit, it doesn't e.g. need to match any function names.  
  *The second parameter is a callback which will hold your tests.

2. **it()** starts a new test.
  *The first parameter is a string describing your expectation for this test.  
  *The second parameter is a callback which will hold **this** test (or 'expectation'). 

3. **expect()** takes the function call you are testing as an argument.  

4. **toBe()** is a **matcher**.
  *It takes your expected results as an argument.

5. **Matchers**. Jasmine has a range of these. Consult the [docs](http://jasmine.github.io/2.2/introduction.html#section-Included_Matchers), but key examples are:
  * toBe()
  * toEqual()
  * **not**.anyMatcher() => negation


## Setting up Jest to test React

At last!

1. You will need to require React, and specifically the React TestUtils in your test file. 
 
```js
var React = require('react/addons'),
    TestUtils = React.addons.TestUtils;
```

2. If you're using JSX, you will need to add a file with a helper function to convert it. e.g. Create a file called ```preprocessor.js``` containing the following code: 

```js
var ReactTools = require('react-tools');

module.exports = {
  process: function(src) {
    return ReactTools.transform(src);
  }
};
```

3. To use this preprocessor, you will need to add a reference to it to your package.json. This example also stops Jest mocking React, and assumes that preprocessor.js is an a ```support``` dir.  

```js
"jest": {
  "scriptPreprocessor": "<rootDir>/support/preprocessor.js",
  "unmockedModulePathPatterns": [
    "<rootDir>/node_modules/react"
  ]
}
```




