# 🎯 Conclusion:  iteration methods
<h6> 

| Method| 	Best Use Case| 
|-----------|------------------|
| forEach()| 	Perform actions without returning a new array| 
| map()	| Transform and return a new array| 
| filter()	| Extract elements that match a condition| 
| reduce()| 	Accumulate values into a single result| 
| find()| 	Get the first matching element| 
| findIndex()| 	Get the index of the first match| 
| some()| 	Check if at least one element passes| 
| every()| 	Check if all elements pass| 
| sort()| 	Sort array elements in place| 
| for...of| 	Simple iteration over elements| 



</h6>

## 📌 1. forEach() – Iterates but Doesn't Return a New Array
- Purpose: Executes a function on each array element but does not return a new array.
- Use Case: When you need to perform side effects like logging or modifying an external variable.
 
``` 
const numbers = [1, 2, 3, 4, 5];

numbers.forEach(num => console.log(num * 2)); 
// Output: 2, 4, 6, 8, 10 (printed separately)
```

<h6> 
🚀 Key Takeaways: <br> 
Does not return anything (undefined). <br> 
Mutates external variables if used (not recommended). <br> 
  
</h6>

## 📌 2. map() – Transforms and Returns a New Array
- Purpose: Applies a function to each element and returns a new array.
- Use Case: When you need to modify data and store the result.
 

```js
const numbers = [1, 2, 3, 4, 5];

const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```
<h6> 
🚀 Key Takeaways: <br> 
Returns a new array (does not modify the original). <br> 
Preferred over forEach() when transformation is needed. <br> 
</h6>


## 📌 3. filter() – Selects Elements Based on a Condition
- Purpose: Filters elements that satisfy a condition and returns a new array.
- Use Case: When you want to extract specific elements from an array.
 
```js
const numbers = [10, 25, 30, 40, 55];

const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [10, 30, 40]
```
<h6>
🚀 Key Takeaways: <br> 
Returns only elements that match the condition. <br> 
Does not modify the original array. <br> 
</h6>

## 📌 4. reduce() – Accumulates Values into a Single Result
- Purpose: Reduces an array into a single value (sum, average, object, etc.).
- Use Case: When you need to calculate totals or aggregate data.
-  Example: Sum of Array Elements:
-  
```js
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 15
```
<h6> 
🚀 Key Takeaways: <br> 
Uses an accumulator (acc) to store the result. <br> 
Best for cumulative operations (sum, product, etc.). <br> 
</h6>

## 📌 5. find() – Returns the First Matched Element
- Purpose: Finds and returns the first element that satisfies a condition.
- Use Case: When you need to find only one matching element.
 
```js
const users = [
  { id: 101, name: "Alice" },
  { id: 102, name: "Bob" },
  { id: 103, name: "Charlie" }
];

const user = users.find(user => user.id === 102);
console.log(user); // { id: 102, name: "Bob" }
```
<h6> 
🚀 Key Takeaways: <br> 
Stops searching after finding the first match (faster than filter()). <br> 
Returns undefined if no match is found. <br> 
</h6>

## 📌 6. findIndex() – Returns Index of the First Matched Element
- Purpose: Like find(), but returns the index instead of the value.
- Use Case: When you need the position of an element, not the element itself.
 
```js
const numbers = [10, 25, 30, 40, 55];

const index = numbers.findIndex(num => num > 30);
console.log(index); // 3 (40 is at index 3)
```

<h6> 
🚀 Key Takeaways: <br> 
Returns index of the first matching element. <br> 
Returns -1 if no match is found. <br> 
</h6>

## 📌 7. some() – Checks If Any Element Matches a Condition
- Purpose: Returns true if at least one element passes the condition.
- Use Case: When you need to check for existence.
 
```js
const numbers = [1, 3, 5, 7, 8];

const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven); // true (because 8 is even)
```
<h6> 
🚀 Key Takeaways:<br> 
Stops searching as soon as it finds a match (efficient).<br> 
Returns true or false.<br> 
</h6>

## 📌 8. every() – Checks If All Elements Match a Condition
- Purpose: Returns true if all elements pass the condition.
- Use Case: When you need to validate an entire array.
 
```js
const numbers = [2, 4, 6, 8, 10];

const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // true (because all numbers are even)
```

<h6> 
🚀 Key Takeaways: <br> 
Returns true only if all elements match. <br> 
Stops early if one element fails the condition. <br> 
</h6>

## 📌 9. sort() – Sorts Elements in Place
- Purpose: Sorts an array in place (modifies the original array).
- Use Case: When you need to sort numbers, strings, or objects.
-  Example: Sorting Numbers

```js
const numbers = [40, 5, 25, 10];

numbers.sort((a, b) => a - b);
console.log(numbers); // [5, 10, 25, 40]
```

<h6> 
🚀 Key Takeaways: <br> 
By default, sorts as strings; use (a, b) => a - b for numbers. <br> 
Modifies the original array. <br> 
</h6>

## 📌 10. for...of – Iterates Over Array Elements
- Purpose: Simpler way to iterate over arrays.
- Use Case: When you just need to loop through values.
 
```js
const numbers = [1, 2, 3, 4, 5];

for (const num of numbers) {
  console.log(num); 
}
// Output: 1, 2, 3, 4, 5
```

<h6> 
🚀 Key Takeaways: <br>  
Easier than forEach() for simple loops.<br>  
Does not modify the array. <br> 
</h6>
