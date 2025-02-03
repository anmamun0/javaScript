## Common JavaScript Objects & Methods

 

| Built-in Objects | Web APIs | Other APIs |
|-------------------------|-----------------------|--------------------------------|
| [`Object`](#object) | [`WeakSet`](#weakset) | [`Fetch`](#fetch) |
| [`Array`](#array) | [`WeakMap`](#weakmap) | [`WebSocket`](#websocket) |
| [`String`](#string) | [`File`](#file) | [`CanvasRenderingContext2D`](#canvasrenderingcontext2d) |
| [`Number`](#number) | [`Blob`](#blob) | [`AudioContext`](#audiocontext) |
| [`Boolean`](#boolean) | [`FormData`](#formdata) | [`IntersectionObserver`](#intersectionobserver) |
| [`Function`](#function) | [`Window`](#window) | [`Intl`](#intl) |
| [`RegExp`](#regexp) | [`Document`](#document) | [`ServiceWorker`](#serviceworker) |
| [`Math`](#math) | [`LocalStorage and SessionStorage`](#localstorage-and-sessionstorage) | [`Storage`](#storage) |
| [`JSON`](#json) | [`Console`](#console) | [`URL`](#url) |
| [`Promise`](#promise) | [`Navigator`](#navigator) | |
| [`Set`](#set) | [`Geolocation`](#geolocation) | |
| [`Map`](#map) | [`XMLHttpRequest`](#xmlhttprequest) | |
 

 

### `Object`
- The base object from which most other objects inherit.
- Methods:
  - `Object.keys()`: Returns an array of a given object's own enumerable property names.
  - `Object.values()`: Returns an array of a given object's own enumerable property values.
  - `Object.entries()`: Returns an array of a given object's own enumerable string-keyed property `[key, value]` pairs.
  - `Object.assign()`: Copies all enumerable own properties from one or more source objects to a target object.
  - `Object.freeze()`: Freezes an object, preventing new properties from being added and existing properties from being modified.
  - `Object.seal()`: Seals an object, preventing new properties from being added but allows modification of existing properties.

### `Array`
- Used to store ordered collections of values.
- Methods:
  - `Array.push()`: Adds one or more elements to the end of an array.
  - `Array.pop()`: Removes the last element from an array.
  - `Array.shift()`: Removes the first element from an array.
  - `Array.unshift()`: Adds one or more elements to the beginning of an array.
  - `Array.slice()`: Returns a shallow copy of a portion of an array into a new array object.
  - `Array.splice()`: Adds or removes elements from an array at a specific index.
  - `Array.map()`: Creates a new array populated with the results of calling a provided function on every element in the array.
  - `Array.filter()`: Creates a new array with all elements that pass the test implemented by the provided function.
  - `Array.reduce()`: Executes a reducer function on each element of the array to reduce it to a single value.
  - `Array.forEach()`: Executes a provided function once for each array element.

```js

// Initial Array
const numbers = [1, 2, 3, 4, 5];

// 1. Array.push() - Adds an element at the end of the array
numbers.push(6);
console.log(numbers); 
// Output: [1, 2, 3, 4, 5, 6]

// 2. Array.pop() - Removes the last element from the array
numbers.pop();
console.log(numbers); 
// Output: [1, 2, 3, 4, 5]

// 3. Array.unshift() - Adds an element at the beginning of the array
numbers.unshift(0);
console.log(numbers); 
// Output: [0, 1, 2, 3, 4, 5]

// 4. Array.shift() - Removes the first element from the array
numbers.shift();
console.log(numbers); 
// Output: [1, 2, 3, 4, 5]

// 5. Array.slice() - Returns a shallow copy of a portion of an array
const slicedNumbers = numbers.slice(1, 4);
console.log(slicedNumbers); 
// Output: [2, 3, 4]

// 6. Array.map() - Creates a new array with the results of calling a function for every array element
const doubledNumbers = numbers.map(num => num * 2);
console.log(doubledNumbers); 
// Output: [2, 4, 6, 8, 10]

// 7. Array.filter() - Creates a new array with all elements that pass the test
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); 
// Output: [2, 4]

// 8. Array.find() - Returns the first element that satisfies the condition
const foundNumber = numbers.find(num => num > 3);
console.log(foundNumber); 
// Output: 4

// 9. Array.forEach() - Executes a provided function once for each array element
numbers.forEach(num => console.log(num));
// Output: 
// 1
// 2
// 3
// 4
// 5

// 10. Array.includes() - Checks if the array contains a certain element
const hasThree = numbers.includes(3);
console.log(hasThree); 
// Output: true
 
```

```js
// Creating an array object using the Array constructor
const arrayObject = new Array(5);  // Creates an array with 5 empty slots
console.log(arrayObject);
// Output: [ <5 empty items> ]

// Using the Array constructor with values
const arrayWithValues = new Array(1, 2, 3, 4, 5);
console.log(arrayWithValues);
// Output: [1, 2, 3, 4, 5]

// 1. Array.isArray() - Checks if an object is an array
console.log(Array.isArray(arrayObject)); 
// Output: true

console.log(Array.isArray({})); 
// Output: false

// 2. Array.concat() - Merges two or more arrays
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const mergedArray = array1.concat(array2);
console.log(mergedArray);
// Output: [1, 2, 3, 4, 5, 6]

// 3. Array.join() - Joins all elements of an array into a string
const joinedString = arrayWithValues.join('-');
console.log(joinedString);
// Output: "1-2-3-4-5"

// 4. Array.reverse() - Reverses the order of elements in an array
const reversedArray = arrayWithValues.reverse();
console.log(reversedArray);
// Output: [5, 4, 3, 2, 1]

// 5. Array.sort() - Sorts the elements of an array in place
const unsortedArray = [5, 2, 8, 1, 3];
unsortedArray.sort((a, b) => a - b);  // Sorting numerically
console.log(unsortedArray);
// Output: [1, 2, 3, 5, 8]

// 6. Array.fill() - Changes all elements in an array to a static value
const filledArray = new Array(5).fill(0);
console.log(filledArray);
// Output: [0, 0, 0, 0, 0]

// 7. Array.slice() - Returns a shallow copy of a portion of an array
const slicedArray = arrayWithValues.slice(1, 3); 
console.log(slicedArray);
// Output: [4, 3]

// 8. Array.find() - Returns the first element that satisfies the condition
const foundValue = arrayWithValues.find(value => value > 3);
console.log(foundValue);
// Output: 4

// 9. Array.map() - Creates a new array with the results of calling a function for every array element
const squaredValues = arrayWithValues.map(value => value * value);
console.log(squaredValues);
// Output: [25, 16, 9, 4, 1]

// 10. Array.filter() - Creates a new array with all elements that pass the test
const evenValues = arrayWithValues.filter(value => value % 2 === 0);
console.log(evenValues);
// Output: [4, 2]


```


### `String`
- Used to handle and manipulate text data.
- Methods:
  - `String.length`: Returns the length of the string.
  - `String.charAt()`: Returns the character at a specific index.
  - `String.indexOf()`: Returns the index of the first occurrence of a specified value.
  - `String.slice()`: Extracts a section of a string and returns a new string.
  - `String.split()`: Splits a string into an array of substrings based on a separator.
  - `String.replace()`: Returns a new string with some part of the string replaced by a new substring.
  - `String.toLowerCase()`: Converts a string to lowercase.
  - `String.toUpperCase()`: Converts a string to uppercase.
  - `String.trim()`: Removes whitespace from both ends of a string.

```js
// 1. Creating a string object
const str = "Hello, JavaScript!";
console.log(str);
// Output: "Hello, JavaScript!"

// 2. String.length - Returns the length of the string
console.log(str.length);
// Output: 19

// 3. String.charAt() - Returns the character at a specified index
console.log(str.charAt(0));
// Output: "H"

console.log(str.charAt(7));
// Output: "J"

// 4. String.indexOf() - Returns the index of the first occurrence of a specified value
console.log(str.indexOf("JavaScript"));
// Output: 7

console.log(str.indexOf("Python"));
// Output: -1 (not found)

// 5. String.slice() - Extracts a section of the string and returns it as a new string
console.log(str.slice(0, 5));
// Output: "Hello"

console.log(str.slice(7));
// Output: "JavaScript!"

// 6. String.replace() - Replaces a specified value with another value
console.log(str.replace("JavaScript", "World"));
// Output: "Hello, World!"

// 7. String.toUpperCase() - Converts the string to uppercase
console.log(str.toUpperCase());
// Output: "HELLO, JAVASCRIPT!"

// 8. String.toLowerCase() - Converts the string to lowercase
console.log(str.toLowerCase());
// Output: "hello, javascript!"

// 9. String.split() - Splits the string into an array of substrings
const words = str.split(" ");
console.log(words);
// Output: ["Hello,", "JavaScript!"]

// 10. String.trim() - Removes whitespace from both ends of the string
const strWithSpaces = "  Hello, World!  ";
console.log(strWithSpaces.trim());
// Output: "Hello, World!"

// 11. String.includes() - Checks if a substring exists within the string
console.log(str.includes("JavaScript"));
// Output: true

console.log(str.includes("Python"));
// Output: false

// 12. String.repeat() - Repeats the string a given number of times
console.log("Hello ".repeat(3));
// Output: "Hello Hello Hello "

// 13. String.split() - Splits the string into an array of substrings
const sentence = "The quick brown fox jumps over the lazy dog.";
const wordsArray = sentence.split(" ");
console.log(wordsArray);
// Output: ["The", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog."]

```


```js

// 1. Creating a String Object
const str = new String("Hello, JavaScript!");
console.log(str);
// Output: [String: 'Hello, JavaScript!']

// 2. String.length - Returns the length of the string
console.log(str.length);
// Output: 19

// 3. String.charAt() - Returns the character at a specified index
console.log(str.charAt(0));
// Output: "H"

console.log(str.charAt(7));
// Output: "J"

// 4. String.indexOf() - Returns the index of the first occurrence of a specified value
console.log(str.indexOf("JavaScript"));
// Output: 7

console.log(str.indexOf("Python"));
// Output: -1 (not found)

// 5. String.slice() - Extracts a section of the string and returns it as a new string
console.log(str.slice(0, 5));
// Output: "Hello"

console.log(str.slice(7));
// Output: "JavaScript!"

// 6. String.replace() - Replaces a specified value with another value
console.log(str.replace("JavaScript", "World"));
// Output: "Hello, World!"

// 7. String.toUpperCase() - Converts the string to uppercase
console.log(str.toUpperCase());
// Output: "HELLO, JAVASCRIPT!"

// 8. String.toLowerCase() - Converts the string to lowercase
console.log(str.toLowerCase());
// Output: "hello, javascript!"

// 9. String.split() - Splits the string into an array of substrings
const words = str.split(" ");
console.log(words);
// Output: ["Hello,", "JavaScript!"]

// 10. String.trim() - Removes whitespace from both ends of the string
const strWithSpaces = new String("  Hello, World!  ");
console.log(strWithSpaces.trim());
// Output: "Hello, World!"

// 11. String.includes() - Checks if a substring exists within the string
console.log(str.includes("JavaScript"));
// Output: true

console.log(str.includes("Python"));
// Output: false

// 12. String.repeat() - Repeats the string a given number of times
console.log("Hello ".repeat(3));
// Output: "Hello Hello Hello "

// 13. String.split() - Splits the string into an array of substrings
const sentence = "The quick brown fox jumps over the lazy dog.";
const wordsArray = sentence.split(" ");
console.log(wordsArray);
// Output: ["The", "quick", "brown", "fox", "jumps", "over", "the", "lazy", "dog."]

```



### `Number`
- Used to represent and work with numeric values.
- Methods:
  - `Number.toFixed()`: Formats a number using fixed-point notation.
  - `Number.toPrecision()`: Formats a number to a specified precision.
  - `Number.isNaN()`: Determines whether a value is NaN.
  - `Number.parseInt()`: Parses a string and returns an integer.
  - `Number.parseFloat()`: Parses a string and returns a floating-point number.


```js
// 1. Creating a number
const num = 42;
console.log(num);
// Output: 42

// 2. Using Number.toString() to convert the number to a string
console.log(num.toString());
// Output: "42"

// 3. Using Number.toFixed() to fix decimal places
const decimalNum = 12.34567;
console.log(decimalNum.toFixed(2));
// Output: "12.35"

// 4. Using Number.isInteger() to check if it's an integer
console.log(Number.isInteger(num));
// Output: true

// 5. Using Number.parseInt() to convert a string to an integer
const str = "123abc";
console.log(Number.parseInt(str));
// Output: 123

// 6. Using Number.parseFloat() to convert a string to a floating-point number
const strFloat = "123.45abc";
console.log(Number.parseFloat(strFloat));
// Output: 123.45


```

```js

// 1. Creating a Number Object
const num = new Number(42);
console.log(num);
// Output: [Number: 42]

// 2. Number.toString() - Converts a number to a string
console.log(num.toString());
// Output: "42"

// 3. Number.toFixed() - Formats a number to a fixed number of decimals
const decimalNum = 12.34567;
console.log(decimalNum.toFixed(2));
// Output: "12.35"

// 4. Number.toPrecision() - Formats a number to a specified length
console.log(decimalNum.toPrecision(4));
// Output: "12.35"

// 5. Number.isInteger() - Checks if the number is an integer
console.log(Number.isInteger(num));
// Output: true

console.log(Number.isInteger(decimalNum));
// Output: false

// 6. Number.isNaN() - Checks if the value is NaN (Not-a-Number)
console.log(Number.isNaN("hello"));
// Output: false

console.log(Number.isNaN(NaN));
// Output: true

// 7. Number.parseInt() - Converts a string to an integer
console.log(Number.parseInt("123abc"));
// Output: 123

// 8. Number.parseFloat() - Converts a string to a floating-point number
console.log(Number.parseFloat("123.45abc"));
// Output: 123.45

// 9. Number.isFinite() - Checks if the value is a finite number
console.log(Number.isFinite(100));
// Output: true

console.log(Number.isFinite(Infinity));
// Output: false

// 10. Number.MAX_VALUE - Represents the largest positive number that can be represented
console.log(Number.MAX_VALUE);
// Output: 1.7976931348623157e+308

// 11. Number.MIN_VALUE - Represents the smallest positive number that can be represented
console.log(Number.MIN_VALUE);
// Output: 5e-324

// 12. Number.EPSILON - The smallest interval between two representable numbers
console.log(Number.EPSILON);
// Output: 2.220446049250313e-16

// 13. Math.random() - Generates a random number between 0 (inclusive) and 1 (exclusive)
console.log(Math.random());
// Output: A random number, e.g., 0.9736

// 14. Math.round() - Rounds a number to the nearest integer
const roundNum = 7.89;
console.log(Math.round(roundNum));
// Output: 8

// 15. Math.max() - Returns the largest of the numbers
console.log(Math.max(1, 5, 3, 8, 2));
// Output: 8

// 16. Math.min() - Returns the smallest of the numbers
console.log(Math.min(1, 5, 3, 8, 2));
// Output: 1


```


### `Boolean`
- Represents true or false values.
- Methods:
  - `Boolean(value)`: Converts a value to a Boolean.

```js
// 1. Creating boolean values
const isTrue = true;
const isFalse = false;
console.log(isTrue); // Output: true
console.log(isFalse); // Output: false

// 2. Using Boolean() constructor to convert values to boolean
console.log(Boolean(1));   // Output: true (non-zero numbers are true)
console.log(Boolean(0));   // Output: false (0 is false)
console.log(Boolean(""));  // Output: false (empty string is false)
console.log(Boolean("Hello")); // Output: true (non-empty string is true)
console.log(Boolean(null)); // Output: false (null is false)

// 3. Using logical NOT ( ! ) to invert boolean values
console.log(!isTrue); // Output: false
console.log(!isFalse); // Output: true

// 4. Using logical AND ( && ) with booleans
console.log(isTrue && isFalse); // Output: false (because one of them is false)

// 5. Using logical OR ( || ) with booleans
console.log(isTrue || isFalse); // Output: true (because one of them is true)


```

```js

// 1. Creating a Boolean object
const boolObj1 = new Boolean(true);
const boolObj2 = new Boolean(false);

console.log(boolObj1); // Output: [Boolean: true]
console.log(boolObj2); // Output: [Boolean: false]

// 2. Using the Boolean object's valueOf() method to retrieve the primitive value
console.log(boolObj1.valueOf()); // Output: true
console.log(boolObj2.valueOf()); // Output: false

// 3. Converting other values to Boolean object using new Boolean()
const boolFromZero = new Boolean(0);
const boolFromString = new Boolean("Hello");

console.log(boolFromZero.valueOf());  // Output: false (because 0 is falsy)
console.log(boolFromString.valueOf()); // Output: true (non-empty string is truthy)

// 4. Checking if the Boolean object is truthy or falsy (in a conditional)
if (boolObj1) {
    console.log("boolObj1 is truthy"); // Output: boolObj1 is truthy
}

if (!boolObj2) {
    console.log("boolObj2 is falsy"); // Output: boolObj2 is falsy
}


```


### `Function`
- Represents a function that can be invoked.
- Methods:
  - `Function.call()`: Calls a function with a specified `this` value and arguments.
  - `Function.apply()`: Calls a function with a specified `this` value and arguments as an array.
  - `Function.bind()`: Creates a new function that, when invoked, has its `this` set to a specified value.

```js
// 1. Defining a function using function declaration
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Mamun")); // Output: Hello, Mamun!

// 2. Defining a function using function expression (Anonymous function)
const sum = function(a, b) {
  return a + b;
};

console.log(sum(5, 3)); // Output: 8

// 3. Defining a function using an arrow function
const multiply = (a, b) => a * b;

console.log(multiply(4, 2)); // Output: 8

// 4. Using the Function constructor to create a function dynamically
const subtract = new Function("a", "b", "return a - b;");

console.log(subtract(10, 4)); // Output: 6

// 5. Using call() method to invoke a function with a specific context
function greetPerson() {
  return `Hello, ${this.name}!`;
}

const person = { name: "Mamun" };
console.log(greetPerson.call(person)); // Output: Hello, Mamun!

// 6. Using bind() method to bind a function to a specific context
const greetPersonBound = greetPerson.bind(person);
console.log(greetPersonBound()); // Output: Hello, Mamun!

```


```js

// 1. Creating a function using the Function constructor
const greet = new Function('name', 'return `Hello, ${name}!`;');

console.log(greet("Mamun")); // Output: Hello, Mamun!

// 2. Using Function object's 'toString()' method to get the function's string representation
const functionStr = greet.toString();
console.log(functionStr); // Output: function anonymous(name) { return `Hello, ${name}!`; }

// 3. Using Function object's 'apply()' method to invoke the function with a specific context
function introduce(name, age) {
    return `${this.greeting}, my name is ${name} and I am ${age} years old.`;
}

const person = { greeting: "Hi" };
console.log(introduce.apply(person, ["Mamun", 25])); // Output: Hi, my name is Mamun and I am 25 years old.

// 4. Using Function object's 'bind()' method to create a new function bound to a specific context
const boundIntroduce = introduce.bind(person);
console.log(boundIntroduce("Mamun", 25)); // Output: Hi, my name is Mamun and I am 25 years old.


// Hello, Mamun!
// function anonymous(name) { return `Hello, ${name}!`; }
// Hi, my name is Mamun and I am 25 years old.
// Hi, my name is Mamun and I am 25 years old.


```

### `Date`
- Used to work with dates and times.
- Methods:
  - `Date.now()`: Returns the current time in milliseconds since January 1, 1970.
  - `Date.getDate()`: Returns the day of the month (from 1 to 31).
  - `Date.getMonth()`: Returns the month (from 0 to 11).
  - `Date.getFullYear()`: Returns the year (four digits).
  - `Date.setFullYear()`: Sets the year of a specified date.


```js

// 1. Creating a Date object representing the current date and time
const currentDate = new Date();
console.log(currentDate); // Output: Current date and time, e.g. "Sat Feb 03 2025 10:30:45 GMT+0000 (Coordinated Universal Time)"

// 2. Creating a Date object with a specific date
const specificDate = new Date("2025-02-03");
console.log(specificDate); // Output: Mon Feb 03 2025 00:00:00 GMT+0000 (Coordinated Universal Time)

// 3. Getting the current year, month, day, hour, minute, second
const year = currentDate.getFullYear();
const month = currentDate.getMonth() + 1; // Months are 0-indexed
const day = currentDate.getDate();
const hour = currentDate.getHours();
const minute = currentDate.getMinutes();
const second = currentDate.getSeconds();

console.log(`Year: ${year}, Month: ${month}, Day: ${day}, Time: ${hour}:${minute}:${second}`);
// Output: Year: 2025, Month: 2, Day: 3, Time: 10:30:45

// 4. Setting a specific date and time
currentDate.setFullYear(2023);
currentDate.setMonth(5); // June (Months are 0-indexed)
currentDate.setDate(15);
console.log(currentDate); // Output: Thu Jun 15 2023 10:30:45 GMT+0000 (Coordinated Universal Time)

// 5. Getting the timestamp (milliseconds since January 1, 1970)
const timestamp = currentDate.getTime();
console.log(timestamp); // Output: 1686817845000 (example, this is the timestamp for the specific date)


```


### `RegExp`
- Represents regular expressions for pattern matching.
- Methods:
  - `RegExp.test()`: Tests whether a pattern exists in a string.
  - `RegExp.exec()`: Executes a search for a match in a string and returns an array of results.

```js

// 1. Creating a RegExp object using a regular expression pattern
const regex = new RegExp("hello", "i"); // 'i' is the flag for case-insensitive matching
console.log(regex); // Output: /hello/i

// 2. Using RegExp to test if a string matches the pattern
const text1 = "Hello World!";
const text2 = "Goodbye World!";
console.log(regex.test(text1)); // Output: true (matches "hello" case-insensitively)
console.log(regex.test(text2)); // Output: false (does not match "hello")

// 3. Using RegExp to find matches in a string
const match = text1.match(regex);
console.log(match); // Output: ["Hello"] (returns an array of matched strings)

// 4. Using RegExp to replace a substring in a string
const replacedText = text1.replace(regex, "Hi");
console.log(replacedText); // Output: "Hi World!" (replaces "Hello" with "Hi")

// 5. Using RegExp with global flag to find all matches
const globalRegex = new RegExp("o", "g"); // 'g' is the global flag
const globalMatches = text1.match(globalRegex);
console.log(globalMatches); // Output: ["o", "o"] (matches every "o" in the string)

// 6. Using RegExp to split a string
const splitText = "apple,banana,orange".split(new RegExp(","));
console.log(splitText); // Output: ["apple", "banana", "orange"] (splits the string by commas)

```



### `Math`
- Provides mathematical constants and functions (e.g., `Math.random()`, `Math.max()`).
- Methods:
  - `Math.random()`: Returns a random number between 0 (inclusive) and 1 (exclusive).
  - `Math.max()`: Returns the largest of zero or more numbers.
  - `Math.min()`: Returns the smallest of zero or more numbers.
  - `Math.round()`: Returns the value of a number rounded to the nearest integer.
 
```js
// 1. Math.abs() - Returns the absolute value of a number
const number1 = -5;
console.log(Math.abs(number1)); // Output: 5

// 2. Math.round() - Rounds a number to the nearest integer
const number2 = 4.6;
console.log(Math.round(number2)); // Output: 5

// 3. Math.floor() - Rounds a number down to the nearest integer
const number3 = 4.6;
console.log(Math.floor(number3)); // Output: 4

// 4. Math.ceil() - Rounds a number up to the nearest integer
const number4 = 4.2;
console.log(Math.ceil(number4)); // Output: 5

// 5. Math.max() - Returns the largest of the given numbers
const number5 = 1, number6 = 5, number7 = 3;
console.log(Math.max(number5, number6, number7)); // Output: 5

// 6. Math.min() - Returns the smallest of the given numbers
console.log(Math.min(number5, number6, number7)); // Output: 1

// 7. Math.random() - Returns a random number between 0 and 1
const randomNumber = Math.random();
console.log(randomNumber); // Output: A random number like 0.123456789

// 8. Math.pow() - Returns the base to the exponent power (base^exponent)
const base = 2, exponent = 3;
console.log(Math.pow(base, exponent)); // Output: 8

// 9. Math.sqrt() - Returns the square root of a number
const number8 = 16;
console.log(Math.sqrt(number8)); // Output: 4

// 10. Math.PI - Returns the value of Pi
console.log(Math.PI); // Output: 3.141592653589793

// 11. Math.E - Returns the value of Euler's number (e)
console.log(Math.E); // Output: 2.718281828459045

```

### `JSON`
- Used to work with JSON data (e.g., `JSON.parse()`, `JSON.stringify()`).
- Methods:
  - `JSON.parse()`: Converts a JSON string into an object.
  - `JSON.stringify()`: Converts a JavaScript object into a JSON string.


```js

// 1. JSON.stringify() - Converts a JavaScript object to a JSON string
const person = {
    name: "Mamun",
    age: 30,
    city: "Dhaka"
};

const jsonString = JSON.stringify(person);
console.log(jsonString); 
// Output: '{"name":"Mamun","age":30,"city":"Dhaka"}'

// 2. JSON.parse() - Converts a JSON string back into a JavaScript object
const jsonResponse = '{"name":"Mamun","age":30,"city":"Dhaka"}';
const parsedObject = JSON.parse(jsonResponse);
console.log(parsedObject); 
// Output: { name: 'Mamun', age: 30, city: 'Dhaka' }

// 3. Using JSON.stringify with formatting options (pretty print)
const jsonStringPretty = JSON.stringify(person, null, 4);
console.log(jsonStringPretty);
// Output:
// {
//     "name": "Mamun",
//     "age": 30,
//     "city": "Dhaka"
// }

// 4. JSON.stringify with a replacer function
const jsonStringReplacer = JSON.stringify(person, (key, value) => {
    if (key === "age") {
        return undefined; // Exclude age from the JSON output
    }
    return value;
});
console.log(jsonStringReplacer); 
// Output: '{"name":"Mamun","city":"Dhaka"}'

```



### `Promise`
- Used for handling asynchronous operations (e.g., `.then()`, `.catch()`).
- Methods:
  - `Promise.then()`: Adds a callback to be executed when the promise resolves.
  - `Promise.catch()`: Adds a callback to be executed when the promise is rejected.
  - `Promise.all()`: Returns a single Promise that resolves when all promises in the array are resolved.


```js

// 1. Basic Promise Example: Handling success (resolve) and failure (reject)
const myPromise = new Promise((resolve, reject) => {
    const success = true; // Change this to false to see the reject case
    
    if (success) {
        resolve("Operation succeeded!");
    } else {
        reject("Operation failed.");
    }
});

myPromise
    .then((message) => {
        console.log(message); // Output if resolved
    })
    .catch((error) => {
        console.log(error); // Output if rejected
    });
// Output: "Operation succeeded!" (if success is true)
// Or Output: "Operation failed." (if success is false)

// 2. Chaining multiple promises
const promise1 = new Promise((resolve) => {
    setTimeout(() => resolve("First operation completed."), 1000);
});

const promise2 = new Promise((resolve) => {
    setTimeout(() => resolve("Second operation completed."), 500);
});

promise1
    .then((message) => {
        console.log(message); // Output: "First operation completed."
        return promise2;
    })
    .then((message) => {
        console.log(message); // Output: "Second operation completed."
    });

// 3. Promise.all: Waiting for multiple promises to resolve
const promise3 = new Promise((resolve) => {
    setTimeout(() => resolve("Third operation completed."), 2000);
});

Promise.all([promise1, promise2, promise3])
    .then((messages) => {
        console.log("All promises resolved:", messages); 
        // Output: All promises resolved: [ 'First operation completed.', 'Second operation completed.', 'Third operation completed.' ]
    })
    .catch((error) => {
        console.log("Error:", error);
    });

```

<h6>

Why use Promises in JavaScript?<br>
Promises in JavaScript are a powerful feature for handling asynchronous operations in a cleaner and more manageable way. Here are the primary reasons why you should use Promises:<br>

1. Handling Asynchronous Code <br>
In JavaScript, many tasks are asynchronous, such as fetching data from a server, reading files, or interacting with APIs. Without promises, handling these asynchronous tasks using callbacks can lead to "callback hell" or "pyramid of doom," making the code harder to read and maintain.<br>

Example of callback hell:<br>
</h6>

```js
fs.readFile('file1.txt', 'utf8', function(err, data1) {
    if (err) throw err;
    fs.readFile('file2.txt', 'utf8', function(err, data2) {
        if (err) throw err;
        fs.readFile('file3.txt', 'utf8', function(err, data3) {
            if (err) throw err;
            console.log(data1, data2, data3);
        });
    });
});

```

<h6>
This nesting can quickly become very complex. <br>

Promises simplify the above code:<br>
</h6>

```js
readFile('file1.txt', 'utf8')
    .then(data1 => readFile('file2.txt', 'utf8'))
    .then(data2 => readFile('file3.txt', 'utf8'))
    .then(data3 => console.log(data1, data2, data3))
    .catch(error => console.error('Error:', error));

```

<h6>
  2. Better Code Readability and Maintainability <br>
Promises allow you to write asynchronous code in a way that resembles synchronous code, making it easier to read and follow the logic. You can chain .then() methods to handle each asynchronous step, and .catch() to handle any errors. <br>

Example: Fetching data with fetch and handling it in a more readable way: <br>
</h6>



```js
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

```
 




### `Set`
- Represents a collection of unique values (ES6).
- Methods:
  - `Set.add()`: Adds a new element to the Set.
  - `Set.delete()`: Removes an element from the Set.
  - `Set.has()`: Checks if a value exists in the Set.
  - `Set.size`: Returns the number of elements in the Set.
 
```js
// Creating a new Set
const uniqueNumbers = new Set();

// Adding values to the Set
uniqueNumbers.add(10);
uniqueNumbers.add(20);
uniqueNumbers.add(30);
uniqueNumbers.add(10);  // Duplicate, won't be added

// Displaying the Set
console.log(uniqueNumbers);  // Output: Set { 10, 20, 30 }

// Checking the size of the Set
console.log("Set size:", uniqueNumbers.size);  // Output: Set size: 3

// Checking if a value exists in the Set
console.log(uniqueNumbers.has(20));  // Output: true
console.log(uniqueNumbers.has(100)); // Output: false

// Removing a value from the Set
uniqueNumbers.delete(20);
console.log(uniqueNumbers);  // Output: Set { 10, 30 }

// Clearing all values from the Set
uniqueNumbers.clear();
console.log(uniqueNumbers);  // Output: Set {}

```

### `Map`
- Represents key-value pairs, similar to an object but with more flexible key types (ES6).
- Methods:
  - `Map.set()`: Adds a new key-value pair to the Map.
  - `Map.get()`: Returns the value for a given key.
  - `Map.has()`: Checks if a key exists in the Map.
  - `Map.delete()`: Removes a key-value pair from the Map.
 
```js
// Creating a new Map
const personMap = new Map();

// Adding key-value pairs to the Map
personMap.set("name", "Mamun");
personMap.set("age", 25);
personMap.set("profession", "Developer");
personMap.set("city", "Dhaka");

// Displaying the Map
console.log(personMap);  
// Output: Map { 'name' => 'Mamun', 'age' => 25, 'profession' => 'Developer', 'city' => 'Dhaka' }

// Getting a value by its key
console.log(personMap.get("name"));  // Output: Mamun
console.log(personMap.get("age"));   // Output: 25

// Checking if a key exists
console.log(personMap.has("profession")); // Output: true
console.log(personMap.has("country"));    // Output: false

// Removing a key-value pair
personMap.delete("city");
console.log(personMap);  
// Output: Map { 'name' => 'Mamun', 'age' => 25, 'profession' => 'Developer' }

// Iterating over the Map using forEach
personMap.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
// Output:
// name: Mamun
// age: 25
// profession: Developer

// Getting the size of the Map
console.log("Map size:", personMap.size);  // Output: Map size: 3

// Clearing all the entries from the Map
personMap.clear();
console.log(personMap);  // Output: Map {}


```

### `WeakSet`
- Like `Set`, but allows garbage collection of its values (ES6).
- Methods:
  - `WeakSet.add()`: Adds an object to the WeakSet.
  - `WeakSet.has()`: Checks if an object exists in the WeakSet.

```js
// Creating a new WeakSet
const weakset = new WeakSet();

// Creating objects
const obj1 = { name: "Mamun" };
const obj2 = { name: "Sami" };

// Adding objects to the WeakSet
weakset.add(obj1);
weakset.add(obj2);

// Displaying the WeakSet (Direct output will be empty, as WeakSet has no iterator)
console.log(weakset);  // Output: WeakSet { <items unknown> }

// Checking if an object is in the WeakSet
console.log(weakset.has(obj1)); // Output: true
console.log(weakset.has(obj2)); // Output: true

// Removing an object from the WeakSet
weakset.delete(obj2);
console.log(weakset.has(obj2)); // Output: false

// Objects in the WeakSet will be garbage collected once no references exist
// Note: You can't directly iterate over the WeakSet or get its size

```



### `WeakMap`
- Like `Map`, but allows garbage collection of its keys (ES6).
- Methods:
  - `WeakMap.set()`: Adds a new key-value pair.
  - `WeakMap.get()`: Retrieves the value for a given key.

```js

// Creating a new WeakMap
const weakMap = new WeakMap();

// Creating objects to be used as keys
const obj1 = { name: "Mamun" };
const obj2 = { name: "Sami" };

// Adding key-value pairs to the WeakMap
weakMap.set(obj1, "Developer");
weakMap.set(obj2, "Designer");

// Retrieving values using keys
console.log(weakMap.get(obj1)); // Output: Developer
console.log(weakMap.get(obj2)); // Output: Designer

// Checking if a key exists in the WeakMap
console.log(weakMap.has(obj1)); // Output: true
console.log(weakMap.has(obj2)); // Output: true

// Deleting a key-value pair from the WeakMap
weakMap.delete(obj2);
console.log(weakMap.has(obj2)); // Output: false

// Example: The key objects can be garbage collected when there are no other references to them


```

### `Error`
- Used to represent runtime errors.
- Methods:
  - `Error.message`: Returns the error message.
  - `Error.name`: Returns the name of the error.

```js
// Example of throwing and catching an Error

try {
    // Throwing a custom error
    throw new Error("Something went wrong!");
} catch (error) {
    // Catching and logging the error
    console.log(error.name); // Output: Error
    console.log(error.message); // Output: Something went wrong!
    console.log(error.stack);  // Output: (stack trace)
}

// Example with custom Error object
try {
    throw new Error("Invalid Input");
} catch (error) {
    console.log(error.name);    // Output: Error
    console.log(error.message); // Output: Invalid Input
}
 
```



### `File`
- Represents files in the browser (typically for file uploads).
- Methods:
  - `File.name`: Returns the file name.
  - `File.size`: Returns the file size.
  - `File.type`: Returns the file type.
 

```html

<!-- HTML File Input -->
<input type="file" id="fileInput">

```

```js
// JavaScript to handle File Object
document.getElementById("fileInput").addEventListener("change", function(event) {
    const file = event.target.files[0]; // Access the selected file
    if (file) {
        console.log("File Name:", file.name);          // Output: Example.txt
        console.log("File Type:", file.type);          // Output: text/plain
        console.log("File Size:", file.size);          // Output: 12345 (size in bytes)
        console.log("File Last Modified:", file.lastModified); // Output: 1617867226000 (timestamp)
    }
});

```

### `Blob`
- Represents binary data.
- Methods:
  - `Blob.slice()`: Creates a new `Blob` object containing a portion of the original blob's data.

<h6>
  Blob Object Example in JavaScript <br>
  
The Blob object represents immutable raw binary data, typically used for handling file-like objects in the browser (such as images, video files, etc.). It can be used to work with data streams, for example, in file uploads or downloading files.
</h6>

```js
// Create a Blob object from text data
const textData = "Hello, Blob!";
const blob = new Blob([textData], { type: "text/plain" });

// Create a URL for the Blob object
const blobUrl = URL.createObjectURL(blob);

// Display the Blob URL
console.log("Blob URL:", blobUrl);

// Example of downloading the Blob as a file
const link = document.createElement("a");
link.href = blobUrl;
link.download = "example.txt"; // Suggests a file name for download
link.click(); 
```
<h6>
Explanation: <br>
A Blob object is created using the constructor new Blob(). The first argument is an array of data (such as a string, or binary data), and the second argument is an options object where we specify the MIME type (text/plain in this case). <br>
URL.createObjectURL(blob) creates a temporary URL representing the Blob object. <br>
We use this URL to trigger a file download by creating a link (<a>), setting its href to the Blob URL, and programmatically clicking it. <br>
</h6>


### `FormData`
- Represents form data to be sent in HTTP requests (e.g., in AJAX requests).
- Methods:
  - `append(name, value)`: Adds a new field (allows duplicates).
  - `set(name, value)`: Adds or replaces a field.
  - `get(name)`: Returns the first value of a field.
  - `getAll(name)`: Returns all values of a field as an array.
  - `has(name)`: Checks if a field exists.
  - `delete(name)`: Removes a field.
  - `entries()`: Returns all key-value pairs.
  - `keys()`: Returns all field names.
  - `values()`: Returns all field values.
 
```js

<!-- Sample HTML form -->
<form id="myForm">
  <input type="text" name="username" value="Mamun">
  <input type="email" name="email" value="mamun@example.com">
  <input type="file" name="profile_picture" id="profile_picture">
  <button type="submit">Submit</button>
</form>

<script>
// Select the form element
const form = document.getElementById("myForm");

// Create a new FormData object from the form
const formData = new FormData(form);

// Append additional data manually (e.g., hobby)
formData.append("hobby", "coding");

// Accessing form data
console.log("Username:", formData.get("username")); // Output: "Mamun"
console.log("Email:", formData.get("email")); // Output: "mamun@example.com"
console.log("Hobby:", formData.get("hobby")); // Output: "coding"

// Get all field names (keys)
for (let key of formData.keys()) {
    console.log("Field name:", key);
}

// Get all field values
for (let value of formData.values()) {
    console.log("Field value:", value);
}

// Example of sending the FormData using fetch
fetch("https://example.com/api", {
    method: "POST",
    body: formData // Send FormData directly as body of request
})
.then(response => response.json())
.then(data => console.log("Response:", data))
.catch(error => console.error("Error:", error));
</script>

```

### `Window`
- Represents the global object for the browser's window.

### `Document`
- Represents the HTML document in the browser, used for DOM manipulation.

### `LocalStorage` and `SessionStorage`
- Provide client-side storage for web applications (persistent or session-based).

### `Console`
- Provides access to the browser's console for logging and debugging.

### `Navigator`
- Represents the browser’s state and environment (e.g., user agent, platform).
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Navigator Object Example</title>
</head>
<body>

    <h1>Navigator Object Example</h1>
    <button id="showNavigatorInfo">Show Navigator Info</button>

    <script>
        // Event listener for the button
        document.getElementById("showNavigatorInfo").addEventListener("click", function() {
            // Accessing navigator properties
            console.log("Browser Name:", navigator.appName);  // Browser name
            console.log("Browser Version:", navigator.appVersion);  // Browser version
            console.log("User Agent:", navigator.userAgent);  // User-Agent string
            console.log("Platform:", navigator.platform);  // Platform (Operating System)
            console.log("Language:", navigator.language);  // Language set in browser
            console.log("Online Status:", navigator.onLine ? "Online" : "Offline");  // Online status

            // Detecting if cookies are enabled
            console.log("Cookies Enabled:", navigator.cookieEnabled ? "Yes" : "No");  
        });
    </script>
</body>
</html>

```

<h6>
  Explanation: <br>
Navigator Properties: <br>
navigator.appName: Name of the browser (e.g., "Netscape" for most modern browsers). <br>
navigator.appVersion: The version information for the browser. <br>
navigator.userAgent: A string representing the browser and operating system. <br>
navigator.platform: The platform (operating system) the browser is running on. <br>
navigator.language: The browser's preferred language (e.g., "en-US" for English). <br>
navigator.onLine: Indicates whether the browser is online or offline. <br>
navigator.cookieEnabled: Indicates whether cookies are enabled in the browser. <br>
</h6>

<h6>

  Browser Name: Netscape  // Modern browsers usually report as 'Netscape' <br>
Browser Version: 5.0 (Windows)  // Browser version (varies based on browser) <br>
User Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36  // Complete user-agent string <br>
Platform: Win32  // Operating system/platform <br>
Language: en-US  // The language set in the browser (e.g., English - US) <br>
Online Status: Online  // Online status (this will be 'Online' if the browser is connected to the internet) <br>
Cookies Enabled: Yes  // Whether cookies are enabled in the browser <br>

</h6>


### `Geolocation`
- Allows access to the user's geographic location.

### `XMLHttpRequest`
- Used for making HTTP requests (older alternative to `fetch()`).

### `Fetch`
- A modern alternative to `XMLHttpRequest` for making HTTP requests.
 
##### When making a fetch request, you can customize the operation using options in the second argument of fetch(). Here's a breakdown of common options:

- `method` : Specifies the HTTP request method (GET, POST, PUT, DELETE, etc.).
- `headers` : Allows you to set HTTP headers for the request.
- `body` : Specifies the body of the request (only for methods like POST, PUT, PATCH).
- `credentials` : Controls the inclusion of credentials (cookies, authorization headers, etc.) in the request.
- `cache` : Allows you to control how the request is cached.
- `mode` : Controls whether the request should be made using CORS (Cross-Origin Resource Sharing).
- `redirect` : Defines how the request handles redirects.
-  `referrer` : Specifies the referrer for the request.

<h6>
  
Basic Fetch Operation <br>
The basic fetch() method takes the URL of the resource you want to fetch and returns a Promise that resolves to the Response object. You can chain .then() to process the data or .catch() for error handling.
</h6>

```js
fetch(url)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

```

### Fetch Operations
- Used to send data to the server.
- You can send data using the body field, usually with JSON.

  
```js
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1
  })
})
.then(response => response.json())
.then(data => console.log('Created:', data))
.catch(error => console.error('Error:', error));

```
#### Example with Multiple Options
- Here’s a more complex fetch operation with multiple options:

 ```js
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST', // POST request
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1
  }),
  credentials: 'include', // Include cookies if needed
  cache: 'no-cache', // No caching
  redirect: 'follow' // Follow redirects
})
.then(response => response.json())
.then(data => console.log('Created:', data))
.catch(error => console.error('Error:', error));
```

#### Fetch with async/await (Modern approach)
- Instead of using .then() and .catch(), you can use async/await for cleaner, more readable code:

```js
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();

```


####  Fetch with Error Handling
- You can handle errors like network issues or invalid responses using the .catch() method, or with try/catch in an async function.

###### Example using try/catch with async/await:

```js
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1000');
    if (!response.ok) {
      throw new Error('Resource not found');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();

```

-To return the response value from an asynchronous fetch() operation, you can use the async/await syntax. Here’s how you can structure it:
-Example of Returning Response Value in Async Fetch 

```js
// Define an async function to fetch data
async function fetchData(url) {
  try {
    const response = await fetch(url);  // Wait for the fetch request to complete

    if (!response.ok) {  // Check if the response is successful
      throw new Error('Network response was not ok');
    }

    const data = await response.json();  // Parse the response as JSON
    return data;  // Return the parsed data

  } catch (error) {
    console.error('Error:', error);  // Handle any errors
    return null;  // Return null if there's an error
  }
}

// Call the async function and handle the returned data
async function run() {
  const data = await fetchData('https://jsonplaceholder.typicode.com/posts');
  console.log(data);  // Log the response data
}

run();

```
<h6> 
  
#### Breakdown:
- `fetchData(url)`: This is an asynchronous function that takes a URL, performs a fetch() request, and returns the parsed JSON response.
- `await fetch(url)`: The await keyword ensures that the code waits for the fetch operation to complete before moving on to the next line.
- `response.json()`: This parses the response as JSON.
- `return data`: The parsed data is returned from the fetchData function.
- `run()`: This function calls fetchData() and logs the result once the promise is resolved.
  
</h6>


### `WebSocket`
- Used for establishing a connection between the client and server for real-time communication.

### `CanvasRenderingContext2D`
- Provides methods to draw on `<canvas>` elements.

### `AudioContext`
- Used for processing audio in the browser.

### `IntersectionObserver`
- Used to monitor when an element enters or exits the viewport.

### `Intl`
- Provides internationalization and localization features (e.g., `Intl.NumberFormat`).

### `ServiceWorker`
- A script that runs in the background and can handle things like caching and push notifications.

---

## Specialized Objects

### `Storage`
- The base interface for `LocalStorage` and `SessionStorage`.

### `URL`
- Represents a URL and provides methods for manipulating URL components.

### `Navigator`
- Represents the browser's capabilities and environment, like user-agent and platform.
