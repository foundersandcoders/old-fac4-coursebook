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

####binding:

####data binding:

####virtual DOM:

####HTML attributes:

####string concatenation:

####XSS injection: