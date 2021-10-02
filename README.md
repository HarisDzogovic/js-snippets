# Collection of useful JavaScript snippets

## Section: Array
This section presents some basic operations on arrays.

### Add elements to an array

Add one element to the end of an array

> **Syntax**
> push(elements[])

- **elements[]:**
```JavaScript
var numbers = [42,43,1,2,3];
numbers.push(22);
console.log(numbers);
```
> Output: [42,43,1,2,3,22] 

Add one element to the start of an array

> **Syntax**
> splice(start, end, elements[])

- **start:** Position to add element(s).
- **end:**  Number of elements to remove/overwrite.
- **elements[]:** New element(s) to add.

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(0,0,22);
console.log(numbers);
```
> Output: [22,42,43,1,2,3] 

```JavaScript
var numbers = [42,43,1,2,3];
numbers.splice(0,0,22,23,24);
console.log(numbers);
```

> Output: [22,23,24,42,43,1,2,3] 
