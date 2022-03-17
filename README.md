
# Javascript
> *This page is an explanation of many JavaScript concepts with assumption that you already know some programming language.*

## Variables

---
```javascript

var x;
let y; // => let was introduced in ES6 to improve variables scopes. Essentially to fix 'var'
const z = "This cannot be changed later on."; 

x = 10;
y = 20;
let total = y + x; // => output: 30
```

## Data Types
---
```javascript
let length = 16;                               // Number
let lastName = "Johnson";                      // String
let x = {firstName:"John", lastName:"Doe"};    // Object 
```



## Functions

---

```javascript
// Built-in functions:
console.log("Hello world!");

// Functions
function square(number) {
    return number * number;
}

// A function must be invoked to run code within itself.
square(9) // => output: 81

// Arrow functions were implemented in ES6
const ES6Function = (number) =>{
    return number * number;
}

// The above function can be simplified (since it is a one liner) by the following:

const arrowFunc = () => number * number;


// A function must be invoked to run code within itself.
let x = ES6Function(9);
console.log(x) // => output: 81
```

## Objects 

---

Objects are comprised of *key* and *value* pairs. You can have as many as you would like/need.

```javascript
const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

// OR

const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

// To get the values within the object, you need the object name and the property name. As such:

objectName.propertyName;

// OR 

objectName["propertyName"];

// Here is an actual example:

person.firstName; // => "John"
person["firstName"]; // => "John"

// In JavaScript, when you create an object, you can also store functions in them. 
// If you store a function in an object, you have just created something we call a method. Here is an example:

const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName; // This method will return the full name of the person instance in this object.
  }
};
```

## Events 

---

    Events are changes in the DOM (Document Object Model), which is essentially the HTML of the page. You can use JavaScript to alter and create "reactions" to those events. An example would be when you click a button on the page and it shows you the curent time. Check below: 


```html
<!-- When the button is clicked, the "The time is?" text will be replaced by the current time. -->
<button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button> 


<!-- The code above can be replaced by the following: -->
<button onclick="this.innerHTML = Date()">The time is?</button>

<!-- It can also be replaced by a function in a JavaScript file. -->
<button onclick="displayDate()">The time is?</button>

<script>
    // Arrow functions return by default. 
    const displayDate = () => Date();
</script>

```

Here is a list of some common HTML events:
| Event | 	Description |
| :--- | :----: |
| onchange | 	An HTML element has been changed |
| onclick | 	The user clicks an HTML element |
| onmouseover | 	The user moves the mouse over an HTML element |
| onmouseout | 	The user moves the mouse away from an HTML element |
| onkeydown | 	The user pushes a keyboard key |
| onload | 	The browser has finished loading the page |


## Arrays

---

*Note: arrays are also objects. However, there are slight differences, such as the fact that arrays use numbers for indexing, objects use names. So, when to use arrays and when to use objects?*

#### Choosing: 
* You should use objects when you want the element names to be strings (text).
* You should use arrays when you want the element names to be numbers.


```javascript
// An array can be created as such:
const arrayName = [item1, item2, ...]; 
const carsMake = ["Mercedes", "Bmw", "Tesla"]

// The way to acces the values within an array, is by indexing. 
carsMake[0]; // => output: "Mercedes"

const fruits = ["Banana", "Orange", "Apple", "Mango"]; 
let length = fruits.length; // Returns the number of elements

fruits.sort()   // Sorts the array 

const fruits = ["Banana", "Orange", "Apple"];
fruits.push("Lemon");  // Adds a new element (Lemon) to fruits at the last index.

const fruits = ["Banana", "Orange", "Apple"];
fruits[6] = "Lemon";  // Creates undefined "holes" in fruits 
// The code above adds Lemon to the array, but adds "Null" to all indexes from 3 (inclusively) to 6.

```

The class "Array", contains the constructor "Array", which means that you can initiallize an array with the values by doing such:

```javascript

const points = new Array();
const points = [];

const points = new Array(40, 100, 1, 5, 25, 10);
const points = [40, 100, 1, 5, 25, 10];

// Create an array with one element:
const points = [40];

// Create an array with 40 undefined elements:
const points = new Array(40);

``` 

### Array Methods
---

```javascript
// Convert to string
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();

// Concatenate array items by a separator (* in this case)
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * ");

// Remove last item from array
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();

// Adds new item as the last item of the array
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");

// Method to used to add new items to array at specific locations
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");

// The first parameter (2) defines the position where new elements should be added (spliced in).
// The second parameter (0) defines how many elements should be removed.
// The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be added.
```

## Switch 

---

### Syntax

```javascript
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block

// Concrete example:
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
     day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case 6:
    day = "Saturday";
}

// Answer depends on the value of the day. 
} 

```

## Loops

---

