## Table of Contents

1. [Understanding JavaScript's Data Types: Objects, Primitives, and Object Wrappers](#1-understanding-javascripts-data-types-objects-primitives-and-object-wrappers)

2. [Utilizing the Rest Parameter Syntax for Collecting Function Arguments as Array-Like Objects](#2-utilizing-the-rest-parameter-syntax-for-collecting-function-arguments-as-array-like-objects)

3. [hasOwnProperty()](#3-hasownproperty)
4. [Table summarizing the differences between var, let, and const in JavaScript](#4-table-summarizing-the-differences-between-var-let-and-const-in-javascript)
5. [continue](#5-continue)
6. [reduce](#6-reduce())


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


## 3. hasOwnProperty()

- #### [hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

- The hasOwnProperty() method returns a boolean indicating whether the object has the specified property as its own property (as opposed to inheriting it


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

# 6 Reduce()





