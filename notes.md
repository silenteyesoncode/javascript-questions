In JavaScript, not everything is an object. JavaScript has built-in primitive data types that are not objects. These primitive types include numbers, strings, booleans, null, and undefined. They are not objects and do not have properties or methods like objects do.

However, JavaScript also has object wrappers for these primitive types. For example, there is a Number object wrapper for numbers, a String object wrapper for strings, and a Boolean object wrapper for booleans. These object wrappers allow you to access properties and methods associated with the primitive values.

So while JavaScript has objects and object wrappers for primitive types, not everything in JavaScript is an object.

```
let numPrimitive = 42; // a primitive number value

let numObject = new Number(42); // a Number object wrapper

console.log(typeof numPrimitive); // Output: "number"
console.log(typeof numObject); // Output: "object"

console.log(numPrimitive.toFixed(2)); // Output: 42.00
console.log(numObject.toFixed(2)); // Output: 42.00
```
