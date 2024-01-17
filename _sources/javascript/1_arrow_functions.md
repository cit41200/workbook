# JavaScript Functions: 3 Ways

JavaScript functions can be written several ways. All are functionally equivalent, but it's important to know the syntax so that you can easily read documentation and online help articles.

(javascript:arrow_functions:basic)=
## 1: Basic Syntax

The most fundamental form of a JavaScript function uses the `function` keyword. Here's an example.

```
function helloWorld() {
    return 'Hello, world!';
}
```

The above function's name is `helloWorld()` and can be invoked in other JavaScript code by that name. *Note that the `()` is a part of the function's name.*

Functions can declare **parameters** that allow information to be passed into the function in the form of **arguments**. An example:

```
function addNumbers(x,y) {
    return x + y;
}
```

To invoke this function, you would enter `addNumbers(1,2)` (substituting in any numeric values for the arguments). This invocation would have a return value of `3`.

(javascript:arrow_functions:expressions)=
## 2: Function Expressions

Functions can also be written as *expressions*, where the function itself is the value of a variable. This allows you to treat the function as an object within your code. That's right: **in JavaScript a function is an object and can be assigned to a variable and passed to other code blocks via that variable name.**

Let's create a refactored version of the `addNumbers(x,y)` function.

```
const addNumbers = function (x,y) {
    return x + y;
}
```

To invoke the above function, you would use the following syntax:

```
console.log(addNumbers(2,3))
```

This results in an output of `5`; the return value of the function is written to the console.

(javascript:arrow_functions:arrow)=
## 3: Arrow Functions

Another way to write a JavaScript function is an *arrow function*. The function is equivalent to the previous example but the syntax is highly simplified.

You will see the arrow function syntax used extensively throughout the sample documentation for JavaScript in the Google Cloud Platform.

```
const addNumbers = (x,y) => return x + y;
```

Note that the `function` keyword is missing entirely. Further, if your function only has one line of output, you can eliminate the braces (`{}`) as well. The "arrow" `=>` tells the compiler that this is a JavaScript function.

You can even further simplify it by eliminating the `return` keyword. Here is the most stripped down version of our original function in JavaScript:

```
const addNumbers = (x,y) => x + y;
```