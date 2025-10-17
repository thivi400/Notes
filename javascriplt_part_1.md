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
const numbers = new Array(1, 2, 3, 4, 5); // const numbers= [1,2,3,4,5];
```
```js
console.log(numbers); // [1, 2, 3, 4, 5]
```

Mixed Datatype Array  

```js
const fruits = ['apples', 'pears', true, 45];
console.log(fruits); // ['apples', 'pears', true, 45]
console.log(fruits.toString()); // apples,orange,true,45
```
</br>

## 4. Array Methods   

### modify, add, remove  

```js
fruits[1] = 'orange';          // Change value: [ 'apples', 'orange', true, 45 ]


fruits.push('mangos','banana'); // Add to end: [ 'apples', 'orange', true, 45, 'mangos', 'banana' ]
fruits.unshift('strawberry');  // Add to start: [ 'strawberry', 'apples', 'orange', true, 45, 'mangos', 'banana']


const removedLastFruit=fruits.pop();      // Remove last element and return remaining
const removedFirstFruit=fruits.shift();   // Remove first element and return remaining
console.log(removedLastFruit,removedFirstFruit); // banana strawberry
```
</br>

### slice(start,end),   splice(startIndex,deleteCount,...items),   toSpliced()
```js
// arr.slice(start,end) -- copy a portion of an array. Dont change original array
console.log(fruits);              // [ 'apples', 'orange', true, 45, 'mangos' ]
const myFruit1=fruits.slice(1,3); // from 1 to 2
console.log(myFruit1);            // [ 'orange', true ]
console.log(fruits);              // [ 'apples', 'orange', true, 45, 'mangos' ]

//arr.splice(startIndex,deleteCount,...items) -- modifies the original array and returns the deleted elements
const myFruit2=fruits.splice(1,3,'berry');// from 1 to 3 remove in original array
console.log(myFruit2);            // [ 'orange', true, 45 ]
console.log(fruits);              // [ 'apples', 'berry', 'mangos' ]

//arr.toSpliced(startIndex,deleteCount,...items) -- creates a new array with the changes while leaving the original untouched
const myFruit3=fruits.toSpliced(1,3,'rambutan');// from 1 to 3 
console.log(myFruit3);            // [ 'apple','rambutan','mangos']
console.log(fruits);              // [ 'apples', 'orange', true, 45, 'mangos' ]

// ie, myfruit2 is deleted & fruits is modified.
//     myfruit3 is modified & fruits is original.
```
<br/>
 
### Merge -- arr.concat() , spread operator: ...

```js
//concat
const breakfast =['Dosa', 'Idly'];
const lunch = ['briyani', 'Egg'];
const dinner= ['fried rice', 'tea'];

const overallFood= breafast.concat(lunch,dinner,'biscuits');

//spreadOperator
const overallFood_SpreadOperator=[...breakfast, ...lunch, ...dinner, 'juice'];
```
</br>

### arr.forEach() -- callbackfn: performs an action (no return).
```js
fruits.forEach((fruit)=> console.log(fruit));
fruits.forEach((fruit)=> console.log(fruit.toUpperCase());
```
</br>

### arr.map() -- transforms and returns a new array.
```js
const numbers=[1,2,4];
const multiplied= numbers.map((num)=> {
    return num*2;
});
const multiplied1= numbers.map((num)=>num*2); // No return in one line
console.log(multiplied, multiplied1); //[2,4,8] [2,4,8]
```
</br>

console.log(Array.isArray(fruits));        // true </br>
console.log(Array.isArray('strawberry'));  // false -- other than fruits anything--> false </br>
console.log(fruits.indexOf('apples'));     // 1 </br>

```js
console.log(fruits);                       // ['strawberry', 'apples', 'orange', true, 45]
```
</br>


## 4.Functions  
</br>

<table>
<thead>
<tr>
<th>No.</th>
<th>Feature</th>
<th>Normal Function</th>
<th>Arrow Function</th>
</tr>
</thead>
<tbody>

<tr>
<td>1</td>
<td><b>Syntax</b></td>
<td>

```js
function add(a, b) {
  return a + b;
}
```
</td>
<td>
 
```js
const add = (a, b) => a + b;
```
</td>
</tr>

<tr>
<td>2</td>
<td><b><code>this</code> keyword</b></td>
<td>
 
```js
const obj = {
  name: "Pubs",
  say: function() {
    console.log(this.name);
  }
};
obj.say(); // Pubs
```
</td>
<td>
 
```js
const obj = {
  name: "Pubs",
  say: () => {
    console.log(this.name);
  }
};
obj.say(); // undefined
```
</td>
</tr>

<tr>
<td>3</td>
<td><b><code>arguments</code> object</b></td>
<td>
 
```js
function sum() {
  console.log(arguments);
}
sum(1, 2, 3); // [1, 2, 3]
```
</td>
<td>
 
```js
const sum = () => {
  console.log(arguments);
}; // ❌ ReferenceError
```
</td>
</tr>

<tr>
<td>4</td>
<td><b>Hoisting</b></td>
<td>
 
```js
sayHi(); // works
function sayHi() {
  console.log("Hi");
}
```
</td>
<td>
 
```js
sayHi(); // ❌ Error
const sayHi = () => console.log("Hi");
```
</td>
</tr>

<tr>
<td>5</td>
<td><b>Use with <code>new</code> (constructor)</b></td>
<td>
 
```js
function Car() {}
```
</td>
<td>
 
```js
const Car = () => {};
new Car(); // ❌ TypeError
```
</td>
</tr>

<tr>
<td>6</td>
<td><b>Best for...</b></td>
<td>Object methods, constructors</td>
<td>Callbacks, short helper functions</td>
</tr>

<tr>
<td>7</td>
<td><b>Line style</b></td>
<td>
 
```js
function square(x) {
  return x * x;
}
```
</td>
<td>
 
```js
const square = x => x * x;
```
</td>
</tr>

<tr>
<td>8</td>
<td><b><code>prototype</code> property</b></td>
<td>
 
```js
function fn() {}
console.log(fn.prototype); // {}
```
</td>
<td>
 
```js
const fn = () => {};
console.log(fn.prototype); // undefined
```
</td>
</tr>

</tbody>
</table>

### ✅ Summary

| Prefer `function` when… | Prefer `=>` when… |
|--------------------------|-------------------|
| You need your own `this` or `arguments` | You want shorter code / inline logic |
| You’re defining object/class methods | You’re writing callbacks (like `map`, `setTimeout`) |
| You use `new` for object creation |  You’re using `map`, `filter`, `reduce`  |
| You’re creating a constructor |  |


###

#🧾 Summary

Data Types	Basic building blocks	String, Number, Boolean, etc.</br>
Template String	Easier string joining	`Hello ${name}` </br>
String Methods	Manipulate text	.length, .substring(), .split() </br>
Arrays	Hold multiple values	[1, 2, 3] </br>
Array Methods	Modify arrays	.push(), .pop(), .unshift() </br>

🧩 NaN → stands for “Not a Number”
Used when a value that’s not numeric is tried to be used in a numeric operation.

