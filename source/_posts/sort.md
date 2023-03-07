---
title: Sort method
date: 2023-03-07 10:17:37
tags: [Sort method]
---
# Sort method

- The sort method sorts the elements of an array (Strings, Numbers, Objects) and returns the same reference of the sorted array except for returning a new array.
- The default sort order is ascending order by changing or swapping the elements in the original array. This algorithm is known as an in-place algorithm.
- First of all, it will convert the element into strings and compare their sequence according to `UTF-16` code and then replace the elements accordingly.
- The time and space complexity depends on different factors and is not fixed.

~~~js
let months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);

// Expected output: ["Dec", "Feb", "Jan", "March"]

let numbers = [1, 30, 4, 21, 100];
numbers.sort();
console.log(array1);

// Expected output: Array [1, 100, 21, 30, 4]
~~~

- The sort method takes a callback function as an argument. this function is known as compare function.
- If compare function is not defined all elements are converted to the string and sorted according to each character's order.
- The compare function takes two arguments for comparison. and sort the array according to the comparison result.
- All the undefined elements move to the end of the array.
- All the empty elements move at the end after undefined elements.
- `true` `false` `null` these are all firstElement converted to the string and then sorted by the `UTF-16`

~~~JS
// Strings

let nameArray = ['sanjeev', 'sandeep', 'sangeeta', 'sanjeet', 'sankar', 'sanju'];
nameArray.sort();

console.log(nameArray);

// Expected output: 

['sandeep', 'sangeeta', 'sanjeet', 'sanjeev', 'sanju', 'sankar'];

//Different case strings

let capitalAndCountry = ['dehiIndia', 'kathmanduNepal', 'islamabadPakistan', 'tokyoJapan', 'kabulAfghanistan', 'washingtonD.C.America'];
capitalAndCountry.sort();

console.log(capitalAndCountry);

// Expected output: 

['dehiIndia', 'islamabadPakistan', 'kabulAfghanistan', 'kathmanduNepal', 'tokyoJapan', 'washingtonD.C.America'];

//  Integers 

let integers = [45, 400, 3, 4, 39, 3000, 1, 10, 111, 444];

integers.sort();

console.log(integers);

// Expected output: 

[1, 10, 111, 3, 3000, 39, 4, 400, 444, 45];

// Note: We are not providing compare function so result will will be according to `UTF-16` code sequence.

// Floating point numbers

let floatingNumbers = [3.14, 44.99, 36.41, 8.41, 0.004, 0.0041];

floatingNumbers.sort();

console.log(floatingNumbers); 

// Expected output: 

[0.004, 0.0041, 3.14, 36.41, 44.99, 8.41];

// Objects

let objectArray = [
    {
        "id": 1,
        "first_name": "Gregg",
        "last_name": "Lacey",
        "job": "Web Developer III",
        "salary": "$3.62",
        "location": "Malta"
    },
    {
        "id": 2,
        "first_name": "Hernando",
        "last_name": "Scargill",
        "job": "Sales Associate",
        "salary": "$4.16",
        "location": "France"
    },
    {
        "id": 3,
        "first_name": "Loren",
        "last_name": "Doull",
        "job": "Physical Therapy Assistant",
        "salary": "$4.34",
        "location": "U.S. Virgin Islands"
    },
    {
        "id": 4,
        "first_name": "Sherwood",
        "last_name": "Adriano",
        "job": "Web Developer II",
        "salary": "$6.46",
        "location": "Brazil"
    },
    {
        "id": 5,
        "first_name": "Addison",
        "last_name": "Dofty",
        "job": "Structural Engineer",
        "salary": "$6.40",
        "location": "Costa Rica"
    }
];

// Applying sort

objectArray.sort ((firstElement, secondElement) => {

    if (firstElement.first_name > secondElement.first_name) {

        return 1;

    } else if (firstElement.first_name < secondElement.first_name) {

        return -1;

    } else {

        return 0;

    }

});

console.log(objectArray);

// Expect output:

[
    {
        "id": 5,
        "firsMultiple keys in an objectt_name": "Addison",
        "last_name": "Dofty",
        "job": "Structural Engineer",
        "salary": "$6.40",
        "location": "Costa Rica"
    },
    {
        "id": 1,
        "first_name": "Gregg",
        "last_name": "Lacey",
        "job": "Web Developer III",
        "salary": "$3.62",
        "location": "Malta"
    },
    {
        "id": 2,
        "first_name": "Hernando",
        "last_name": "Scargill",
        "job": "Sales Associate",
        "salary": "$4.16",
        "location": "France"
    },
    {
        "id": 3,
        "first_name": "Loren",
        "last_name": "Doull",
        "job": "Physical Therapy Assistant",
        "salary": "$4.34",
        "location": "U.S. Virgin Islands"
    },
    {
        "id": 4,
        "first_name": "Sherwood",
        "last_name": "Adriano",
        "job": "Web Developer II",
        "salary": "$6.46",
        "location": "Brazil"
    },
];

// Multiple keys in object

let info = [
    {
        name: 'Sanjeev kumar',
        roll_no: 75
    },
    {
        name: 'Ankita',
        roll_no: 5
    },
    {
        name: 'Aarti',
        roll_no: 8
    },
    {
        name: 'Srikesh jalan',
        roll_no: 50
    },
    {
        name: 'Abhishek tiwari',
        roll_no: 1,
    },
    {
        name: 'Himanshu Srivastava',
        roll_no: 35
    },
    {
        name: 'Himanshu Srivastava',
        roll_no: 28,
    }
];

// Applying sort

info.sort ((firstElement, secondElement) => {

    if (firstElement.name < secondElement.name) {

        return -1;

    } else if (firstElement.name > secondElement.name) {

        return 1;

    } else if ( firstElement.name == secondElement.name) {
        
        if (firstElement.roll_no < secondElement.roll_no) {

            return -1;

        } else if (firstElement.roll_no > secondElement.roll_no) {

            return 1;

        } else {

            return 0;

        } 
    }

});

console.log(info);

// Expected output: 

[
    {
        name: 'Aarti', 
        roll_no: 8
    },
    {
        name: 'Abhishek tiwari',
        roll_no: 1,
    },
    {
        name: 'Ankita',
        roll_no: 5
    },
    {
        name: 'Himanshu Srivastava',
        roll_no: 28,
    },
    {
        name: 'Himanshu Srivastava',
        roll_no: 35
    },
    {
        name: 'Sanjeev kumar',
        roll_no: 75
    },
    {
        name: 'Srikesh jalan',
        roll_no: 50
    },
];

~~~ 
