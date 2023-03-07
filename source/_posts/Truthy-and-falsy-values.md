---
title: Truthy-and-falsy-values
writer: Sanjeev Kumar
date: 2023-02-26 10:27:17
tags: [Truthy & Falsy values]
---
When we convert a non-boolean value to a boolean the result we will get is either `true` or `false`. So in javascript, a value of any datatype will be either a truthy or falsy.

There are 6 falsy values in javascript except for these 6 values all other values are considered as truthy values.

---
## Falsey values
1. **false**
2. **' '**
3. **0**
4. **undefined**
5. **null**
6. **NaN**

---
~~~js
console.log(Boolean(''));     // Expected output false

console.log(Boolean(0));     // Expected output false

console.log(Boolean(undefined));     // Expected output false

console.log(Boolean(null));     // Expected output false

console.log(Boolean(NaN));     // Expected output false

console.log(Boolean('Hello world!'));     // Expected output true

console.log(Boolean(Infinity));     // Expected output true

console.log(Boolean(-Infinity));     // Expected output true

console.log(Boolean(0) === false);     // Expected output true (implicit conversion)
~~~

---
## Checking by the Boolean inbuild method
to check if a value is truthy or falsy we can use the Boolean method by passing the value.

~~~js
let value1 = Boolean('');

console.log(value1) // Expected output 'false'

let value2 = Boolean('Hello');

console.log(value2) // Expected output 'true'
~~~

***
## Use of truthy and falsy values in

### 1. if else statement

- Javascript uses type conversion implicitly. In cases of conditional if-else statements if we will provide only a single value in parenthesis it will implicitly convert that value into a boolean.
***
~~~js
if('Hello'){
    console.log('Truthy');
}else{
    console.log('Falsy');
}
// Expected output 'Truthy'

if(0){
    console.log('Truthy');
}else{
    console.log('Falsy');
}
// Expected output 'Falsy'
~~~
***

### 2. Logical `AND` operator (&&)

- A logical `AND` operator returns true only when all the given conditions are true otherwise it will return false.
- If all the given conditions are true it will return the last true condition.
- If any of the given cases or more cases are false it will return the first false value.

~~~js
let condition1 = ('Hello' && true && Infinity && -1 && -Infinity);
console.log(condition1)
// Expected output -Infinity because all the values are turthy value
let condition2 = ('Hello' && true && 0 && 'World' && false);
console.log(condition2);
// Expected output 0 because 0 is first falsy value
~~~
***
### 2. Logical `OR` operator (||)

- A logical `OR` operator returns true if any one of the given conditions is true otherwise it will return false.
- If all the given conditions are false it will return the last false condition.
- If any of the given cases or more cases are true it will return the first true value.

~~~js
let condition1 = ('' || false || 0 || undefined || null || NaN || 1);
console.log(condition1)
// Expected output 1 because there is no any turthy value
let condition2 = ('Hello' || true || 0 || ture || false);
console.log(condition2);
// Expected output Hello because Hello is first falsy value
~~~
***