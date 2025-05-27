# JavaScript Operators summary

<h6> 

| Operator	| Purpose	Example| 
|----------|-------------|
| ... (Spread) | 	Expands arrays/objects	[...arr]| 
| ... (Rest)| 	Collects multiple values	(...args) => {}| 
| {} {} (Destructuring)	| Extracts values from objects/arrays	const {name} = obj| 
| ?. (Optional Chaining)	| Safe property access	obj?.prop?.subProp| 
| ?? (Nullish Coalescing)	| Handles null & undefined	value ?? "default"| 
| ? : (Ternary)	| Short if-else	condition ? "Yes" : "No"| 
| \`		\` |  (Logical OR)| 
| && (Logical AND) | 	Conditional execution	isTrue && func()| 


 </h6>

<br>

## JavaScript Operators & Iteration Methods Description

## 1️⃣ Spread (`...`) & Rest (`...`) Operator

- **Spread (`...`)**: Expands arrays/objects.
- **Rest (`...`)**: Gathers values into an array.

### ✅ Spread Operator Example
```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];  
console.log(arr2); // [1, 2, 3, 4, 5]
```

### ✅ Rest Operator Example
```js
function sum(...nums) {  
  return nums.reduce((acc, num) => acc + num, 0);
}
console.log(sum(1, 2, 3)); // 6
```

---

## 2️⃣ Destructuring (`[]`, `{}`)
Used to extract values from arrays or objects.

### ✅ Array Destructuring Example
```js
const numbers = [10, 20, 30];
const [a, b] = numbers;
console.log(a, b); // 10, 20
```

### ✅ Object Destructuring Example
```js
const user = { name: "Alice", age: 25 };
const { name, age } = user;
console.log(name, age); // Alice 25
```

---

## 3️⃣ Optional Chaining (`?.`)
Used to safely access nested properties without errors.

### ✅ Example
```js
const user = { profile: { name: "Bob" } };
console.log(user?.profile?.name); // Bob
console.log(user?.address?.city); // undefined (No Error)
```

---

## 4️⃣ Nullish Coalescing (`??`)
Returns right-hand value if left-hand value is `null` or `undefined`.

### ✅ Example
```js
const name = null;
const defaultName = name ?? "Guest";  
console.log(defaultName); // Guest
```

---

## 5️⃣ Ternary Operator (`? :`)
Shorthand for `if-else` conditions.

### ✅ Example
```js
const age = 18;
const message = age >= 18 ? "Adult" : "Minor";
console.log(message); // Adult
```

---

## 6️⃣ Logical OR (`||`) & AND (`&&`)
Used for default values and conditional execution.

### ✅ OR (`||`) – Returns first truthy value
```js
const username = "" || "Guest";  
console.log(username); // Guest
```

### ✅ AND (`&&`) – Executes only if left side is true
```js
const isLoggedIn = true;
isLoggedIn && console.log("Welcome!"); // Welcome!