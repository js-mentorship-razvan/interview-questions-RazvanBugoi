# Interview Questions and Answers 

1. **What is a potential pitfall using ```typeof bar === "object"``` to determine if bar is an object? How can this pitfall be avoided?** 


The pitfall is that both null and array data type will console.log true when checking their type: 

```typeof null === "object" // prints true 
typeof array === "object" // prints true 
```
We can avoid this pitfall by comparing out object against ```null``` and ```array``` and we should get ```false``` in return. 


2. **What will the code below output to the console and why ?** 

``` 
(function() {
    var a = b = 3;
})();

console.log("a defined? " + (typeof a !== "undefined"));
console.log("a defined? " + (typeof b !== "undefined"));
```

First console.log will output "true" and second "false" because ```a``` is equal to something that is still to be defined. We can avoid this by using ```use strict``` mode and the browser's engine won't let us do this. 


3. **What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block?**

Because of the scope. When wrapping it in a function block, we set it's scope to local to avoid problems in the future.

4. **What is the significance, and what are the benefits, of including "use strict" at the beginning of a JavaScript source file?**

One of the benefits is that it makes debugging much easier because the engine won't let you define a variable outside of a function if it doesn't have a value assigned to it.

5. **Consider the two functions below. Will they both return the same thing? Why or why not?**
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

The first function will return the object while the second function will return undefined because of the positioning of the curly braces under return.

6. **What is NaN? What is its type? How can you reliably test if a value is equal to NaN?**

If we ```console.log(typeof NaN)``` we will get "number".
To check if a value is NaN, we can use ```Number.isNaN()``` method.

7. **Write a function ```isInteger(x)``` that determines if x is an integer.**
```
function isInteger(x) {
    Number.isInteger(x);
}
```

8. **In what order will the numbers 1-4 be logged to the console when the code below is executed? Why?**
```
(function(){
    console.log(1);
    setTimeout(function(){console.log(2)}, 1000);
    setTimeout(function(){console.log(3)}, 0);
    console.log(4);
})();
```

The right order is 1,4,3,2 because the engine will first print what's easiest to run. In our case a simple console.log is easiest to run then a function.

9. **Write a simple function (less than 160 characters) that returns a boolean indicating whether or not a string is a palindrome.**

```
function pal(x) {
   return x === x.split("").reverse().join("");
}
```

10. **Write a sum method which will work properly when invoked using either syntax below.**
```
console.log(sum(2,3));  // Outputs 5
console.log(sum(2)(3)); // Outputs 5
```
```
function sum(a, b) {
    if (arguments.length == 2) {
        return arguments[0] + arguments[1];
    } else {
        return function(b) {
            return a + b;
        }
    }
}
```

11. **What is a "closure" in JavaScript? Provide an example.**
```
function createCounter() {
    let counter = 0;
    const myFunction = function () {
        counter = counter + 1;
        return counter;
    }
    return myFunction
}
const increment = createCounter();
const c1 = increment();
const c2 = increment();
const c3 = increment();
console.log("example increment", c1, c2, c3);
```

A closure is basically a function within a function. 

12. **What will be the output when the following code is executed? Explain.**
```
console.log( false == "0");
console.log( false === "0");
```

First console.log will output ```true``` because it doesn't check for it's type, it only converts the string to a number and compares it. The other console.log will output false because it checks for type too but without converting the value. 

13. 
