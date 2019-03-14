for in          / for of
속성의 key 반복  / 속성의 value 반복
                / Symbol.iterator 속성(Array, String, Map, Set ...)
                / Object는 Symbol.iterator 속성 X
                / index에 접근 X

```js
for(let i in 'hello'){
    console.log(i);
}
// 0 ,1 ,2 ,3 ,4

for(let i of 'hello'){
    console.log(i);
}
// h, e, l, l, o
