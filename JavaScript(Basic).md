# Complete JavaScript

## Table of Contents
1. [JavaScript Basics](#javascript-basics)
2. [Variables & Data Types](#variables--data-types)
3. [Operators](#operators)
4. [Control Flow](#control-flow)
5. [Functions](#functions)
6. [Objects](#objects)
7. [Arrays](#arrays)
8. [String Methods](#string-methods)
9. [Array Methods](#array-methods)
10. [DOM Manipulation](#dom-manipulation)
11. [Events](#events)
12. [Asynchronous JavaScript](#asynchronous-javascript)
13. [ES6+ Features](#es6-features)
14. [Classes & OOP](#classes--oop)
15. [Error Handling](#error-handling)
16. [Advanced Topics](#advanced-topics)

---

## JAVASCRIPT BASICS

### What is JavaScript?
JavaScript is a programming language that runs in web browsers and makes web pages interactive.

### How to Add JavaScript

#### 1. Inline Script (Not Recommended)
```html
<button onclick="alert('Hello')">Click me</button>
```

#### 2. Internal Script
```html
<head>
  <script>
    console.log('Hello, World!');
  </script>
</head>
```

#### 3. External Script (RECOMMENDED) // add exact before ending of the body tag
```html
<body>
  <div>
    <p></p>
  </div>
  <script src="script.js"></script>
</body>
```

### First Program
```javascript
// This is a comment
/* This is a 
   multi-line comment */

Note : short-cut => ctrl + /

console.log('Hello, World!'); // Output to console
alert('Hello!');               // Show dialog box
document.write('Hello!');      // Write to page
```

### Console Output
```javascript
console.log('General message');
console.warn('Warning message');
console.error('Error message');
console.info('Info message');
console.table([{name: 'Prit', age: 20}]); // Display as table

// Take user Input 

syntax :
variable_name = prompt(`write message here`)

```

---

## VARIABLES & DATA TYPES

### Declaring Variables

#### var (Avoid - Old way)
```javascript
var name = 'Prit';
var age = 20;
```

#### let (Recommended)
```javascript
let name = 'Prit';
let age = 20;
```

#### const (Recommended)
```javascript
const PI = 3.14159;
const name = 'Prit';

// Can't reassign
name = 'Jane'; // Error!

// But can modify contents
const arr = [1, 2, 3];
arr.push(4); // OK - modifying contents
arr = []; // Error - reassigning
```

### Rules for Variable Names
- Start with letter, underscore, or $
- Can contain letters, numbers, underscore, $
- Case sensitive
- Don't use reserved words (if, else, function, etc.)

```javascript
let firstName = 'prit';        // camelCase (recommended)
let first_name = 'prit';       // snake_case
let FirstName = 'prit';        // PascalCase (for classes)
```

### Data Types

#### Primitive Types

**String** - Text
```javascript
let str1 = 'Hello';
let str2 = "World";
let str3 = `Hello ${str2}`; // Template literal
let str4 = `
  Multi-line
  string
`;
```

**Number** - Integer and decimal
```javascript
let int = 42;
let float = 3.14;
let negative = -10;
let scientific = 1.5e2; // 150
let infinity = Infinity;
let notANumber = NaN; // Not a Number
```

**Boolean** - true or false
```javascript
let isActive = true;
let isOpen = false;
let result = 10 > 5; // true
```

**undefined** - Variable declared but not assigned
```javascript
let x;
console.log(x); // undefined
```

**null** - No value (intentional)
```javascript
let empty = null;
```

**Symbol** - Unique identifier
```javascript
const id = Symbol('id');
const id2 = Symbol('id');
console.log(id === id2); // false - each symbol is unique
```

**BigInt** - Very large integers
```javascript
const bigNum = 9007199254740992n;
const bigNum2 = BigInt('9007199254740992');
```

#### Reference Types

**Object** - Collection of key-value pairs
```javascript
let person = {
  name: 'prit',
  age: 20,
  city: 'Rajkot'
};
```

**Array** - Ordered list
```javascript
let colors = ['red', 'green', 'blue'];
let numbers = [1, 2, 3, 4, 5];
```

**Function** - Reusable code block
```javascript
function firstName(name) {
  return `Hello, ${name}!`;
}
```

### Type Checking
```javascript
typeof 'hello'                    // 'string'
typeof 42                         // 'number'
typeof true                       // 'boolean'
typeof undefined                  // 'undefined'
typeof {}                         // 'object'
typeof []                         // 'object'
typeof function(){}               // 'function'
typeof null                       // 'object' (quirk!)

// Better way to check
Array.isArray([1, 2, 3])         // true
Number.isInteger(42)             // true
```

### Type Conversion

**Implicit Conversion**
```javascript
'5' + 3                           // '53' (string concatenation)
'5' - 3                           // 2 (number subtraction)
'5' * '2'                         // 10 (number multiplication)
true + 1                          // 2
```

**Explicit Conversion**
```javascript
// String conversion
String(42)                        // '42'
String(true)                      // 'true'
(42).toString()                   // '42'

// Number conversion
Number('42')                      // 42
Number('3.14')                    // 3.14
Number(true)                      // 1
Number(false)                     // 0
parseInt('42')                    // 42
parseFloat('3.14')                // 3.14

// Boolean conversion
Boolean(1)                        // true
Boolean(0)                        // false
Boolean('')                       // false
Boolean('hello')                  // true
Boolean(null)                     // false
Boolean(undefined)                // false
```

---

## OPERATORS

### Arithmetic Operators
```javascript
10 + 5              // 15 (addition)
10 - 5              // 5 (subtraction)
10 * 5              // 50 (multiplication)
10 / 5              // 2 (division)
10 % 3              // 1 (modulo - remainder)
2 ** 3              // 8 (exponentiation)

// Increment and Decrement
let x = 5;
x++                 // 6 (post-increment)
++x                 // 7 (pre-increment)
x--                 // 6 (post-decrement)
--x                 // 5 (pre-decrement)
```

### Assignment Operators
```javascript
let x = 10;
x += 5              // x = x + 5 (15)
x -= 3              // x = x - 3 (12)
x *= 2              // x = x * 2 (24)
x /= 4              // x = x / 4 (6)
x %= 4              // x = x % 4 (2)
x **= 2             // x = x ** 2 (4)
```

### Comparison Operators
```javascript
10 == '10'          // true (loose equality - type coercion)
10 === '10'         // false (strict equality - no coercion)
10 != '10'          // false (loose inequality)
10 !== '10'         // true (strict inequality)

10 > 5              // true
10 >= 10            // true
5 < 10              // true
5 <= 5              // true
```

### Logical Operators
```javascript
// AND (&&) - all conditions must be true
true && true        // true
true && false       // false

// OR (||) - at least one condition must be true
true || false       // true
false || false      // false

// NOT (!) - negation
!true               // false
!false              // true

// Practical examples
if (age >= 18 && hasLicense) {
  console.log('Can drive');
}

if (weather === 'sunny' || weather === 'cloudy') {
  console.log('Can go outside');
}

if (!isRaining) {
  console.log('It\'s not raining');
}
```

### Ternary Operator
```javascript
// condition ? value_if_true : value_if_false
let status = age >= 18 ? 'Adult' : 'Minor';

let message = score >= 60 
  ? 'Passed' 
  : 'Failed';

// Nested ternary (not recommended)
let grade = score >= 90 ? 'A' : score >= 80 ? 'B' : 'C';
```

### Nullish Coalescing (??)
```javascript
let value = null ?? 'default'; // 'default'
let value = undefined ?? 'default'; // 'default'
let value = 0 ?? 'default'; // 0 (not replaced)
let value = '' ?? 'default'; // '' (not replaced)
```

### Optional Chaining (?.)
```javascript
let person = {
  name: 'prit',
  address: {
    city: 'Rajkot'
  }
};

person.address.city              // 'Rajkot'
person.phone?.number             // undefined (safe)
person.address.zipcode?.value    // undefined (safe)

// Array access
let arr = [1, 2, 3];
arr?.[0]                          // 1
```

---

## CONTROL FLOW

### if Statement
```javascript
if (age >= 18) {
  console.log('You are an adult');
}

if (age >= 18) {
  console.log('You are an adult');
} else {
  console.log('You are a minor');
}

if (score >= 90) {
  console.log('Grade: A');
} else if (score >= 80) {
  console.log('Grade: B');
} else if (score >= 70) {
  console.log('Grade: C');
} else {
  console.log('Grade: F');
}
```

### switch Statement
When Should You Use switch?

✅ Use switch when:

(1) Comparing one variable with many fixed values.
(2) Creating menus.
(3) Handling calculator operators.
(4) Mapping numbers to names (days, months).
(5) Handling user choices in games or applications.

```javascript
let day = 3;
let dayName;

switch (day) {
  case 1:
    dayName = 'Monday';
    break;
  case 2:
    dayName = 'Tuesday';
    break;
  case 3:
    dayName = 'Wednesday';
    break;
  case 4:
    dayName = 'Thursday';
    break;
  case 5:
    dayName = 'Friday';
    break;
  default:
    dayName = 'Weekend';
}

console.log(dayName); // 'Wednesday'

// Switch with multiple cases
let fruit = 'apple';
switch (fruit) {
  case 'apple':
  case 'orange':
  case 'banana':
    console.log('It\'s a fruit');
    break;
  default:
    console.log('Unknown');
}
```

### for Loop

The for loop is used when you know how many times you want to repeat something or when you need the index of an array

```javascript
// syntax :
for (initialization; condition; increment/decrement) {
    // Code
}

// Traditional for loop
for (let i = 0; i < 5; i++) {
  console.log(i); // 0, 1, 2, 3, 4
}

// Loop with array
let colors = ['red', 'green', 'blue'];
for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}

// Backwards loop
for (let i = 5; i > 0; i--) {
  console.log(i); // 5, 4, 3, 2, 1
}
```

### while Loop
```javascript
let i = 0;
while (i < 5) {
  console.log(i); // 0, 1, 2, 3, 4
  i++;
}

// do...while (executes at least once)
let x = 0;
do {
  console.log(x); // 0
  x++;
} while (x < 0);
```

### for...in Loop
Mostly used with objects.
```javascript
syntax :
for (let key in object) {
    // Code
}

let person = { name: 'prit', age: 20, city: 'Rajkot' };

for (let key in person) {
  console.log(key, person[key]);
  // name prit
  // age 20
  // city Rajkot
}
```

### for...of Loop

for...of is used to loop over values of an iterable.

Works with : -> Arrays ,Strings, Maps, Set (Not for plain objects.)


```javascript
syntax:
for (let variable of iterable) {
    // Code
}

let colors = ['red', 'green', 'blue'];

for (let color of colors) {
  console.log(color); // red, green, blue
}

// With strings
for (let char of 'hello') {
  console.log(char); // h, e, l, l, o
}

// With objects (won't work directly)
let person = { name: 'prit', age: 20 };
for (let value of Object.values(person)) {
  console.log(value); // prit, 20
}
```

### break and continue
```javascript
// break - exits loop
for (let i = 0; i < 10; i++) {
  if (i === 5) break;
  console.log(i); // 0, 1, 2, 3, 4
}

// continue - skip iteration
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i); // 0, 1, 3, 4
}
```

---

## FUNCTIONS

### Declaring Functions

#### Function Declaration
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet('prit')); // 'Hello, prit!'

// Hoisting: Can call before declaring
console.log(sayHi()); // 'Hi!'

function sayHi() {
  return 'Hi!';
}
```

#### Function Expression
```javascript
const greet = function(name) {
  return `Hello, ${name}!`;
};

console.log(greet('prit')); // 'Hello, prit!'

// Anonymous function
const add = function(a, b) {
  return a + b;
};

// With name (optional)
const multiply = function multiply(a, b) {
  return a * b;
};
```

#### Arrow Functions
```javascript
// Single parameter, implicit return
const square = x => x * x;

// Multiple parameters
const add = (a, b) => a + b;

// No parameters
const sayHi = () => 'Hi!';

// Multiple lines
const greet = (name) => {
  const message = `Hello, ${name}!`;
  return message;
};

// Arrow functions don't have their own 'this'
const person = {
  name: 'prit',
  greet: function() {
    const inner = () => {
      console.log(this.name); // 'prit' - inherits from parent
    };
    inner();
  }
};
```

### Parameters and Arguments
```javascript
// Default parameters
function greet(name = 'Guest') {
  console.log(`Hello, ${name}`);
}

greet();            // 'Hello, Guest'
greet('prit');      // 'Hello, prit'

// Rest parameters (...)
function sum(...numbers) {
  let total = 0;
  for (let num of numbers) {
    total += num;
  }
  return total;
}

console.log(sum(1, 2, 3, 4)); // 10

// Destructuring parameters
function displayPerson({ name, age }) {
  console.log(name, age);
}

displayPerson({ name: 'prit', age: 20 });

// Destructuring array
function first([a, b, c]) {
  console.log(a); // 1
}

first([1, 2, 3]);
```

### Return Statement
```javascript
function divide(a, b) {
  if (b === 0) {
    return 'Cannot divide by zero';
  }
  return a / b;
}

// Multiple returns
function checkAge(age) {
  if (age < 0) return 'Invalid age';
  if (age < 13) return 'Child';
  if (age < 18) return 'Teen';
  return 'Adult';
}

// No return (returns undefined)
function logMessage(msg) {
  console.log(msg);
}
```

### Scope
```javascript
let global = 'I am global';

function outer() {
  let outerVar = 'I am outer';
  
  function inner() {
    let innerVar = 'I am inner';
    console.log(innerVar);   // 'I am inner' - accessible
    console.log(outerVar);   // 'I am outer' - accessible (closure)
    console.log(global);     // 'I am global' - accessible
  }
  
  inner();
  // console.log(innerVar); // Error! Not accessible
}

outer();
// console.log(outerVar); // Error! Not accessible

// Block scope (let and const)
{
  let blockVar = 'I am block scoped';
  const blockConst = 'Me too';
}
// console.log(blockVar); // Error!

// Function scope (var)
function test() {
  if (true) {
    var functionScoped = 'I am function scoped';
  }
  console.log(functionScoped); // Accessible (not recommended)
}
```

### Closures
A closure is a function that has access to variables from another function's scope.

```javascript
function createCounter() {
  let count = 0;
  
  return function() {
    count++;
    return count;
  };
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3

// Practical example
function createMultiplier(multiplier) {
  return function(number) {
    return number * multiplier;
  };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5));  // 10
console.log(triple(5));  // 15
```

---

## OBJECTS

### Creating Objects
```javascript
// Object literal
let person = {
  name: 'prit',
  age: 20,
  city: 'Rajkot',
  'full-name': 'prit-khanpara'  // Property with hyphen
};

// Using constructor
let person2 = new Object();
person2.name = 'Jane';
person2.age = 25;

// Constructor function
function Person(name, age) {
  this.name = name;
  this.age = age;
}

let person3 = new Person('Yash', 35);
```

### Accessing Properties
```javascript
let person = {
  name: 'Prit',
  age: 20,
  address: {
    street: '123 Main St',
    city: 'RAJKOT'
  }
};

// Dot notation
console.log(person.name);        // 'Prit'
console.log(person.age);         // 20
console.log(person.address.city); // 'RAJKOT'

// Bracket notation
console.log(person['name']);     // 'Prit'
console.log(person['age']);      // 20

// Dynamic property access
let prop = 'name';
console.log(person[prop]);       // 'Prit'

// Optional chaining
console.log(person.address?.zipcode); // undefined (safe)
```

### Adding and Modifying Properties
```javascript
let person = { name: 'Prit' };

// Add property
person.age = 20;
person['city'] = 'RAJKOT';

// Modify property
person.name = 'Jane';

// Dynamic property
let newProp = 'email';
person[newProp] = 'prit@example.com';

console.log(person);
// { name: 'Jane', age: 20, city: 'RAJKOT', email: 'prit@example.com' }
```

### Methods (Functions in Objects)
```javascript
let person = {
  name: 'Prit',
  age: 20,
  greet: function() {
    console.log(`Hello, I am ${this.name}`);
  },
  getAge() {
    return this.age;
  },
  setAge(newAge) {
    this.age = newAge;
  }
};

person.greet();        // 'Hello, I am Prit'
console.log(person.getAge());  // 20
person.setAge(31);
console.log(person.age); // 31
```

### Object Methods

**Object.keys()**
```javascript
let person = { name: 'Prit', age: 20, city: 'RAJKOT' };
console.log(Object.keys(person)); // ['name', 'age', 'city']
```

**Object.values()**
```javascript
console.log(Object.values(person)); // ['Prit', 20, 'RAJKOT']
```

**Object.entries()**
```javascript
console.log(Object.entries(person));
// [['name', 'Prit'], ['age', 20], ['city', 'RAJKOT']]
```

**Object.assign()**
```javascript
let obj1 = { a: 1, b: 2 };
let obj2 = { b: 3, c: 4 };
let merged = Object.assign({}, obj1, obj2);
console.log(merged); // { a: 1, b: 3, c: 4 }
```

**Object.freeze()**
```javascript
let person = { name: 'Prit' };
Object.freeze(person);
person.name = 'Jane'; // Fails silently (or throws error in strict mode)
```

**Object.seal()**
```javascript
let person = { name: 'Prit' };
Object.seal(person);
person.name = 'Jane'; // OK - can modify
person.age = 20;      // Fails - can't add new properties
```

---

## ARRAYS

### Creating Arrays
```javascript
// Array literal
let colors = ['red', 'green', 'blue'];

// Array constructor
let numbers = new Array(1, 2, 3, 4, 5);

// Mixed types
let mixed = [1, 'hello', true, null, undefined, { name: 'Prit' }];

// Array with length
let empty = new Array(5); // 5 empty slots
```

### Accessing Elements
```javascript
let colors = ['red', 'green', 'blue'];

console.log(colors[0]);        // 'red'
console.log(colors[1]);        // 'green'
console.log(colors.length);    // 3
console.log(colors[colors.length - 1]); // 'blue' (last element)
```

### Modifying Arrays
```javascript
let colors = ['red', 'green', 'blue'];

// Change element
colors[1] = 'yellow';

// Add to end
colors[colors.length] = 'purple';

// Add to beginning
colors.unshift('pink');

console.log(colors);
// ['pink', 'red', 'yellow', 'blue', 'purple']
```

---

## STRING METHODS

### String Properties and Methods

**length**
```javascript
let str = 'Hello, World!';
console.log(str.length); // 13
```

**charAt() and charCodeAt()**
```javascript
let str = 'Hello';
console.log(str.charAt(0));      // 'H'
console.log(str.charCodeAt(0));  // 72 (ASCII value)
console.log(str[0]);             // 'H' (bracket notation)
```

**indexOf() and lastIndexOf()**
```javascript
let str = 'Hello, World!';
console.log(str.indexOf('o'));       // 4
console.log(str.lastIndexOf('o'));   // 8
console.log(str.indexOf('World'));   // 7
console.log(str.indexOf('xyz'));     // -1 (not found)
```

**includes()**
```javascript
let str = 'Hello, World!';
console.log(str.includes('World'));  // true
console.log(str.includes('xyz'));    // false
```

**startsWith() and endsWith()**
```javascript
let str = 'Hello, World!';
console.log(str.startsWith('Hello'));   // true
console.log(str.endsWith('!'));         // true
console.log(str.endsWith('World'));     // false
```

**slice()**
```javascript
let str = 'Hello, World!';
console.log(str.slice(0, 5));        // 'Hello'
console.log(str.slice(7));           // 'World!'
console.log(str.slice(-6));          // 'World!'
console.log(str.slice(-6, -1));      // 'World'
```

**substring()**
```javascript
let str = 'Hello, World!';
console.log(str.substring(0, 5));    // 'Hello'
console.log(str.substring(7));       // 'World!'
// Note: negative values are treated as 0
```

**substr()** (deprecated)
```javascript
let str = 'Hello, World!';
console.log(str.substr(0, 5));       // 'Hello'
console.log(str.substr(7, 5));       // 'World'
```

**toLowerCase() and toUpperCase()**
```javascript
let str = 'Hello, World!';
console.log(str.toLowerCase());      // 'hello, world!'
console.log(str.toUpperCase());      // 'HELLO, WORLD!'
```

**trim(), trimStart(), trimEnd()**
```javascript
let str = '  Hello, World!  ';
console.log(str.trim());             // 'Hello, World!'
console.log(str.trimStart());        // 'Hello, World!  '
console.log(str.trimEnd());          // '  Hello, World!'
```

**split()**
```javascript
let str = 'red,green,blue';
console.log(str.split(','));         // ['red', 'green', 'blue']

let words = 'Hello World';
console.log(words.split(' '));       // ['Hello', 'World']

let chars = 'Hello';
console.log(chars.split(''));        // ['H', 'e', 'l', 'l', 'o']
```

**replace() and replaceAll()**
```javascript
let str = 'Hello, Hello, Hello!';
console.log(str.replace('Hello', 'Hi'));      // 'Hi, Hello, Hello!'
console.log(str.replaceAll('Hello', 'Hi'));   // 'Hi, Hi, Hi!'
```

**repeat()**
```javascript
let str = 'abc';
console.log(str.repeat(3));          // 'abcabcabc'
```

**padStart() and padEnd()**
```javascript
let str = '5';
console.log(str.padStart(3, '0'));   // '005'
console.log(str.padEnd(3, '0'));     // '500'
```

**concat()**
```javascript
let str1 = 'Hello';
let str2 = 'World';
console.log(str1.concat(', ', str2, '!')); // 'Hello, World!'
console.log(str1 + ' ' + str2);            // Alternative
```

**match() and search()**
```javascript
let str = 'The year is 2024';
console.log(str.match(/\d+/));       // ['2024']
console.log(str.search(/\d+/));      // 12 (index)
```

---

## ARRAY METHODS

### Modifying Arrays

**push()** - Add to end
```javascript
let arr = [1, 2, 3];
arr.push(4);
arr.push(5, 6);
console.log(arr); // [1, 2, 3, 4, 5, 6]
```

**pop()** - Remove from end
```javascript
let arr = [1, 2, 3];
let removed = arr.pop();
console.log(removed); // 3
console.log(arr);     // [1, 2]
```

**unshift()** - Add to beginning
```javascript
let arr = [2, 3];
arr.unshift(1);
console.log(arr); // [1, 2, 3]
```

**shift()** - Remove from beginning
```javascript
let arr = [1, 2, 3];
let removed = arr.shift();
console.log(removed); // 1
console.log(arr);     // [2, 3]
```

**splice()** - Add/remove at any position
```javascript
let arr = [1, 2, 3, 4, 5];
arr.splice(2, 1);        // Remove 1 element at index 2
console.log(arr);        // [1, 2, 4, 5]

arr.splice(2, 0, 3);     // Insert at index 2
console.log(arr);        // [1, 2, 3, 4, 5]

arr.splice(1, 2, 'a', 'b'); // Remove 2, insert 2
console.log(arr);        // [1, 'a', 'b', 4, 5]
```

### Searching Arrays

**indexOf() and lastIndexOf()**
```javascript
let arr = [1, 2, 3, 2, 1];
console.log(arr.indexOf(2));        // 1
console.log(arr.lastIndexOf(2));    // 3
console.log(arr.indexOf(5));        // -1
```

**includes()**
```javascript
let arr = [1, 2, 3, 4, 5];
console.log(arr.includes(3));       // true
console.log(arr.includes(10));      // false
```

**find()** - Find first element matching condition
```javascript
let arr = [1, 2, 3, 4, 5];
let result = arr.find(x => x > 3);
console.log(result); // 4

let users = [
  { id: 1, name: 'Prit' },
  { id: 2, name: 'Jane' }
];
let user = users.find(u => u.id === 2);
console.log(user); // { id: 2, name: 'Jane' }
```

**findIndex()** - Find index of element
```javascript
let arr = [1, 2, 3, 4, 5];
let index = arr.findIndex(x => x > 3);
console.log(index); // 3
```

### Iterating Arrays

**forEach()**
```javascript
let arr = [1, 2, 3, 4, 5];
arr.forEach((element, index, array) => {
  console.log(element);
});
// 1, 2, 3, 4, 5
```

**map()** - Transform array
```javascript
let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(x => x * 2);
console.log(doubled); // [2, 4, 6, 8, 10]

let users = [
  { name: 'Prit', age: 20 },
  { name: 'Jane', age: 25 }
];
let names = users.map(u => u.name);
console.log(names); // ['Prit', 'Jane']
```

**filter()** - Filter elements
```javascript
let numbers = [1, 2, 3, 4, 5];
let even = numbers.filter(x => x % 2 === 0);
console.log(even); // [2, 4]

let users = [
  { name: 'Prit', age: 20 },
  { name: 'Jane', age: 25 },
  { name: 'Yash', age: 17 }
];
let adults = users.filter(u => u.age >= 18);
console.log(adults); // [Prit, Jane]
```

**reduce()** - Combine array into single value
```javascript
let numbers = [1, 2, 3, 4, 5];
let sum = numbers.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 15

// Without initial value
let product = numbers.reduce((acc, curr) => acc * curr);
console.log(product); // 120

// Counting occurrences
let arr = ['a', 'b', 'a', 'c', 'b', 'a'];
let counts = arr.reduce((acc, curr) => {
  acc[curr] = (acc[curr] || 0) + 1;
  return acc;
}, {});
console.log(counts); // { a: 3, b: 2, c: 1 }
```

**sort()**
```javascript
let numbers = [3, 1, 4, 1, 5, 9, 2, 6];
numbers.sort((a, b) => a - b);
console.log(numbers); // [1, 1, 2, 3, 4, 5, 6, 9]

let words = ['banana', 'apple', 'cherry'];
words.sort();
console.log(words); // ['apple', 'banana', 'cherry']

// Descending
numbers.sort((a, b) => b - a);
console.log(numbers); // [9, 6, 5, 4, 3, 2, 1, 1]
```

**reverse()**
```javascript
let arr = [1, 2, 3, 4, 5];
arr.reverse();
console.log(arr); // [5, 4, 3, 2, 1]
```

### Combining Arrays

**concat()**
```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];
let combined = arr1.concat(arr2);
console.log(combined); // [1, 2, 3, 4, 5, 6]

let all = arr1.concat(arr2, [7, 8], 9);
console.log(all); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**Spread operator (...)**
```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];
let combined = [...arr1, ...arr2];
console.log(combined); // [1, 2, 3, 4, 5, 6]

let copy = [...arr1];
console.log(copy); // [1, 2, 3]
```

**join()**
```javascript
let colors = ['red', 'green', 'blue'];
console.log(colors.join(', '));    // 'red, green, blue'
console.log(colors.join('-'));     // 'red-green-blue'
console.log(colors.join(''));      // 'redgreenblue'
```

---

## DOM MANIPULATION

### Selecting Elements

**getElementById()**
```javascript
let element = document.getElementById('myId');
console.log(element);
```

**querySelector()**
```javascript
let element = document.querySelector('.className');
let element = document.querySelector('#myId');
let element = document.querySelector('p');
let element = document.querySelector('div.container > p');
```

**querySelectorAll()**
```javascript
let elements = document.querySelectorAll('.className');
let paragraphs = document.querySelectorAll('p');

elements.forEach(el => {
  console.log(el);
});
```

**getElementsByClassName()**
```javascript
let elements = document.getElementsByClassName('myClass');
console.log(elements); // HTMLCollection (live)
```

**getElementsByTagName()**
```javascript
let paragraphs = document.getElementsByTagName('p');
console.log(paragraphs); // HTMLCollection (live)
```

### Modifying Content

**innerHTML** - Set HTML content
```javascript
let element = document.getElementById('myDiv');
element.innerHTML = '<h1>Hello</h1>';
element.innerHTML += '<p>World</p>';
```

**textContent** - Set text content
```javascript
let element = document.getElementById('myDiv');
element.textContent = 'Hello, World!';
```

**innerText** - Set visible text
```javascript
let element = document.getElementById('myDiv');
element.innerText = 'Hello, World!';
```

### Modifying Attributes

**setAttribute()**
```javascript
let link = document.getElementById('myLink');
link.setAttribute('href', 'https://example.com');
link.setAttribute('target', '_blank');
```

**getAttribute()**
```javascript
let href = link.getAttribute('href');
console.log(href); // 'https://example.com'
```

**removeAttribute()**
```javascript
link.removeAttribute('target');
```

**Direct property access**
```javascript
let img = document.getElementById('myImg');
img.src = 'image.jpg';
img.alt = 'My Image';
img.width = 300;
img.height = 200;
```

### Modifying Styles

**style property**
```javascript
let element = document.getElementById('myDiv');
element.style.backgroundColor = 'red';
element.style.color = 'white';
element.style.fontSize = '20px';
element.style.padding = '10px';
element.style.display = 'none'; // Hide
element.style.display = 'block'; // Show
```

**classList**
```javascript
let element = document.getElementById('myDiv');

// Add class
element.classList.add('active');
element.classList.add('class1', 'class2');

// Remove class
element.classList.remove('active');

// Toggle class
element.classList.toggle('active');

// Check if has class
if (element.classList.contains('active')) {
  console.log('Has active class');
}

// Replace class
element.classList.replace('old', 'new');
```

### Creating and Removing Elements

**createElement()**
```javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'Hello';
newDiv.className = 'container';
newDiv.id = 'myDiv';

document.body.appendChild(newDiv);
```

**appendChild()**
```javascript
let parent = document.getElementById('container');
let child = document.createElement('p');
child.textContent = 'New paragraph';
parent.appendChild(child);
```

**insertBefore()**
```javascript
let parent = document.getElementById('container');
let newElement = document.createElement('p');
newElement.textContent = 'First paragraph';

let firstChild = parent.firstChild;
parent.insertBefore(newElement, firstChild);
```

**removeChild()**
```javascript
let parent = document.getElementById('container');
let child = parent.querySelector('p');
parent.removeChild(child);
```

**remove()**
```javascript
let element = document.getElementById('myDiv');
element.remove(); // Remove itself
```

### Element Properties

```javascript
let element = document.getElementById('myDiv');

// Navigation
element.parentElement      // Parent node
element.childNodes         // All child nodes
element.children           // Element children only
element.firstChild         // First child
element.lastChild          // Last child
element.nextSibling        // Next sibling
element.previousSibling    // Previous sibling

// Classes
element.className          // Get/set all classes

// HTML
element.innerHTML          // Get/set HTML
element.textContent        // Get/set text

// Visibility
element.hidden = true;     // Hide element
element.hidden = false;    // Show element
```

---

## EVENTS

### Adding Event Listeners

**addEventListener()**
```javascript
let button = document.getElementById('myButton');

button.addEventListener('click', function(event) {
  console.log('Button clicked!');
});

// Arrow function
button.addEventListener('click', (event) => {
  console.log('Button clicked!');
});
```

**Inline HTML**
```html
<button onclick="myFunction()">Click me</button>
```

```javascript
function myFunction() {
  console.log('Button clicked!');
}
```

### Common Events

**Mouse Events**
```javascript
element.addEventListener('click', (e) => {
  console.log('Clicked');
});

element.addEventListener('dblclick', (e) => {
  console.log('Double clicked');
});

element.addEventListener('mouseenter', (e) => {
  console.log('Mouse entered');
});

element.addEventListener('mouseleave', (e) => {
  console.log('Mouse left');
});

element.addEventListener('mousemove', (e) => {
  console.log(e.clientX, e.clientY);
});
```

**Keyboard Events**
```javascript
document.addEventListener('keydown', (e) => {
  console.log('Key pressed:', e.key);
  console.log('Key code:', e.code);
});

document.addEventListener('keyup', (e) => {
  console.log('Key released:', e.key);
});

input.addEventListener('keypress', (e) => {
  console.log('Key pressed:', e.key);
});
```

**Form Events**
```javascript
form.addEventListener('submit', (e) => {
  e.preventDefault(); // Prevent form submission
  console.log('Form submitted');
});

input.addEventListener('change', (e) => {
  console.log('Input changed:', e.target.value);
});

input.addEventListener('input', (e) => {
  console.log('Input value:', e.target.value);
});

input.addEventListener('focus', (e) => {
  console.log('Input focused');
});

input.addEventListener('blur', (e) => {
  console.log('Input blurred');
});
```

**Window Events**
```javascript
window.addEventListener('load', (e) => {
  console.log('Page loaded');
});

window.addEventListener('resize', (e) => {
  console.log('Window resized');
  console.log(window.innerWidth, window.innerHeight);
});

window.addEventListener('scroll', (e) => {
  console.log('Scrolled');
});
```

### Event Object
```javascript
element.addEventListener('click', (event) => {
  console.log(event.type);        // 'click'
  console.log(event.target);      // Element that triggered event
  console.log(event.currentTarget); // Element with listener
  console.log(event.clientX);     // Mouse X coordinate
  console.log(event.clientY);     // Mouse Y coordinate
  console.log(event.key);         // Key pressed
  console.log(event.keyCode);     // Key code
  
  event.preventDefault();         // Prevent default action
  event.stopPropagation();        // Stop event bubbling
});
```

### Event Delegation
```javascript
// Instead of adding listener to each item:
let items = document.querySelectorAll('li');
items.forEach(item => {
  item.addEventListener('click', () => {
    console.log('Item clicked');
  });
});

// Use event delegation on parent:
let list = document.getElementById('myList');
list.addEventListener('click', (e) => {
  if (e.target.tagName === 'LI') {
    console.log('Item clicked:', e.target.textContent);
  }
});
```

---

## ASYNCHRONOUS JAVASCRIPT

### setTimeout and setInterval

**setTimeout()** - Run code after delay
```javascript
setTimeout(() => {
  console.log('Runs after 2 seconds');
}, 2000);

let timeoutId = setTimeout(() => {
  console.log('This will be cancelled');
}, 3000);

clearTimeout(timeoutId); // Cancel timeout
```

**setInterval()** - Run code repeatedly
```javascript
let counter = 0;
let intervalId = setInterval(() => {
  counter++;
  console.log('Counter:', counter);
  
  if (counter === 5) {
    clearInterval(intervalId); // Stop interval
  }
}, 1000);
```

### Callbacks
```javascript
function fetchData(callback) {
  setTimeout(() => {
    let data = { name: 'Prit', age: 20 };
    callback(data);
  }, 2000);
}

fetchData((data) => {
  console.log('Data received:', data);
});

// Callback hell (avoid)
function step1(callback) {
  setTimeout(() => {
    console.log('Step 1');
    callback();
  }, 1000);
}

function step2(callback) {
  setTimeout(() => {
    console.log('Step 2');
    callback();
  }, 1000);
}

step1(() => {
  step2(() => {
    console.log('Done');
  });
});
```

### Promises
```javascript
// Creating a promise
let promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    let success = true;
    if (success) {
      resolve('Success!');
    } else {
      reject('Failed!');
    }
  }, 2000);
});

// Using promise
promise
  .then((result) => {
    console.log('Result:', result);
  })
  .catch((error) => {
    console.log('Error:', error);
  })
  .finally(() => {
    console.log('Done');
  });
```

**Promise Methods**
```javascript
// Promise.all - Wait for all
Promise.all([promise1, promise2, promise3])
  .then((results) => {
    console.log('All promises resolved:', results);
  })
  .catch((error) => {
    console.log('One or more promises rejected:', error);
  });

// Promise.race - First to settle
Promise.race([promise1, promise2])
  .then((result) => {
    console.log('First promise settled:', result);
  });

// Promise.any - First to resolve
Promise.any([promise1, promise2])
  .then((result) => {
    console.log('First promise resolved:', result);
  });

// Promise.allSettled - All settle
Promise.allSettled([promise1, promise2])
  .then((results) => {
    console.log('All settled:', results);
  });
```

### async/await
```javascript
// Define async function
async function getData() {
  return 'Data';
}

// Call async function
getData().then((data) => {
  console.log(data);
});

// Using await
async function fetchUserData() {
  try {
    let response = await fetch('https://api.example.com/user');
    let data = await response.json();
    console.log('User:', data);
  } catch (error) {
    console.log('Error:', error);
  } finally {
    console.log('Request completed');
  }
}

fetchUserData();
```

**Practical Example**
```javascript
async function getMultipleUsers() {
  try {
    let user1 = await fetch('https://api.example.com/user/1').then(r => r.json());
    let user2 = await fetch('https://api.example.com/user/2').then(r => r.json());
    
    console.log('Users:', user1, user2);
  } catch (error) {
    console.log('Error:', error);
  }
}

// Parallel requests
async function getMultipleUsersParallel() {
  try {
    let [user1, user2] = await Promise.all([
      fetch('https://api.example.com/user/1').then(r => r.json()),
      fetch('https://api.example.com/user/2').then(r => r.json())
    ]);
    
    console.log('Users:', user1, user2);
  } catch (error) {
    console.log('Error:', error);
  }
}
```

---

## ES6 FEATURES

### let and const
```javascript
// var (avoid)
var x = 5;
var x = 10; // Can redeclare

// let (block scope)
let y = 5;
// let y = 10; // Error - can't redeclare
y = 10;        // OK - can reassign

// const (block scope, can't reassign)
const z = 5;
// z = 10; // Error - can't reassign

const obj = { name: 'Prit' };
obj.name = 'Jane'; // OK - modifying contents
// obj = {}; // Error - can't reassign
```

### Template Literals
```javascript
let name = 'Prit';
let age = 20;

// String concatenation (old)
let message = 'My name is ' + name + ' and I am ' + age + ' years old.';

// Template literal (new)
let message = `My name is ${name} and I am ${age} years old.`;

// Multi-line
let html = `
  <div>
    <h1>${name}</h1>
    <p>Age: ${age}</p>
  </div>
`;

// Expressions
console.log(`5 + 3 = ${5 + 3}`);
console.log(`${age > 18 ? 'Adult' : 'Minor'}`);
```

### Destructuring

**Array Destructuring**
```javascript
// Without destructuring
let arr = [1, 2, 3, 4, 5];
let first = arr[0];
let second = arr[1];

// With destructuring
let [first, second] = [1, 2, 3, 4, 5];
console.log(first, second); // 1, 2

// Skip elements
let [a, , c] = [1, 2, 3];
console.log(a, c); // 1, 3

// Rest elements
let [head, ...tail] = [1, 2, 3, 4, 5];
console.log(head); // 1
console.log(tail); // [2, 3, 4, 5]

// Swap variables
let x = 5, y = 10;
[x, y] = [y, x];
console.log(x, y); // 10, 5
```

**Object Destructuring**
```javascript
let person = { name: 'Prit', age: 20, city: 'RAJKOT' };

// Without destructuring
let name = person.name;
let age = person.age;

// With destructuring
let { name, age } = person;
console.log(name, age); // Prit, 20

// Rename variables
let { name: fullName, age: years } = person;
console.log(fullName, years); // Prit, 20

// Default values
let { name, job = 'Unknown' } = person;
console.log(job); // 'Unknown'

// Nested destructuring
let user = {
  name: 'Prit',
  address: {
    city: 'RAJKOT',
    zip: '10001'
  }
};

let { address: { city } } = user;
console.log(city); // 'RAJKOT'

// Rest properties
let { name, ...rest } = person;
console.log(rest); // { age: 20, city: 'RAJKOT' }
```

### Spread Operator (...)

**Array Spread**
```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let combined = [...arr1, ...arr2];
console.log(combined); // [1, 2, 3, 4, 5, 6]

let copy = [...arr1];
console.log(copy); // [1, 2, 3]

let withNew = [0, ...arr1, 4];
console.log(withNew); // [0, 1, 2, 3, 4]
```

**Object Spread**
```javascript
let obj1 = { a: 1, b: 2 };
let obj2 = { c: 3, d: 4 };

let merged = { ...obj1, ...obj2 };
console.log(merged); // { a: 1, b: 2, c: 3, d: 4 }

let copy = { ...obj1 };
console.log(copy); // { a: 1, b: 2 }

let updated = { ...obj1, b: 99 };
console.log(updated); // { a: 1, b: 99 }
```

**Function Spread**
```javascript
let numbers = [1, 2, 3, 4, 5];
console.log(Math.max(...numbers)); // 5

function sum(a, b, c) {
  return a + b + c;
}

console.log(sum(...[1, 2, 3])); // 6
```

### Default Parameters
```javascript
function greet(name = 'Guest', greeting = 'Hello') {
  console.log(`${greeting}, ${name}!`);
}

greet();                 // 'Hello, Guest!'
greet('Prit');           // 'Hello, Prit!'
greet('Prit', 'Hi');     // 'Hi, Prit!'
```

### for...of Loop
```javascript
let colors = ['red', 'green', 'blue'];

for (let color of colors) {
  console.log(color);
}

// With index
for (let [index, color] of colors.entries()) {
  console.log(index, color);
}
```

---

## CLASSES & OOP

### Class Syntax
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, I am ${this.name}`);
  }

  getAge() {
    return this.age;
  }
}

let prit = new Person('Prit', 20);
prit.greet();           // 'Hello, I am Prit'
console.log(prit.getAge()); // 20
```

### Constructor
```javascript
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  getArea() {
    return this.width * this.height;
  }
}

let rect = new Rectangle(10, 5);
console.log(rect.getArea()); // 50
```

### Inheritance
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  speak() {
    console.log(`${this.name} barks`);
  }
}

let dog = new Dog('Rex');
dog.speak(); // 'Rex barks'
```

**super keyword**
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a sound`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);    // Call parent constructor
    this.breed = breed;
  }

  speak() {
    super.speak();  // Call parent method
    console.log(`${this.name} barks`);
  }
}

let dog = new Dog('Rex', 'Labrador');
dog.speak();
// 'Rex makes a sound'
// 'Rex barks'
```

### Static Methods
```javascript
class MathUtil {
  static add(a, b) {
    return a + b;
  }

  static multiply(a, b) {
    return a * b;
  }
}

console.log(MathUtil.add(5, 3));      // 8
console.log(MathUtil.multiply(5, 3)); // 15

// Can't call static methods on instances
let util = new MathUtil();
// util.add(5, 3); // Error
```

### Getters and Setters
```javascript
class Circle {
  constructor(radius) {
    this._radius = radius;
  }

  get radius() {
    return this._radius;
  }

  set radius(value) {
    if (value <= 0) {
      throw new Error('Radius must be positive');
    }
    this._radius = value;
  }

  get area() {
    return Math.PI * this._radius ** 2;
  }
}

let circle = new Circle(5);
console.log(circle.radius);  // 5
console.log(circle.area);    // 78.54...

circle.radius = 10;
console.log(circle.radius);  // 10
```

---

## ERROR HANDLING

### try...catch...finally
```javascript
try {
  let result = riskyFunction();
  console.log(result);
} catch (error) {
  console.log('Error caught:', error.message);
  console.log('Error type:', error.name);
} finally {
  console.log('Cleanup code');
}
```

### Throwing Errors
```javascript
function divide(a, b) {
  if (b === 0) {
    throw new Error('Cannot divide by zero');
  }
  return a / b;
}

try {
  console.log(divide(10, 0));
} catch (error) {
  console.log('Error:', error.message);
}
```

### Error Types
```javascript
// SyntaxError - Malformed code
// ReferenceError - Undefined variable
try {
  console.log(nonExistent);
} catch (error) {
  console.log(error instanceof ReferenceError); // true
}

// TypeError - Wrong type
try {
  let obj = null;
  obj.property; // TypeError: Cannot read property 'property' of null
} catch (error) {
  console.log(error instanceof TypeError); // true
}

// Custom error
class ValidationError extends Error {
  constructor(message) {
    super(message);
    this.name = 'ValidationError';
  }
}

try {
  throw new ValidationError('Invalid input');
} catch (error) {
  console.log(error.name);    // 'ValidationError'
  console.log(error.message); // 'Invalid input'
}
```

---

## ADVANCED TOPICS

### Closures
```javascript
function createCounter() {
  let count = 0;
  
  return {
    increment: function() {
      count++;
      return count;
    },
    decrement: function() {
      count--;
      return count;
    },
    getCount: function() {
      return count;
    }
  };
}

let counter = createCounter();
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.decrement()); // 1
console.log(counter.getCount());  // 1
```

### this Keyword
```javascript
// Regular function - this refers to window/undefined
function greet() {
  console.log(this);
}
greet(); // window (in browser) or undefined (strict mode)

// Object method - this refers to object
let person = {
  name: 'Prit',
  greet: function() {
    console.log(this.name);
  }
};
person.greet(); // 'Prit'

// Arrow function - inherits this from parent scope
let person = {
  name: 'Prit',
  greet: () => {
    console.log(this); // window (not person)
  }
};

// Constructor - this refers to new instance
function Person(name) {
  this.name = name;
}
let prit = new Person('Prit');
console.log(prit.name); // 'Prit'
```

### call(), apply(), and bind()
```javascript
let person1 = { name: 'Prit' };
let person2 = { name: 'Jane' };

function greet(greeting, punctuation) {
  console.log(`${greeting}, ${this.name}${punctuation}`);
}

// call - call function with specific this and arguments
greet.call(person1, 'Hello', '!');  // 'Hello, Prit!'
greet.call(person2, 'Hi', '?');     // 'Hi, Jane?'

// apply - like call but arguments as array
greet.apply(person1, ['Hello', '!']); // 'Hello, Prit!'

// bind - return new function with specific this
let greetPrit = greet.bind(person1);
greetPrit('Hello', '!'); // 'Hello, Prit!'

// Practical example
function sum(a, b) {
  return a + b;
}
let add5 = sum.bind(null, 5);
console.log(add5(3)); // 8
```

### Prototypes and Prototype Chain
```javascript
// Every object has a prototype
let obj = {};
console.log(obj.__proto__);    // Object.prototype
console.log(Object.getPrototypeOf(obj)); // Object.prototype

// Constructor function
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(this.name + ' makes a sound');
};

let dog = new Animal('Dog');
dog.speak(); // 'Dog makes a sound'

// Prototype chain
console.log(dog.hasOwnProperty('name'));     // true
console.log(dog.hasOwnProperty('speak'));    // false (inherited)
console.log('speak' in dog);                 // true

// Check prototype
console.log(dog instanceof Animal);          // true
```

### Higher Order Functions
```javascript
// Function that returns another function
function multiplyBy(multiplier) {
  return function(number) {
    return number * multiplier;
  };
}

let double = multiplyBy(2);
let triple = multiplyBy(3);

console.log(double(5)); // 10
console.log(triple(5)); // 15

// Function that takes another function
function executeOperation(a, b, operation) {
  return operation(a, b);
}

let add = (a, b) => a + b;
let subtract = (a, b) => a - b;

console.log(executeOperation(10, 5, add));      // 15
console.log(executeOperation(10, 5, subtract)); // 5
```

### Memoization
```javascript
function createMemoizer(fn) {
  const cache = {};
  
  return function(...args) {
    const key = JSON.stringify(args);
    
    if (key in cache) {
      console.log('From cache');
      return cache[key];
    }
    
    console.log('Computing');
    const result = fn(...args);
    cache[key] = result;
    return result;
  };
}

function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

let memoFib = createMemoizer(fibonacci);
console.log(memoFib(10)); // Computing
console.log(memoFib(10)); // From cache
```

### Currying
```javascript
// Regular function
function add(a, b, c) {
  return a + b + c;
}

// Curried function
function curriedAdd(a) {
  return function(b) {
    return function(c) {
      return a + b + c;
    };
  };
}

console.log(curriedAdd(1)(2)(3)); // 6

// Shorthand with arrow functions
const curriedAdd2 = a => b => c => a + b + c;
console.log(curriedAdd2(1)(2)(3)); // 6

// Currying function
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn(...args);
    } else {
      return function(...nextArgs) {
        return curried(...args, ...nextArgs);
      };
    }
  };
}
```

### Regular Expressions
```javascript
// Creating regex
let regex1 = /pattern/;
let regex2 = /pattern/gi; // g: global, i: case-insensitive

let regex = new RegExp('pattern', 'gi');

// Test - returns boolean
console.log(/hello/i.test('Hello World')); // true

// Match - returns matches
let str = 'cat, bat, rat';
console.log(str.match(/[cbr]at/g)); // ['cat', 'bat', 'rat']

// Replace
console.log(str.replace(/at/, 'ot'));   // 'cot, bat, rat'
console.log(str.replace(/at/g, 'ot'));  // 'cot, bot, rot'

// Patterns
/^hello/          // Starts with 'hello'
/world$/          // Ends with 'world'
/h.llo/           // . matches any char
/hel+o/           // + one or more
/hel*o/           // * zero or more
/hel?o/           // ? zero or one
/[abc]/           // a, b, or c
/[a-z]/           // a to z
/[0-9]/           // digits
/\d/              // digit
/\w/              // word character
/\s/              // whitespace
```

---

## PRACTICAL EXAMPLES

### Todo Application
```javascript
let todos = [];

function addTodo(text) {
  const todo = {
    id: Date.now(),
    text: text,
    completed: false,
    createdAt: new Date()
  };
  todos.push(todo);
  return todo;
}

function deleteTodo(id) {
  todos = todos.filter(todo => todo.id !== id);
}

function toggleTodo(id) {
  let todo = todos.find(todo => todo.id === id);
  if (todo) {
    todo.completed = !todo.completed;
  }
}

function getTodos() {
  return todos;
}

function getCompletedTodos() {
  return todos.filter(todo => todo.completed);
}

function getActiveTodos() {
  return todos.filter(todo => !todo.completed);
}

function clearCompleted() {
  todos = todos.filter(todo => !todo.completed);
}

// Usage
addTodo('Learn JavaScript');
addTodo('Build a project');
addTodo('Practice daily');

console.log(getTodos());
toggleTodo(todos[0].id);
console.log(getCompletedTodos());
clearCompleted();
```

### Fetch API
```javascript
// GET request
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log('Error:', error));

// POST request
fetch('https://api.example.com/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ name: 'Prit', age: 20 })
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.log('Error:', error));

// With async/await
async function getData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.log('Error:', error);
  }
}

getData();
```

### Form Validation
```javascript
const form = document.getElementById('myForm');
const errors = {};

function validateForm(e) {
  e.preventDefault();
  errors = {};

  const name = form.name.value.trim();
  const email = form.email.value.trim();
  const password = form.password.value;

  if (!name) {
    errors.name = 'Name is required';
  } else if (name.length < 3) {
    errors.name = 'Name must be at least 3 characters';
  }

  if (!email) {
    errors.email = 'Email is required';
  } else if (!email.includes('@')) {
    errors.email = 'Email must be valid';
  }

  if (!password) {
    errors.password = 'Password is required';
  } else if (password.length < 6) {
    errors.password = 'Password must be at least 6 characters';
  }

  if (Object.keys(errors).length === 0) {
    console.log('Form is valid!');
    // Submit form
  } else {
    displayErrors();
  }
}

function displayErrors() {
  for (let field in errors) {
    let errorElement = document.getElementById(field + 'Error');
    if (errorElement) {
      errorElement.textContent = errors[field];
    }
  }
}

form.addEventListener('submit', validateForm);
```

---

## JAVASCRIPT QUICK REFERENCE

```javascript
// Variables
let x = 5;
const y = 10;

// Data Types
typeof x;
Array.isArray([]);

// Operators
x + y;
x == y;
x === y;
x > y;
x && y;

// Control Flow
if (x > 5) {}
switch (x) { case 1: break; }
for (let i = 0; i < 5; i++) {}
while (x > 0) {}

// Functions
function greet(name) { return 'Hi ' + name; }
const arrow = (x) => x * 2;

// Objects
let obj = { name: 'Prit', age: 20 };
obj.name;
obj['age'];

// Arrays
let arr = [1, 2, 3];
arr.push(4);
arr.map(x => x * 2);
arr.filter(x => x > 2);

// Strings
'hello'.length;
'hello'.toUpperCase();
'hello'.includes('l');
'a,b,c'.split(',');

// Dates
new Date();
Date.now();

// Math
Math.max(1, 2, 3);
Math.random();
Math.round(3.7);

// JSON
JSON.stringify(obj);
JSON.parse(jsonString);

// DOM
document.getElementById('id');
document.querySelector('.class');
element.addEventListener('click', () => {});
```

---

## LEARNING TIPS

1. **Practice regularly** - Code every day
2. **Read error messages** - They tell you what's wrong
3. **Use console.log()** - Debug your code
4. **Build projects** - Learn by doing
5. **Understand before memorizing** - Know why things work
6. **Read other people's code** - Learn patterns
7. **Use DevTools** - Inspect and debug in browser
8. **Learn incrementally** - Master basics before advanced
9. **Practice algorithms** - Improve problem solving
10. **Stay updated** - JavaScript keeps evolving

---

## ADDITIONAL RESOURCES

- **MDN Web Docs**: https://developer.mozilla.org/en-US/docs/Web/JavaScript
- **JavaScript.info**: https://javascript.info
- **Eloquent JavaScript**: https://eloquentjavascript.net
- **CodeWars**: https://www.codewars.com (Practice coding)
- **JavaScript Playground**: https://jsfiddle.net

---

This guide covers JavaScript from beginner to advanced level. Practice each concept and build projects to solidify your understanding. Good luck!
