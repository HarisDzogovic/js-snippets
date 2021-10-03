# JavaScript Snippets

## Table of Contents

- [JavaScript Snippets](#JavaScript-Snippets)
  - [Section: Arrays](#Section-Arrays)
    - [Add element(s) to an array](#Add-elements-to-an-array)
    - [Remove element(s) from an array](#Remove-elements-from-an-array)

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

Copy whole array

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