```javascript
// For loop
for (loopingVariable; condition; increments) {
  // Code to run every iteration
} 
// Example:
for (let i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
} 



// For IN
for (key in object) {
  // code block to be executed
}

const person = {fname:"John", lname:"Doe", age:25};

let text = "";
for (let x in person) {
  text += person[x];
} 


// For OF
for (variable of iterable) {
  // code block to be executed
}

const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text += x;
}



// While loop
while (condition) {
  // code block to be executed
}

while (i < 10) {
    text += "The number is " + i;
    i++;

    if (i == 9){ break; }
    // The break statement "jumps out" of a loop. 
    if (i == 5){ continue; }
    // The continue statement "jumps over" one iteration in the loop.

}
```
## Sets 
---

A *Set* is a unique collection of values. Each value can only occur once within the set. 

```javascript
// Create a Set
const letters = new Set(["a","b","c"]);

// ================================

// Create a Set
const letters = new Set();

// Add Values to the Set
letters.add("a");
letters.add("b");
letters.add("c");

// ================================

// Create a Set
const letters = new Set();

// Create Variables
const a = "a";
const b = "b";
const c = "c";

// Add Variables to the Set
letters.add(a);
letters.add(b);
letters.add(c);

// ================================

// Adds to the set
letters.add("d");
letters.add("e");

// ================================

letters.values()   // Returns [object Set Iterator] 
// With it you can iterate with a loop.
// List all Elements
let text = "";
for (const x of letters.values()) {
  text += x;
}



```
## Objects 
---

A map holds key-value pairs (kind of like dictionaries in Python) where keys can be of any possible data-type.

Maps can be similar to Objects, but here are the key differences:

| X | Object | Map |
| :--- | :--- | :--- | 
| Iterable | Not directly iterable | Directly iterable |
| Size | Do not have a size property | Have a size property |
| Key Types | Keys must be Strings (or Symbols) | Keys can be any datatype |
| Key Order | Keys are not well ordered | Keys are ordered by insertion |
| Defaults | Have default keys | Do not have default keys |

```javascript

// Create a Map
const fruits = new Map([
  ["apples", 500],
  ["bananas", 300],
  ["oranges", 200]
]);

// ================================

// Create a Map
const fruits = new Map();

// Set Map Values
fruits.set("apples", 500);
fruits.set("bananas", 300);
fruits.set("oranges", 200);

// ================================

// Change already existing values
fruits.set("apples", 200);

// ================================

// Gets the value of the key.
fruits.get("apples");    // Returns 500

// ================================

// Returns the number of keys in the map.
fruits.size; 

// ================================

// Removes the item from the map
fruits.delete("apples");

// ================================

// Returns (true || false) depending if the key exists
fruits.has("apples");

```

## What is ***this?***

---

The keyword *this* refers to an object. Now, the object that it is refering to is very depend where it is being called. For example, it can be used within an object created by you to reference to internal properties, however, it can also be used to reference elements in the DOM.

* In an object method, *this* refers to the object.
* Alone, *this* refers to the global object.
* In a function, *this* refers to the global object.
* In a function, in strict mode, *this* is undefined.
* In an event, *this* refers to the element that received the event.
* Methods like call(), apply(), and bind() can refer *this* to any object.

```javascript

// ================================

const person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName; // Object referal [object person]
  }
};

// ================================

let x = this; // Global object reference => [object Window]

// ================================

"use strict";
let x = this; // Global object reference => [object Window]

// ================================
 
<button onclick="this.style.display='none'">
  Click to Remove Me! 
</button> // Refers to the HTML element that received the event (Button in this case)

// ================================
// ================================

```

## Classes

---

JavaScript classes are templates for JavaScript Objects. 


```javascript

class Car {
    constructor(name, year) { // Same principle as in C#, C++, and others, it needs a constructor. In Python, this is the initiallizer (__init__) 
        this.name = name; // keyword "this" is referencing the object Car
        this.year = year; // keyword "this" is referencing the object Car
    }

    // A Class, just like an object, can have its own methods. 

    age() {
        let date = new Date();
        return date.getFullYear() - this.year;
    }

    crash() {
        return "Oh no! You crashed!"
    }

    fixed() {
        return "The car is fixed! Pay more attention next time!"
    }



}

```

## Modules

---

Modules are the solution to having your code split into multiple files. This makes it easier to maintain the code base and the whole project in general. Modules rely extensively on *EXPORT* an *IMPORT*.

In-line individually:





```javascript

// ./person.js => In-Line Exports
export const name = "Jesse";
export const age = 40;

// ./person.js => All at the bottom
const name = "Jesse";
const age = 40;

export {name, age};

// Default export allows to demonstrate the export created
// ./message.js
const message = () => {
const name = "Jesse";
const age = 40;
return name + ' is ' + age + 'years old.';
};

export default message;

// =====================

// importing is as simple as exporting. You only need the keyword import
import { name, age } from "./person.js";
import message from "./message.js";







```













