*const vs let*
```js
const anotherInstructor = "Tim";
anotherInstructor = "Elie"; // TypeError
const anotherInstructor = "elie"; // SyntaxError
// can never redeclare a variable by the same name

const numbers = [1,2,3,4];
numbers.push(10); // 5
numbers // [1,2,3,4,5]
numbers = "no!"; // TypeError
// can mutate if it is an object, but not declare again

let anotherInstructor = "Tim";
anotherInstructor = "Elie";
let anotherInstructor = "Tim"; // SyntaxError
```
*block scope*
```js
var instructor = "Elie";
if(instructor === "Elie"){
    let funFact = "Plays the cello";
}

funFact; // ReferenceError!
```
*Hoisting with let*  
let does hoist, but we cannot access the value - it is in a TDZ(Temporal Dead Zone)
```js
function helloInstructor(){
    return elie;
    var elie = "ME!";
}
helloInstructor(); // undefined

function helloSecondInstructor(){
    return colt;
    let colt = "HIM!";
}
helloSecondInstructor(); // ReferenceError
```
*Use Cases for let*
```js
for(var i = 0; i <5; i++){
    setTimeout(function(){
        console.log(i);
    },1000)
}
// 5

for(var i =0; i < 5; i++){
    (function(j){
        setTimeout(function(){
            console.log(j);
        },1000);
    })(i)
}
// 0
// 1
// 2
// 3 
// 4
```
