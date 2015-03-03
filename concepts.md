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
How suitable it is for reuse.<br>
Some factors that influence how reusable the code is:<br>
 * How dry the code is<br>
 * How independant the code is<br>
 * How extensible the code is<br>
 * How Modular the code is

####composition:
What its made up of

####components:
React components are very simple. You can think of them as simple functions that take in props and state and render HTML.

####templates:
A template is a generic  'structure' for a web page, data is then injected into it and functionality (javascript) added to make a final page.

"Templates separate technologies not concerns" e.g. Templates separate html from javascript but don't separate up a page with concern for different component areas (aka functional areas)

Think of Jekyll and the _layout directory.  We used liquid and YaML to do this templating.

Javascript libraries that deal with setting up templates:
Underscore, Mustache, Handlebars, etc

####coupling:
Coupling is the act of joining two things together.  In software development, coupling refers to the degree to which one software component is dependant upon another.  

 * tightly-coupled architecture - when each component and its associated components must be present in order for code to be executed or compiled.  
 * loosely-coupled architecture - when components can remain autonomous and allow middleware software to manage communication between them.
 * decoupled architecture - the components can operate completely separately and independently. 

####cohesion:
refers to the degree to which the elements of a module belong together.     
Thus, it is a measure of how strongly related each piece of functionality expressed by the source code of a software module is.  
In Objects - all of the functions and attributes will have a high level of cohesion

####separation of concerns:
separation of concerns (SoC) is a design principle for separating a computer program into distinct sections, such that each section addresses a separate concern. A concern is a set of information that affects the code of a computer program. A concern can be as general as the details of the hardware the code is being optimized for, or as specific as the name of a class to instantiate

Concerns are the different aspects of software functionality. For instance, the "business logic" of software is a concern, and the interface through which a person uses this logic is another.

The separation of concerns is keeping the code for each of these concerns separate. Changing the interface should not require changing the business logic code, and vice versa.

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
Cross-site scripting (XSS) is a type of computer security vulnerability typically found in Web applications. XSS enables attackers to inject client-side script into Web pages viewed by other users
<p>
A type of hacker attack where the hacker injects some malicious code in the form of a string which is run when the program executes some function related to the data. 
