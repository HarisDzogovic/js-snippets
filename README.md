# JavaScript Snippets

## Table of Contents

- [JavaScript Snippets](#JavaScript-Snippets)
  - [Section: Arrays](#Section-Arrays)
    - [Array Initialization](#Array-Initialization)
    - [Add element(s) to an array](#Add-elements-to-an-array)
    - [Remove element(s) from an array](#Remove-elements-from-an-array)
    - [Copy element(s) of array](#Copy-elements-of-array)
    - [Merge two arrays](#Merge-two-arrays)
    - [Check equality of arrays](#Check-equality-of-arrays)
    - [Apply operation on all elements of an array](#Apply-operation-on-all-elements-of-an-array)
    - [Filter elements of an array](#Filter-elements-of-an-array)
    - [Check if element is in array](#Check-if-element-is-in-array)
    - [Get part of array](#Get-part-of-array)
  - [Get unique values of array](#Get-unique-values-of-array)
  - [Section: Dictionaries](#Section-Dictionaries)
  - [Section: Queue (FIFO)](#Section-Queue-FIFO)
  - [Section: Stack (LIFO)](#Section-Stack-LIFO)
  - [Section: Conversion](#Section-Conversion)
    - [String to Boolean](#String-to-Boolean)
    - [Boolean to String](#Boolean-to-String)
  - [Section: Logical Operations](#Section-Logical-Operations)

## Section: Arrays

### Array Initialization

Empty array

---

```JavaScript
var array = [];
var array = new Array();
```

Single-dimensonial array

---

```JavaScript
var numbers = [1,2,3];
var strings = ["1","2","3"];
```

Multidimensonial array

---

```JavaScript
var numbers = [[1,2],[3,4],[5,6]];
```

### Add element(s) to an array

Functions

---
> **Syntax**
> push(elements[])

- **elements[]:** New element(s) to add.

> **Syntax**
> splice(start, end, elements[])

- **start:** Position to add element(s).
- **end:**  Number of elements to remove.
- **elements[]:** New element(s) to add.

---

Add one element to the end of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.push(22);
console.log(numbers);
```
> Output: [42,43,1,2,3,22] 

Add multiple elements to the end of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.push(22,23,24);
console.log(numbers);
```
> Output: [42,43,1,2,3,22,23,24] 

Add one element to the start of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(0,0,22);
console.log(numbers);
```
> Output: [22,42,43,1,2,3] 

Add multiple elements to the start of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(0,0,22,23,24);
console.log(numbers);
```

> Output: [22,23,24,42,43,1,2,3] 

### Remove element(s) from an array

Functions

---

> **Syntax**
> pop()

> **Syntax**
> shift()

> **Syntax**
> splice(start, end, elements[])

- **start:** Position to add element(s).
- **end:**  Number of elements to remove.
- **elements[]:** New element(s) to add.

> **Syntax**
> delete

---

Remove last element of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.pop();
console.log(numbers);
```
> Output: [42,43,1,2] 

Remove first element of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.shift();
console.log(numbers);
```
> Output: [43,1,2,3] 

Remove multiple elements from the start of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(0,2);
console.log(numbers);
```
> Output: [1,2,3] 

Remove multiple elements from the end of an array

---

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(numbers.length - 2 ,2);
console.log(numbers);
```
> Output: [42,43,1] 

Remove all array elements by value

---

```JavaScript
var numbers = [42,43,1,2,2,2,2,3];
    for(let i = 0; i< numbers.length; i++){ 
        if ( numbers[i] === 2) { 
            numbers.splice(i, 1); 
            //Length is chaning do not skip the next element in the array
            i--;
        }
    }
console.log(numbers);
```
> Output: [42,43,1,3] 


Remove first element with value in array

---

```JavaScript
var numbers = [42,43,1,2,2,2,2,3];
    for(let i = 0; i< numbers.length; i++){ 
        if ( numbers[i] === 2) { 
            numbers.splice(i, 1); 
            break;
        }
    }
console.log(numbers);
```
> Output: [42,43,1,2,2,2,3] 

Explicitly remove array element by index

---

```JavaScript
var numbers = [42,43,1,2,3];
delete numbers[1];
console.log(numbers);
```
> Output: [42,undefined,1,2,3] 

**Annotation:** The value 43 is not anymore part of the array but the length remains the same. The position where 43 was before we have now an "undefined" element.

Remove elements by using array filter method 

---

```JavaScript
var numbers = [42,43,1,2,2,2,2,2,3];
var filteredNumbers= numbers.filter(function(value, index, arr){ 
        return value !== 2;
    });
console.log(filteredNumbers);
```
> Output: [42,43,1,3] 

### Copy element(s) of array

Functions

---

> **Syntax**
> splice(start, end, elements[])

- **start:** Position to add element(s).
- **end:**  Number of elements to remove.
- **elements[]:** New element(s) to add.

---

Copy whole array

---

```JavaScript
var numbers = [42,43,1,2,3];
var copyNumbers = [];
copyNumbers = numbers.slice();
console.log(numbers);
console.log(copyNumbers);
```
> Output: 
>
>[42,43,1,2,3] 
>
>[42,43,1,2,3] 

Copy whole array (ECMAScript 6)

---

```JavaScript
var numbers = [42,43,1,2,3];
var copyNumbers = [];
copyNumbers = [...numbers];
console.log(numbers);
console.log(copyNumbers);
```
> Output: 
>
>[42,43,1,2,3] 
>
>[42,43,1,2,3] 

### Merge two arrays

Functions

---

> **Syntax**
> concat(elements)

- **elements:** Arrays and/or values to concat to current array

---

Merge one array to other array with concat

---

```JavaScript
var numbers1 = [42,43,1,2,3];
var numbers2 = [9,8,7,6,5];
var numbers12 = numbers1.concat(numbers2);
console.log(numbers12);
```
> Output: [42,43,1,2,3,9,8,7,6,5]

Merge one array to other array (ECMAScript 6)

---

```JavaScript
var numbers1 = [42,43,1,2,3];
var numbers2 = [9,8,7,6,5];
var numbers12 = [...numbers1,...numbers2];
console.log(numbers12);
```
> Output: [42,43,1,2,3,9,8,7,6,5]

### Check equality of arrays

Check equality with join function

---

```JavaScript
var numbers1 = [42,43,1,2,3];
var numbers2 = [42,43,1,2,3];
var numbers3 = [2,3,4,5,6,7];

var equal12 = numbers1.join() === numbers2.join();
var equal13 = numbers1.join() === numbers3.join();

console.log(equal12);
console.log(equal13);
```
> Output: 
>
> True
>
> False

Check equality with custom function

---

```JavaScript
var numbers1 = [42,43,1,2,3];
var numbers2 = [42,43,1,2,3];
var numbers3 = [2,3,4,5,6,7];

function arraysEqual(a, b) {
    if (a === b) return true;
    if (a == null || b == null) 
        return false;
    if (a.length !== b.length) 
        return false;
    for (var i = 0; i < a.length; i++) {
        if (a[i] !== b[i]) return false;
    }
    return true;
}

var equal12 = arraysEqual(numbers1,numbers2);
var equal12 = arraysEqual(numbers1,numbers3);

console.log(equal12);
console.log(equal13);
```
> Output: 
>
> True
>
> False

### Apply operation on all elements of an array

Apply operation on all elements with map function

---

```JavaScript
var numbers = [42,43,1,2,3];
var mappedNumbers = numbers.map(function (number) { return number * 2 });

console.log(mappedNumbers);
```
> Output: [84, 86, 2, 4, 6]

Apply operation on all elements with map function (ECMAScript 6)

---

```JavaScript
var numbers = [42,43,1,2,3];
var mappedNumbers = numbers.map(number => number * 2);

console.log(mappedNumbers);
```
> Output: [84, 86, 2, 4, 6]

### Filter elements of an array

Apply filter operation on all elemnts of an array

---

```JavaScript
var numbers = [1,2,3,4,5,6,7,8];
var oddNumbers = numbers.filter(function(number) {
        return number % 2 === 1;
});

console.log(oddNumbers);
```
> Output: [1, 3, 5, 7]

Apply filter operation on all elemnts of an array (ECMAScript 6)

---

```JavaScript
var numbers = [1,2,3,4,5,6,7,8];
var oddNumbers = numbers.filter(number => number % 2 === 1);

console.log(oddNumbers);
```
> Output: [1, 3, 5, 7]

### Check if element is in array

Check if element is inside array with in operator

---

```JavaScript
var numbers = [1,2,3,4,5,6,7,8];
var contains = 3 in numbers;
var notContains = 9 in numbers;

console.log(contains);
console.log(notContains);
```
> Output: 
>
> True
>
> False

Check if element is inside array with includes() function

---

```JavaScript
var numbers = [1,2,3,4,5,6,7,8];
var contains = numbers.includes(3);
var notContains = numbers.icludes(9);

console.log(contains);
console.log(notContains);
```
> Output: 
>
> True
>
> False

### Get part of array

Get a part of an array with splice() function

---

```JavaScript
var numbers = [1,2,3,4,5,6,7,8];
var first3 = numbers.splice(0, 3);
var last3 = numbers.splice(numbers.length-3,3);

console.log(first3);
console.log(last3);
```
> Output: 
>
> [1, 2, 3]
>
> [6, 7, 8]

## Get unique values of array

Get unique values of array with indexOf() and filter function

---

```JavaScript
var numbers = [1,2,3,1,2,3,1,2];

function isUnique(value, index, self) {
    return self.indexOf(value) === index;
}

var uniqueNumbers = numbers.filter(isUnique);

console.log(uniqueNumbers);
```
> Output: [1, 2, 3]

## Section: Dictionaries

## Section: Queue (FIFO)

## Section: Stack (LIFO)

## Section: Conversion

### String to Boolean

```JavaScript
var string1 = "true";
var value1 = (string1.toLowerCase() == "true");

var string2 = "false";
var value2 = JSON.parse(string2);
```

### Boolean to String

```JavaScript
var bool1 = true;
var string1 = bool1.toString();

var bool2 = false;
var string2 = bool2.toString();
```

## Section: Logical Operations

## Section: Functions

### The arguments object

```JavaScript
function foo(param1, param2, param3) {
  console.log(arguments[0]);
  console.log(arguments[1]);
  console.log(arguments[2]);
}

foo(42, 0, 1);
```
> Output: 
>
> 42
>
> 0
>
> 1

## Section: Expressions and Operators

### Spread Operator

```JavaScript
function sum(a, b, c) {
  return a + b + c;
}

const values = [42, 0, 1];

console.log(sum(...numbers));
```
> Output: 
>
> 43

```JavaScript
let args = [42, 0, 1];
var [head, ...tail] = args; // head = 42, tail = [0, 1]
```

```JavaScript
const addToEnd = (list) => {
    return [...list, 0];  
}

------------------------------

const addToEnd = (list) => {
    return list.concat([0]);
}
```
