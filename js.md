#OOP in JS

##class in js
```
function Person(name) {
  this.name = name;
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name + '.');
  };
}
```
when create instances, simply

```
var person1 = new Person('Bob');
var person2 = new Person('Sarah');
```
After the new objects have been created, the person1 and person2 variables effectively contain the following objects:

```
{
  name : 'Bob',
  greeting : function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
}
```
We say effectively because in actual fact the functionality is still defined in the class, rather than in the object instances, in contrast to the object literal we looked at earlier.

###another way to create objects
```
var person1 = new Object();
```
or

```
var person = {};
person.name="";
...
```
or

```
var person1 = new Object({
  name : 'Chris',
  age : 38,
  greeting : function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
});
```

or

```
var person2 = Object.create(person1);
```
###prototype
The prototype property is one of the most confusingly-named parts of JavaScript — you might think that this points to the prototype object of the current object, but it doesn't (that's an internal object that can be accessed by \_\_proto__, remember?) prototype instead is a property containing an object on which you define members that you want to be inherited.

##function
When `function` means Expression and when it's a Declaration?
The rule is simple.

When the JavaScript parser sees a function in the main code flow, it assumes Function Declaration.

When a function comes as a part of a statement, it is a Function Expression.

#Syntax
##type
```
SO it seems string concatenation should have the highest priority, but when it comes to - or *, string concatenation could not happend, so consider calculation in the following situations
var x = "5" + 7;     // x.valueOf() is 57,  typeof x is a string
var x = 5 - 7;       // x.valueOf() is -2,  typeof x is a number
var x = 5 - "7";     // x.valueOf() is -2,  typeof x is a number
```
**mix + with string and number will give you concatenated string, mix string and number with - will give you number**

```
typeof "John"                 // Returns "string" 
typeof 3.14                   // Returns "number"
typeof NaN                    // Returns "number"
typeof false                  // Returns "boolean"
typeof [1,2,3,4]              // Returns "object"
typeof {name:'John', age:34}  // Returns "object"
typeof new Date()             // Returns "object"
typeof function () {}         // Returns "function"
typeof myCar                  // Returns "undefined" *
typeof null                   // Returns "object"
typeof + "a"                  // Returns "number"
```
```
<!DOCTYPE html>
<html lang="en-US">
```

#DOM
```
document.body.style.backgroundColor = "red";

element.addEventListener("click", handler, false);
or
element.onlick = function(){}

elem.addEventListener( "click" , handler, false) // assign the handler

elem.removeEventListener( "click", handler, false) // remove the handler

```

##form manipulation
```
var form = document.querySelector('form');
var fname = document.getElementById('fname');
var lname = document.getElementById('lname');
var submit = document.getElementById('submit');
var para = document.querySelector('p');

form.onsubmit = function(e) {
  if(fname.value === '' || lname.value === '') {
    e.preventDefault();
    para.textContent = 'You need to fill in both names!'
  }
}
```

##closure and scope
If a variable is set, but not found anywhere, then it is created in the outmost LexicalEnvironment, which is window

##AJAX

```
function loadXMLDoc() {
    var xmlhttp = new XMLHttpRequest();

    xmlhttp.onreadystatechange = function() {
        if (xmlhttp.readyState == XMLHttpRequest.DONE ) {
           if (xmlhttp.status == 200) {
               document.getElementById("myDiv").innerHTML = xmlhttp.responseText;
           }
           else if (xmlhttp.status == 400) {
              alert('There was an error 400');
           }
           else {
               alert('something else other than 200 was returned');
           }
        }
    };

    xmlhttp.open("GET", "ajax_info.txt", true);
    xmlhttp.send();
}
```