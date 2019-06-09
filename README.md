# interview

What is a potential pitfall with using typeof bar === "object" to determine if bar is an object? How can this pitfall be avoided?



What will the code below output to the console and why?

```
(function(){
  var a = b = 3;
})();

console.log("a defined? " + (typeof a !== 'undefined'));
console.log("b defined? " + (typeof b !== 'undefined'));
```

What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block?


What is the significance, and what are the benefits, of including 'use strict' at the beginning of a JavaScript source file?


Consider the two functions below. Will they both return the same thing? Why or why not?

```
function foo1()
{
  return {
      bar: "hello"
  };
}

function foo2()
{
  return
  {
      bar: "hello"
  };
}
```


What is NaN? What is its type? How can you reliably test if a value is equal to NaN?

Write a function `isInteger(x)` that determines if x is an integer.


In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?

```
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```

Write a simple function (less than 160 characters) that returns a boolean indicating whether or not a string is a palindrome.


Write a sum method which will work properly when invoked using either syntax below.

```
console.log(sum(2,3));   // Outputs 5
console.log(sum(2)(3));  // Outputs 5
```

What is a “closure” in JavaScript? Provide an example.

```
function createCounter() {
    let counter = 0
    const myFunction = function () {
        counter = counter + 1
        return counter
    }
    return myFunction
}
const increment = createCounter()
const c1 = increment()
const c2 = increment()
const c3 = increment()
console.log('example increment', c1, c2, c3)
```


What will be the output when the following code is executed? Explain.

```
console.log(false == '0')
console.log(false === '0')
```

What will the following code output to the console and why:

```
let hero = {
    _name: 'John Doe',
    getSecretIdentity: function (){
        return this._name;
    }
};

let stoleSecretIdentity = hero.getSecretIdentity;

console.log(stoleSecretIdentity());
console.log(hero.getSecretIdentity());
```

How do you clone an object?

What do the following lines output, and why?

```
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```

How do you add an element at the begining of an array? How do you add one at the end?


