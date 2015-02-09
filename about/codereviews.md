# Code reviews

Work in pairs. Treat each code review as a structured dialogue, involving a series of questions and answers. If you do not understand a question or the answer, seek clarification before moving on.

Suggested questions

1. Are you using sensible names for all your variables? Is it obvious at first glance what each of them is being used for?

1. Are you polluting the global namespace unnecessarily with variables that could be put into functions or objects?

1. Are you declaring all your variable names at the top of the block in which they are used (this is particularly important in a language like JavaScript)?

1. Is your code *DRY*: Have you factored out your code or are you repeating yourself?

1. Are you keeping structure (HMTL), styling (CSS), data and bahaviour separate?

1. Is your code nicely commented?

1. Is your code consistently indented?

1. What feedback to you get from running jshint or some other code linting tool over your code?

See [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) for more ideas.


### Functions

1. When defining a new function are we using sensible names? Is it obvious at first glance what the function is for?

1. What are the inputs for the function? And are these inputs reflected in the arguments?

1. Do you expect the function to have a return value and if so what do you expect it to be?

1. Are your functions easy to test?

1. As you work through the problem, are you working from the outsides in or are you trying to solve the problem in a linear sequence from top to bottom?

### Unit tests

1. Are you writing tests for your functions?

1. What's a sensible first test for the function? Is this the simplest possible test that you can think of?

1. As you work through the problem, are all your passing tests still passing? If not, why not?




