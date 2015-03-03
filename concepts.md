# Concepts

####Declarative Programming: 

Allows us to describe what we want, and let the underlying software/computer/etc deal with how it should happen

***Imperative Code:***
```
var numbers = [1,2,3,4,5]
var doubled = []

for(var i = 0; i < numbers.length; i++) {
  var newNumber = numbers[i] * 2
  doubled.push(newNumber)
}
console.log(doubled) //=> [2,4,6,8,10]
```
***Declarative Code:***
```
var numbers = [1,2,3,4,5]
 
var doubled = numbers.map(function(n) {
  return n * 2
})
console.log(doubled) //=> [2,4,6,8,10]
```

####Rendering:
The process of converting/translating a form of data into another form of data usually visual

####Mutability:
Its changeable unlike strings, numbers which are immutable
<p> Arrays, Objects are mutable

####reusability:
you can use it again

####composition:
What its made up of
####components:

####templates:

####coupling:

####cohesion:

####separation of concerns:

####scope:
Scope is where code lives. Scope in JS is created by functions. Code can only see and manipulate other code withing the same scope or higher scope. 

####binding:
Binding in this sense refers to the javascript method 'bind()'. myFunc.bind(x) forces x to be treated as the 'this' value in the myFunc function. The reason for this is beyond the scope of this brief definition.
An alternative usage of 'bind' follows.

####data binding:
As was alluded to in the previous definition, an alternative usage of bind is in the context of data-binding. Two-way binding refers to binding changes to an object's properties to changes in the UI and vice-versa. If the data changes, the UI should correspondingly change, and vice-versa.
Consider D3's data-binding.

####virtual DOM:
The virtual DOM, or vDOM as its friends call it, is React's way of getting around the age-old problem of perfomance. React generates a representation of the DOM (vDOM - how it should look), against which it compares changes in the actual DOM (how it actually looks), in order to minimise DOM manipulation.

In other words, it compares the old-version of the DOM to a new version of the DOM and calculates the minimum number of changes required to bring the old in line with the new (i.e. to render the UI).

####HTML attributes:
Attributes provide additional information about HTML elements.
e.g. Width, Height, Type, Href, Src, Hidden

####string concatenation:
Joining strings together to form a single string

####XSS injection:
