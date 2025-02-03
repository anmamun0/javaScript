## FormData Methods Summary

## 🔹 Summary Table

| Method              | Description                                       |
|--------------------|-------------------------------------------------|
| [`append(name, value)`](#21-appendname-value) | Adds a new field (allows duplicates).          |
| [`set(name, value)`](#22-setname-value)   | Adds or replaces a field.                      |
| [`get(name)`](#23-getname)         | Returns the first value of a field.             |
| [`getAll(name)`](#24-getallname)      | Returns all values of a field as an array.      |
| [`has(name)`](#25-hasname)        | Checks if a field exists.                       |
| [`delete(name)`](#26-deletename)     | Removes a field.                                |
| [`entries()`](#27-entries)       | Returns all key-value pairs.                     |
| [`keys()`](#28-keys)          | Returns all field names.                         |
| [`values()`](#29-values)        | Returns all field values.                        |
 
```html
  <form id="form_create_course">
        <label for="course_name">Course Name:</label>
        <input type="text" id="course_name" name="course_name" required> 

        <label for="level">Level:</label>
        <select id="level" name="level">
            <option value="beginner">Beginner</option>
            <option value="intermediate">Intermediate</option> 
        </select>
        <br><br>

        <label for="tags">Tags (hold Ctrl to select multiple):</label>
        <select id="tags" name="tags" multiple>
            <option value="javascript">JavaScript</option>
            <option value="html">HTML</option> 
        </select>
        <br><br>

        <label for="course_file">Upload Course File:</label>
        <input type="file" id="course_file" name="course_file"> 

        <button type="button" onclick="submitForm()">Submit</button>
    </form> 
```

```js
    <script>
        function submitForm() {
            // Select the form element
            const formElement = document.getElementById("form_create_course");

            // Create a FormData object from the form
            const formData = new FormData(formElement);

            // 🔹 Print individual values
            console.log("Course Name:", formData.get("course_name"));
            console.log("Level:", formData.get("level"));

            // 🔹 Get all selected tags
            console.log("Tags:", formData.getAll("tags")); 

            // 🔹 Check if a file is selected and print file details
            const file = formData.get("course_file");

            if (file && file.name) {
                console.log("Uploaded File Name:", file.name);
                console.log("File Size:", file.size, "bytes");
            } else {
                console.log("No file uploaded.");
            }

            // 🔹 Loop through all form entries (key-value pairs)
            console.log("All Form Data:");
            for (let [key, value] of formData.entries()) {
                console.log(`${key}:`, value);
            }
            console.log('abda----')
            for (let value of formData.values()) {
                console.log(value);
            } 
        } 
    </script>


<!-- 
    Course Name: your name youo
    Level: intermediate

    Tags: (3) ['javascript', 'html', 'css']
    Uploaded File Name: WhatsApp Image 2025-02-01 at 20.17.56_f40dda0e.jpg
    File Size: 82261 bytes

    All Form Data:
    course_name: your name youo
    level: intermediate
    tags: javascript
    tags: html
    tags: css
    course_file: File {name: 'WhatsApp Image 2025-02-01 at 20.17.56_f40dda0e.jpg', lastModified: 1738419519648, lastModifiedDate: Sat Feb 01 2025 20:18:39 GMT+0600 (Bangladesh Standard Time), webkitRelativePath: '', size: 82261, …} 

-->
``` 


📌 JavaScript FormData Object – All Methods & Use Cases
- The FormData object is used to collect form inputs and send them via AJAX (Fetch/XHR) requests without reloading the page. It is especially useful for handling file uploads and dynamically creating form data.

### 🔹 1. Creating a FormData Object
###### You can create a FormData object in two ways:

##### 👌 Method 1: From an HTML Form
```js
// Select the form element by its ID
const formElement = document.getElementById("myForm");

// Create a FormData object from the form
const formData = new FormData(formElement);
```

### 👌 Method 2: Manually Create FormData
```js
// Create an empty FormData object
const formData = new FormData();

// Add key-value pairs manually
formData.append("username", "mamun");
formData.append("email", "mamun@example.com");
```

## 🔹 2. FormData Methods & Use Cases
###### Here are all the methods available in the FormData object.

### 👌 2.1. append(name, value)
✔️ Adds a new field to the FormData object.
✔️ If a field with the same name exists, it adds another instead of replacing it.

```js
const formData = new FormData();
formData.append("name", "Mamun");
formData.append("email", "mamun@example.com");
formData.append("hobby", "coding");
formData.append("hobby", "gaming"); // Adds multiple hobbies

console.log(formData.getAll("hobby")); // ["coding", "gaming"]
```

### 👌 2.2. set(name, value)
✔️ Replaces an existing field (unlike append, which adds multiple).
✔️ If the field does not exist, it creates a new one.

```js
formData.set("name", "Mamun"); 
formData.set("hobby", "reading"); // Replaces previous hobbies

console.log(formData.get("hobby")); // "reading"
```

### 👌 2.3. get(name)
✔️ Retrieves the first value of a field.

```js
console.log(formData.get("name"));  // "Mamun"
console.log(formData.get("email")); // "mamun@example.com"
console.log(formData.get("hobby")); // "reading"
```

### 👌 2.4. getAll(name)
✔️ Retrieves all values for a field as an array.

```js
formData.append("language", "JavaScript");
formData.append("language", "Python");

console.log(formData.getAll("language")); // ["JavaScript", "Python"]
```

### 👌 2.5. has(name)
✔️ Checks if a field exists in FormData.

```js
console.log(formData.has("name"));     // true
console.log(formData.has("password")); // false
```

### 👌 2.6. delete(name)
✔️ Removes a field from FormData.

```js
formData.delete("hobby");
console.log(formData.has("hobby")); // false
```

### 👌 2.7. entries()
✔️ Returns an iterator of key-value pairs.
✔️ Use it in a for...of loop.

```js
for (let [key, value] of formData.entries()) {
    console.log(`${key}: ${value}`);
}
```

### 👌 2.8. keys()
✔️ Returns an iterator of field names.

```js
for (let key of formData.keys()) {
    console.log("Field name:", key);
}
```

### 👌 2.9. values()
✔️ Returns an iterator of field values.

```js
for (let value of formData.values()) {
    console.log("Field value:", value);
}
```

## 🔹 3. Use Cases of FormData

### 👌 Case 1: Sending Form Data with fetch()
✔️ Used in AJAX calls to send data to a backend.

```js
fetch("https://example.com/api", {
    method: "POST",
    body: formData // Send FormData directly
})
.then(response => response.json())
.then(data => console.log("Success:", data))
.catch(error => console.error("Error:", error));
```

### 👌 Case 2: Handling File Uploads
✔️ FormData supports files natively.

```js
const fileInput = document.getElementById("file");
const file = fileInput.files[0];

// Append file to FormData
formData.append("profile_picture", file);
```

### 👌 Case 3: Sending FormData with Axios
✔️ Axios supports FormData natively.

```js
axios.post("https://example.com/api", formData)
     .then(response => console.log("Response:", response))
     .catch(error => console.error("Error:", error));
```









---

### Multiple select input print in consol

```html
<select id="tags" name="category" multiple>
    <option value="javascript">JavaScript</option>
    <option value="html">HTML</option>
    <option value="css">CSS</option>
    <option value="web">Web Development</option>
</select>
```


```js
const formElement = document.getElementById("form_create_course");
const formData = new FormData(formElement);

const allvalue = formData.getAll('category') // output:  ['javascript', 'html'] 
```







