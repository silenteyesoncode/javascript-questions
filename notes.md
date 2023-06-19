# MyNotes
### Table of Contents

1. [Understanding JavaScript's Data Types: Objects, Primitives, and Object Wrappers](#1-understanding-javascripts-data-types-objects-primitives-and-object-wrappers)
2. [Utilizing the Rest Parameter Syntax for Collecting Function Arguments as Array-Like Objects](#2-utilizing-the-rest-parameter-syntax-for-collecting-function-arguments-as-array-like-objects)
3. [hasOwnProperty()](#3-hasownproperty)
4. [Table summarizing the differences between var, let, and const in JavaScript](#4-table-summarizing-the-differences-between-var-let-and-const-in-javascript)
5. [continue](#5-continue)
6. [reduce](#6-reduce)
7. [Truthy and Falsy Values in JavaScript](#7-truthy-and-falsy-values-in-javascript)



## 1. JavaScript's Data Types: Objects, Primitives, and Object Wrappers 
-  In JavaScript, not everything is an object. JavaScript has built-in primitive data types that are not objects. These primitive types include numbers, strings, booleans, null, and undefined. They are not objects and do not have properties or methods like objects do.

-  However, JavaScript also has object wrappers for these primitive types. For example, there is a Number object wrapper for numbers, a String object wrapper for strings, and a Boolean object wrapper for booleans. These object wrappers allow you to access properties and methods associated with the primitive values.

 - So while JavaScript has objects and object wrappers for primitive types, not everything in JavaScript is an object.

  
```
let numPrimitive = 42; // a primitive number value

let numObject = new Number(42); // a Number object wrapper

console.log(typeof numPrimitive); // Output: "number"
console.log(typeof numObject); // Output: "object"

console.log(numPrimitive.toFixed(2)); // Output: 42.00
console.log(numObject.toFixed(2)); // Output: 42.00
```
### [Back to Top](#mynotes)

## 2. Utilizing the Rest Parameter Syntax for Collecting Function Arguments as Array-Like Objects
- When using the rest parameter syntax (...args), the collected arguments are stored as an array-like object called args. This means that args behaves similarly to an array in terms of accessing individual elements and the length property. However, it does not have access to array methods like push, pop, or forEach.

- To perform array operations or use array methods on args, you can convert it into a proper array using techniques like the Array.from() method or the spread syntax [...args].

```
function getAge(...args) {
  const argsArray = Array.from(args); // Convert args to an array
  console.log(argsArray);
}

getAge(21);
```

### [Back to Top](#mynotes)
## 3. hasOwnProperty()

- #### [hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

- The hasOwnProperty() method returns a boolean indicating whether the object has the specified property as its own property (as opposed to inheriting it

### [Back to Top](#mynotes)
## 4. Table summarizing the differences between var, let, and const in JavaScript

#### var:

- Variables declared with `var` have function scope. This means that they are accessible throughout the entire function in which they are declared.
- Variables declared with `var` are hoisted, which means they are moved to the top of their scope during the compilation phase.
- `var` allows variables to be redeclared and reassigned within its scope.

#### let:

- Variables declared with `let` have block scope. They are only accessible within the block ({}) in which they are defined.
- `let` does not allow variables to be redeclared within the same block scope, but it allows them to be reassigned.
- `let` variables are not hoisted, so they need to be declared before they are used.

#### const:

- Variables declared with `const` also have block scope.
- `const` stands for "constant," which means that once a value is assigned to a `const` variable, it cannot be reassigned.
- `const` variables must be assigned a value at the time of declaration and cannot be left uninitialized.
- Like `let`, `const` variables are not hoisted and need to be declared before use.



| Feature   | var                         | let                          | const                        |
|-----------|-----------------------------|------------------------------|------------------------------|
| Scope     | Function scope              | Block scope                  | Block scope                  |
| Hoisting  | Hoisted                     | Not hoisted                  | Not hoisted                  |
| Redeclaration  | Allowed within scope     | Not allowed within same scope | Not allowed within same scope |
| Reassignment   | Allowed                   | Allowed                      | Not allowed                  |
| Initialization | Can be left uninitialized | Can be left uninitialized    | Must be initialized          |

- Remember that `var` has function scope, while `let` and `const` have block scope. Variables declared with `var` are hoisted, meaning they are moved to the top of their scope during compilation. However, `let` and `const` variables are not hoisted and need to be declared before use.

- With `var`, variables can be redeclared and reassigned within the same scope. In contrast, `let` does not allow redeclaration within the same block scope, although reassignment is permitted. `const` variables are constants and cannot be reassigned after they are initialized. They must be assigned a value at the time of declaration and cannot be left uninitialized.

- Using `let` and `const` is generally recommended over `var` in modern JavaScript, as they provide better scoping behavior and help prevent common issues associated with `var`, such as accidental global scope pollution.

### [Back to Top](#mynotes)
## 5. continue

- #### [continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)
- The continue statement terminates execution of the statements in the current iteration of the current or labeled loop, and continues execution of the loop with the next iteration.

```
let text = '';

for (let i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text = text + i;
}

console.log(text);
```
### [Back to Top](#mynotes)
## 6. Reduce()

- The reduce() method takes two parameters: a callback function and an optional initial value. The callback function is executed on each element of the array, and it takes four arguments: accumulator, currentValue, currentIndex, and the array itself.

```
array.reduce(callback[, initialValue])
```

The callback function is called for each element in the array, and it has the following arguments:

- `accumulator`: It is the accumulated value computed from previous iterations. In the first iteration, if an initial value is provided, the accumulator will be set to that value. Otherwise, it will be set to the first element of the array, and the iteration will start from the second element.
- `currentValue`: It is the current element being processed in the array.
- `currentIndex` (optional): It is the index of the current element being processed.
- `array` (optional): It is the array on which `reduce()` was called.

The callback function should return the updated accumulator value after performing the desired operation on the `currentValue`. The returned accumulator value will be used as the accumulator in the next iteration.

If an initial value is provided as the second argument to `reduce()`, the iteration starts from the first element of the array with the initial value as the accumulator. If no initial value is provided, the iteration starts from the second element of the array, and the first element becomes the initial value.


 

```
const array = [15, 16, 17, 18, 19];

function reducer(accumulator, currentValue, index) {
  const returns = accumulator + currentValue;
  console.log(
    `accumulator: ${accumulator}, currentValue: ${currentValue}, index: ${index}, returns: ${returns}`,
  );
  return returns;
}

array.reduce(reducer);

Output: 
accumulator: 15, currentValue: 16, index: 1, returns: 31
accumulator: 31, currentValue: 17, index: 2, returns: 48
accumulator: 48, currentValue: 18, index: 3, returns: 66
accumulator: 66, currentValue: 19, index: 4, returns: 85

```
### [Back to Top](#mynotes)
## 7. Truthy and Falsy Values in JavaScript

| Falsy Values | Truthy Values      |
|--------------|--------------------|
| `false`      | `true`             |
| `0`          | `1`                |
| `""`         | `"Hello"`          |
| `null`       | `{}` (empty object)|
| `undefined`  | `[1, 2, 3]`        |
| `NaN`        | `function() {}`    |


### [Back to Top](#mynotes)

## 8. Promise.race 

- [Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race)
- Promise.race() is a JavaScript function that takes an array of promises as input and returns a new promise. The new promise settles (resolves or rejects) as soon as any of the promises in the input array settles.



