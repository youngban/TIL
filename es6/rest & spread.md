
```js
function printRest(a,b,...c){
    console.log(a);
    console.log(b);
    console.log(c);
}

printRest(1,2,3,4,5);
//1
//2
//[3,4,5]
```

The rest operator always returns an array
Is called the rest operator "only" when it is a parameter to a function
Is accessed without the ... in a function
A better alternative to using the arguments array-like-object

```js
// ES5
function sumArguments(){
    var total = 0;
    for (var i = 0; i < arguments.length; i++){
        total += arguments[i];
    }
    return total;
}

// ES5 +
function sumArguments(){
    var argumentsArray = [].slice.call(arguments);
    return argumentsArray.reduce(function(accumulator, nextValue){
        return accumulator + nextValue;
    });
}

// ES2015
var sumArguments = (...args) => args.reduce((acc, next)) => acc+next);
```

Used on arrays to spread each value out (as a comma separated value)
Useful when you have an array, but what you are working with expects comma separated values

```js
// ES5
var arr1 = [1,2,3];
var arr2 = [4,5,6];
var arr3 = [7,8,9];

var combined = arr1.concat(arr2).concat(arr3);

// ES2015
var combined = [...arr1, ...arr2, ...arr3];

var arr = [3,2,4,1,5];
Math.max(arr); // NaN

// ES5
Math.max.apply(this, arr); // 5

// Es2015
Math.max(...arr); // 5
```