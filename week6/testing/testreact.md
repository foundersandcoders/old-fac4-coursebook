# Testing React!

[TestUtils](http://facebook.github.io/react/docs/test-utils.html)

React has a built in library of test methods that you can plug in to your Jasmine style describe/it statemnts. Have a look at the methods [here](http://facebook.github.io/react/docs/test-utils.html).

The key method is 'render into document', which will create a component instance in the virtual DOM of your component class, and allow you to run tests on it in it's instantiated state

```js
ReactComponent renderIntoDocument(ReactComponent instance)
```