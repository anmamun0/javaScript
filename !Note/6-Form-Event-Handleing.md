# From Event handeling


### 📌 Most Common Event Properties

| Property                     | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| `event.target`              | The element that triggered the event (e.g., `<input>`)                      |
| `event.target.name`         | The `name` attribute of the triggering element                              |
| `event.target.value`        | The current value inside the input                                          |
| `event.type`                | Type of the event (e.g., `"click"`, `"change"`)                             |
| `event.preventDefault()`    | Stops the default browser behavior (e.g., page reload on form submit)       |
| `event.stopPropagation()`   | Prevents the event from bubbling up to parent elements                      |
| `event.nativeEvent`         | The original native browser event                                           |
| `event.currentTarget`       | The element the event handler is attached to (may differ from `target`)     |
| `event.bubbles`             | Boolean indicating if the event bubbles up the DOM tree                     |
| `event.isDefaultPrevented()`| Returns `true` if `preventDefault()` has been called                        |
| `event.persist()`           | Removes the event from React's synthetic pool so you can access it asynchronously |



```
<input name="email" value="mamun@gmail.com" onChange={handleChange} />
const handleChange = (event) => {
  console.log(event); // What will be printed?
};
```

✅ Output of console.log(event)
```js 
SyntheticBaseEvent {
  bubbles: true,               // Whether the event bubbles up through the DOM
  cancelable: true,            // Whether the default action can be prevented
  currentTarget: <input>,      // The element the event handler is attached to
  defaultPrevented: false,     // Whether preventDefault() has been called
  eventPhase: 2,               // At which phase the event is being processed (2 = at target)
  isTrusted: true,             // Whether the event is trusted (not synthetic)
  nativeEvent: InputEvent { ... }, // The real browser event object
  target: <input>,             // The actual element where the event occurred
  timeStamp: 123456.78,        // When the event was created
  type: "change",              // Type of event
  persist: ƒ(),                // Method to remove the event from the React pool (for async use)
  isDefaultPrevented: ƒ(),     // Method to check if preventDefault() was called
  isPropagationStopped: ƒ(),   // Method to check if stopPropagation() was called
  ...
}
```

## 🔍 Breakdown with Meaning

| Property                  | Meaning                                                                 |
|---------------------------|-------------------------------------------------------------------------|
| `bubbles`                | `true` if the event will bubble (move up) the DOM                        |
| `cancelable`             | `true` if you can call `preventDefault()` on the event                  |
| `currentTarget`          | The element that the event handler is attached to                       |
| `defaultPrevented`       | `true` if `preventDefault()` has been called                            |
| `eventPhase`             | Numeric phase: `1 = capturing`, `2 = target`, `3 = bubbling`            |
| `isTrusted`              | `true` if it’s a real user event (not triggered by JavaScript)          |
| `nativeEvent`            | The actual browser `InputEvent` or native DOM event                     |
| `target`                 | The element that triggered the event (e.g., `<input name="email" />`)   |
| `timeStamp`              | The time (in ms) the event occurred                                     |
| `type`                   | Type of the event (e.g., `"change"`, `"click"`)                         |
| `persist()`              | Keeps the synthetic event in memory for asynchronous use               |
| `isDefaultPrevented()`   | Returns `true` if `preventDefault()` was called                         |
| `isPropagationStopped()` | Returns `true` if `stopPropagation()` was called                        |










 

```jsx 
<input name="email" value={email} onChange={handleChange} />

//Let’s say you type: mamun@gmail.com
```

Now, here’s the code you shared again with expected output comments:

```js 
const handleChange = (event) => {
  console.log("🧾 event object:", event); 
  // 🧾 event object: SyntheticBaseEvent { 
  //   type: "change", 
  //   target: <input name="email" value="mamun@gmail.com" />, 
  //   ... 
  // }

  console.log("🔹 event.type:", event.type); 
  // 🔹 event.type: "change"

  console.log("🔹 event.target:", event.target); 
  // 🔹 event.target: <input name="email" value="mamun@gmail.com" />

  console.log("🔹 name:", event.target.name); 
  // 🔹 name: "email"

  console.log("🔹 value:", event.target.value); 
  // 🔹 value: "mamun@gmail.com"

  console.log("🔹 nativeEvent:", event.nativeEvent); 
  // 🔹 nativeEvent: InputEvent { 
  //   data: "m", 
  //   inputType: "insertText", 
  //   isComposing: false, 
  //   ... 
  // }

  console.log("🔹 bubbles:", event.bubbles); 
  // 🔹 bubbles: true
};


```


---



## Full List of Key SyntheticEvent Properties (With Use Cases)

<h6>

