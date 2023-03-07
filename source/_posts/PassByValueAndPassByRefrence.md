---
title: PassByValueAndPassByRefrence
writer: Sanjeev Kumar
date: 2023-03-02 12:04:04
tags: [Pass-By-Value & Pass-By-Ref]
---
# Pass by value and Pass by reference;
- there are two types of data in any programming language.
- The first type is the primitive data type and the Eg: String, number, boolean, characters etc.
- The second type is the Non-primitive data type Eg: array and objects 
- In primitive data type, a value assigned to the variable is stored in that variable. We can copy it directly by value.
In nonprimitive datatype value of an object or array assigned to a variable is exactly not stored in that variable. A variable assigned to an object or an array always has the reference of storage where data is stored. A not primitive data type can't be copied by value directly it will copy only that reference where data is stored actually. 

>For example if you will copy a object in N no of varialbes it tey all variables share the data from one location. If a value will be changed from any of the variable the change will reflect to all the variables. Because all the variable are sharing the data from same refrence.

~~~js
/* Example: Pass by value */

let name = 'Rohan';
let sohan = name;
console.log(sohan) // Output 'Rohan'

/* === === === */

let name = 'Rohan';
let sohan = name;
let name = 'Sanjeev';
console.log(sohan) // Output 'Rohan'
console.log(name) // Output 'Sanjeev'
~~~

~~~js
/* Example: pass by reference */

let info = {
    name: 'Sanjeev',
    add: 'Uttar Pradesh',
    pin: 221712,
    gender: male,
    qualification: 'B.tech'
}

let info2 = info;
let info3 = info2;
let info4 = info;

info4.name = 'Sanju';
info3.pin = 880876;
info2.add = 'Banglore';

console.log(info2); 

/* Output */

{
    name: 'Sanju',
    add: 'Banglore',
    pin: 880876;
    gender: male,
    qualification: 'B.tech'

}
console.log(info3); 

/* Output */

{
    name: 'Sanju',
    add: 'Banglore',
    pin: 880876;
    gender: male,
    qualification: 'B.tech'

}
console.log(info4);

 /* Output */

{
    name: 'Sanju',
    add: 'Banglore',
    pin: 880876;
    gender: male,
    qualification: 'B.tech'

}


~~~