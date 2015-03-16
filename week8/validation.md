# Validation

------

### Using Joi

Validation is like flossing: you know you should do it, but it’s easy to skip. And just like flossing, if you neglecting your validation, you’re asking for trouble.

Validating data can be very helpful in making sure that your application is stable and secure.

The **Joi module** is Hapi’s answer to validation, but you don’t need to be using Hapi in order to use Joi.

By default, all available validators are set to **true** which means that no validation will be performed.

If the validation parameter is set to **false** it signifies that **no value is allowed for that parameter**.

### What can Joi do?

Joi is basically like running a test. You are testing your data to check that it meets the constraints of the schema object.

* Joi can validate any object
* Joi can easily validate requests made to a Hapi application

------

### Let's Play with Joi

```
var Joi = require('joi');

var schema = {
  username: Joi.string().alphanum().min(3).max(30).with('birthyear').required(),
  birthyear: Joi.number().integer().min(1900).max(2013)
};

module.exports = function(data, config) {
  config = config || {};
  var err = Joi.validate(data, schema, config);
  console.dir(err ? err : 'Valid!');
}

```

On line 10 where we call ```Joi.validate(data, schema, config)``` , the data is being matched against the schema and returns an error if anything’s wrong.

In other words, if everything in the data object is valid according to the schema, the call returns ```null```, otherwise an ```Error``` object is returned.

------

### Usage

Usage is a two steps process. First, a schema is constructed where the types and constraints are defined. Please see example below - please note you must first ```require``` Joi in order to use it: 

```
var Joi = require('joi');

var schema = Joi.object().options({ abortEarly: false }).keys({
    email: Joi.string().email().required().label('User Email'),
    password: Joi.string().min(8).required(),
    password_confirmation: Joi.any().valid(Joi.ref('password')).required().options({ language: { any: { allowOnly: 'must match password' }, label: 'Password Confirmation' } }).label('This label is not used because language.label takes precedence'),
    first_name: Joi.string().required(),
    last_name: Joi.string().required(),
    company: Joi.string().optional()
});
```

Please refer to [HapiJS/Joi](https://github.com/hapijs/joi) for more information and a list of commands/methods that Joi uses. 