| Property / Method            | Meaning / Use Case                                                                                                                                   |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`bubbles`**                | `true` if the event bubbles up the DOM.<br>🧪 Use Case: Checking whether a `click` event should trigger parents.                                     |
| **`cancelable`**             | `true` if the default action can be prevented.<br>🧪 Use Case: Conditionally calling `e.preventDefault()` on a form.                                 |
| **`currentTarget`**          | The element that the event handler is attached to.<br>🧪 Use Case: Useful in delegation or when dealing with multiple event listeners.               |
| **`defaultPrevented`**       | `true` if `preventDefault()` was called.<br>🧪 Use Case: Conditional UI logic (e.g., show warning if submission blocked).                            |
| **`eventPhase`**             | The phase of event propagation: <br>1 (Capturing), 2 (At target), 3 (Bubbling).<br>🧪 Use Case: Advanced event debugging.                            |
| **`isTrusted`**              | `true` if it’s a real user action (not triggered via JS).<br>🧪 Use Case: Preventing automated/bot actions or fakes.                                 |
| **`nativeEvent`**            | The actual browser-native event (like `MouseEvent`, `InputEvent`).<br>🧪 Use Case: Access browser-specific event props like `inputType`, `key`, etc. |
| **`target`**                 | The element where the event **actually happened**.<br>🧪 Use Case: In `<input>`, read `e.target.value`, `e.target.name`, etc.                        |
| **`timeStamp`**              | When the event was created (ms since page load).<br>🧪 Use Case: Custom event timing or analytics tracking.                                          |
| **`type`**                   | The type of the event (like `"change"`, `"click"`).<br>🧪 Use Case: Conditionally handling events for multiple input types.                          |
| **`persist()`**              | Removes the event from React’s event pool so it doesn’t get cleared.<br>🧪 Use Case: When using the event in an async callback like `setTimeout`.    |
| **`isDefaultPrevented()`**   | Returns `true` if `preventDefault()` has been called.<br>🧪 Use Case: Conditional logic or debugging if default behavior was blocked.                |
| **`isPropagationStopped()`** | Returns `true` if `stopPropagation()` has been called.<br>🧪 Use Case: Prevent bubbling in nested components.                                        |

 </h6>


## 1. event.target → Element where the event occurred
```jsx 
const handleClick = (event) => {
  console.log("Clicked Element:", event.target); // e.g., <button>Click</button>
};

<button onClick={handleClick}>Click</button>
```

## 2. event.currentTarget → Element where the handler is attached
```jsx 
const handleClick = (event) => {
  console.log("Handler Bound On:", event.currentTarget); // Always <div>
};

<div onClick={handleClick}>
  <button>Click Me</button>
</div>
```

📝 If you click the <button>, target is the button, currentTarget is the <div>.

## 3. event.type → Type of the event
```jsx 
const handleEvent = (e) => {
  console.log("Event Type:", e.type); // e.g., 'click', 'change'
};

<button onClick={handleEvent}>Click</button>
<input onChange={handleEvent} />
```

## 4. event.bubbles → Does the event bubble up?
```jsx 
const handleClick = (e) => {
  console.log("Bubbles?", e.bubbles); // true for most events
};

<button onClick={handleClick}>Click</button>
```

## 5. event.cancelable → Can default be prevented?
```jsx 
const handleClick = (e) => {
  console.log("Cancelable?", e.cancelable); // true
};

<button onClick={handleClick}>Click</button>
```

## 6. event.preventDefault() → Prevent default browser action

```jsx 
const handleSubmit = (e) => {
  e.preventDefault(); // Stops form from reloading page
  console.log("Form Submit Prevented");
};

<form onSubmit={handleSubmit}>
  <button type="submit">Submit</button>
</form>
```

## 7. event.stopPropagation() → Stop bubbling up
```jsx 
const parentClick = () => console.log("Parent clicked");
const childClick = (e) => {
  e.stopPropagation(); // Prevent parent click
  console.log("Child clicked");
};

<div onClick={parentClick}>
  <button onClick={childClick}>Click</button>
</div>
```

## 8. event.nativeEvent → Raw browser event
```jsx 
const handleInput = (e) => {
  console.log("Native InputType:", e.nativeEvent.inputType); // e.g., 'insertText'
};

<input onInput={handleInput} />
```

## 9. event.defaultPrevented → Has default been prevented?

```jsx 
const handleSubmit = (e) => {
  e.preventDefault();
  console.log("Prevented?", e.defaultPrevented); // true
};

<form onSubmit={handleSubmit}>
  <button type="submit">Submit</button>
</form>
```

## 10. event.persist() → Keep event object for async use
```jsx 
const handleClick = (e) => {
  e.persist(); // Allows keeping the event beyond this function
  setTimeout(() => {
    console.log("Event target after 1s:", e.target);
  }, 1000);
};

<button onClick={handleClick}>Click</button>
```

## 11. event.isDefaultPrevented() → Checks if default was prevented

```jsx 
const handleClick = (e) => {
  console.log("Before prevent:", e.isDefaultPrevented()); // false
  e.preventDefault();
  console.log("After prevent:", e.isDefaultPrevented()); // true
};

<a href="https://example.com" onClick={handleClick}>Link</a>
```

## 12. event.isPropagationStopped() → Checks if propagation was stopped

```jsx 
const handleChild = (e) => {
  e.stopPropagation();
  console.log("Propagation stopped?", e.isPropagationStopped()); // true
};

<div onClick={() => console.log("Parent Clicked")}>
  <button onClick={handleChild}>Child</button>
</div>
```

## 13. event.timeStamp → Time event was triggered (ms since page load)

```jsx 
const handleClick = (e) => {
  console.log("Event time:", e.timeStamp); // e.g., 123456.789
};

<button onClick={handleClick}>Click</button>
```
