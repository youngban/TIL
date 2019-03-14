Arrow Functions
```js
var add = function(a,b) {
    return a+b;
}
```

Replace the keyword 'function' with =>
```js
var add = (a,b) => {
    return a+b;
}
```
One-line arrow function (the return keyword, {} 생략)
```js

var add = (a,b) => {
    return a+b;
}
var add = (a,b) => a+b;

function doubleAndFilter(arr){
    return arr.map(function(value){
        return value * 2;
    }).filter(function(value){
        return value % 3 === 0;
    })
};

var doubleAndFilter = arr => arr.map(val => val * 2).filter(num => num % 3 === 0);
```

Arrow functions do not have their own 'this' keyword
Inside of an arrow function, the keyword this refers to its enclosing context(the instructor object)
```js
var instructor = {
    firstName = "Elie",
    //why can't we use an arrow function here?
    //If we use arrow function, sayHi function will not have its own keyword this    
    //and the keyword this will not refer to the instructor object anymore! 
    sayHi: function(){
        setTimeout(() => {
            console.log("Hello " + this.firstName);
        }, 1000);
    }
}
instructor.sayHi(); // "Hello Elie"
```

An arguments keyword can be accessed if the arrow function is inside of another function 
(it will be the outer functions arguments)
```js
function outer() {
    return innerFunction = () => {
        return arguments;
    }
}
outer(1)(2); // only prints out [1]
```

Arrow functions should NEVER be used as methods in objects since we will get the incorrect value of the keyword this
```js
var instructor = {
    firstName: "Elie",
    sayHi: () => `Hello ${this.firstName}`;
}

instructor.sayHi(); // "Hello undefined"
```
