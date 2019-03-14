Destructuring
: Extracting value from data stored in objects and arrays

```js
var instructor = {
    firstName: "Elie",
    lastName: "Schoppick"
}

var firstName = instructor.firstName;
var lastName = instructor.lastName;

firstName; // "Elie"
lastName; // "Schoppik"
```
Object Destructuring
```js
var instructor = {
    firstName: "Elie",
    lastName: "Schoppik"
}

var {firstName, lastName} = instructor;

firstName; // "Elie"
lastName; // "Schoppik"

// ES5 default values with an object
function createInstructor(options){
    var options = options || {};
    var name = options.name || {first:"Matt", Last"Lane"}
    var isHilarious = options.isHilarious || false;
    return [name.first, name.last, isHilarious];
}

createInstructor(); // ["Matt", "Lane", false]
createInstructor({isHilarious:true}); // ["Matt", "Lane", true]
createInstructor({name: {first:"Tim", last:"Garcia"}}); // ["Tim", "Garcia", false]

// ES2015 destructuring
function createInstructor({name = {first:"Matt", last:"Lane"}, isHilarious=false} = {}){
    return [name.first, name.last, isHilarious];
}
```
We're passing in a destructured object as a default parameter!  
We assign as a default value an empty object so ES2015 knows we are destructuring  
If nothing is passed in, we default to the destructured object as the parameter.  

```js
//Object fields as parameters ES5
function displayInfo(obj) {
    return [obj.name, obj.favColor];
}
var instructor = {
    name: "Elie",
    favColor: "Purple"
};

displayInfo(instructor); // ["Elie", "Purple"]

//Object fields as parameters ES2015
function displayInfo({name, favColor}) {
    return [name, favColor];
}
var instructor = {
    name:"Elie",
    favColor:"Purple"
};

```
Array Distructuring
```js
// ES5
var arr = [1,2,3];
var a = arr[0];
var b = arr[1];
var c = arr[2];

// ES2015
var arr = [1,2,3];
var [a,b,c] = arr;

// ES5
function returnNumbers(a,b) {
    return [a,b];
}
var first = returnNumbers(5,10)[0];
var second = returnNumbers(5,10)[1];

// ES2015
function returnNumbers(a,b) {
    return [a,b];
}
[first, second] = returnNumbers(5,10);
```
Swapping Values
```js
// ES5
function swap(a,b){
    var temp = a;
    a = b;
    b = temp;
    return [a,b];
}

swap(10,5); // [5,10]

// ES2015
function swap(a,b){
    return [a,b] = [b,a];
}