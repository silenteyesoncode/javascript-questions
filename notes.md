
## 1. Understanding JavaScript's Data Types: Objects, Primitives, and Object Wrappers
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
