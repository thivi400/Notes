# 🧾 JavaScript Basics — Notes

### Commenting  

```javascript
// Single-line comment
/* Multi-line comment */
```
</br>

## There are 8 main Data Types in JavaScript 

<pre>
String    → text
Number    → integers or decimals
Boolean   → true / false
Null      → intentional “nothing” value 
Undefined → variable declared but not assigned
Symbol    → unique identifier
BigInt    → large numbers beyond Number limit
Object    → collection of key-value pairs
</pre>
Example:  

```js
const name = 'Pubs';          // String
const age = 23;               // Number
const rating = 4.5;           // Number
const isCool = true;          // Boolean
const x = null;               // Null
const y = undefined;          // Undefined
let z;                        // Undefined
```

```js
console.log(typeof(rating)); 
```
Output:
```console
number
```
</br>

## 1. Template Strings -- Used for string concatenation  

```js
const welcome = `Hello ${name} of age ${age}`;
console.log(welcome);
```
⚠️ Use backticks " ` " not single quotes ( ' ).  
</br>

## 2. String Methods  

```js
const s = 'Hello World';
console.log(s.length);             // 11
console.log(s.substring(0, 7));    // 'Hello W'
console.log(s.substring(0, 5).toUpperCase()); // 'HELLO'
```

Splitting Strings:  

```js
console.log(s.split(''));   // ['H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd']
console.log(s.split(' '));  // ['Hello', 'World']

const names = 'Thivi, Pubs, Ananthy';
console.log(names.split(', ')); // ['Thivi', 'Pubs', 'Ananthy']
```

empty --> split by letter  
```' '```  --> split by word  
</br>

## 3. Arrays -- to store multiple values in one variable.  

Creating Array:  

```js
const numbers = new Array(1, 2, 3, 4, 5);
```
```js
console.log(numbers); // [1, 2, 3, 4, 5]
```

Mixed Datatype Array  

```js
const fruits = ['apples', 'pears', true, 45];
```
Array Operations:  

```js
fruits[1] = 'orange';        // Change value: [ 'apples', 'orange', true, 45 ]
fruits.push('mangos');       // Add to end: [ 'apples', 'orange', true, 45, 'mangos' ]
fruits.unshift('strawberry'); // Add to start: [ 'strawberry', 'apples', 'orange', true, 45, 'mangos' ]
fruits.pop();                // Remove last element and return remaining
console.log(Array.isArray(fruits));        // true
console.log(Array.isArray('strawberry'));  // false -- other than fruits anything--> false
console.log(fruits.indexOf('apples'));     // 1
```
```js
console.log(fruits);                       // ['strawberry', 'apples', 'orange', true, 45]
```
</br>

#🧾 Summary

Data Types	Basic building blocks	String, Number, Boolean, etc.</br>
Template String	Easier string joining	`Hello ${name}` </br>
String Methods	Manipulate text	.length, .substring(), .split() </br>
Arrays	Hold multiple values	[1, 2, 3] </br>
Array Methods	Modify arrays	.push(), .pop(), .unshift() </br>

🧩 NaN → stands for “Not a Number”
Used when a value that’s not numeric is tried to be used in a numeric operation.

