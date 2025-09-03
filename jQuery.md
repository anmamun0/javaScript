#📘 jQuery Roadmap (Basic → Advanced)
 
 > First, include jQuery in your project:
```html
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```
 > Basic syntax:
```
$(selector).action();
```

Example:
```html
<button id="btn">Click Me</button>

<script>
  $("#btn").click(function() {
    alert("Button Clicked!");
  });
</script>
```

## 🔹 2. Selectors

👉 Example:

$("p").css("color", "blue");  // all paragraphs blue
$(".special").hide();          // hide class="special"
$("#title").text("New Title");


### 1. Basic Selectors
```js
$("#id")          // select element by ID
$(".class")       // select element by class
$("tag")          // select by tag (e.g., "p", "div")
$("*")            // select all elements
```

### 2. Grouping & Combining
```js
$("div, p, .class")   // select multiple types
$("div p")            // all <p> inside <div> (descendant)
$("div > p")          // direct child <p> of <div>
$("div + p")          // first <p> immediately after <div>
$("div ~ p")          // all <p> after <div>
```

### 3. Positional Selectors
```js
$("p:first")      // first <p>
$("p:last")       // last <p>
$("p:even")       // even index <p> (0, 2, 4…)
$("p:odd")        // odd index <p> (1, 3, 5…)
$("p:eq(2)")      // the 3rd <p> (index 2)
$("p:gt(2)")      // all <p> with index > 2
$("p:lt(2)")      // all <p> with index < 2
```
 >  Modern way (preferred):
```js
$("p").eq(2);     // same as $("p:eq(2)") → 3rd <p>
$("p").first();   // first <p>
$("p").last();    // last <p>
```

### 4. Attribute Selectors
```js
$("[href]")                  // elements with href attribute
$("a[href='https://google.com']") // specific value
$("a[href!='#']")            // not equal to
$("a[href^='https']")        // starts with
$("a[href$='.jpg']")         // ends with
$("a[href*='google']")       // contains substring
```

### 5. Form Selectors
```js
$(":input")       // all input, textarea, select, button
$(":text")        // text input
$(":password")    // password input
$(":radio")       // radio button
$(":checkbox")    // checkbox
$(":submit")      // submit button
$(":reset")       // reset button
$(":selected")    // selected option
$(":checked")     // checked checkbox/radio
$(":disabled")    // disabled element
$(":enabled")     // enabled element
```
### 6. Content Filters
```js
$("p:contains('Hello')")   // <p> containing "Hello"
$("p:empty")               // empty <p>
$("p:has(span)")           // <p> that has <span> inside
$("p:hidden")              // hidden <p>
$("p:visible")             // visible <p>
```

### 7. Child Filters
```js
$("ul li:first-child")     // first child <li>
$("ul li:last-child")      // last child <li>
$("ul li:nth-child(2)")    // 2nd child <li>
$("ul li:only-child")      // element that is the only child
```

###  8. Form State Filters
```js
$(":focus")        // element currently focused
```
### 9. Special Traversing Methods

👉 These are not selectors, but useful:
```js
$("p").eq(2)       // 3rd <p>
$("p").first()     // first <p>
$("p").last()      // last <p>
$("p").filter(".active")   // filter by condition
$("p").not(".active")      // exclude condition
$("p").slice(1, 3) // select 2nd and 3rd <p>
```


### Example

```html
<!DOCTYPE html>
<html>
<head>
  <title>jQuery Selectors Demo</title>
  <style>
    body { font-family: Arial; }
    .highlight { background: yellow; border: 1px solid red; }
    .hidden { display: none; }
  </style>
</head>
<body>

  <h2 id="title">jQuery Selectors Example</h2>

  <!-- For Basic / Grouping / Position selectors -->
  <div class="root">
    <p>Paragraph 1</p>
    <p class="special">Paragraph 2 (class)</p>
    <p>Paragraph 3</p>
    <span>Inside Div</span>
  </div>
  <p>Paragraph 4 (outside div)</p>

  <!-- Attribute Selectors -->
  <a href="https://google.com">Google</a>
  <a href="https://example.com/image.jpg">Image Link</a>
  <a href="#">Hash Link</a>

  <!-- Form Selectors -->
  <form id="myForm">
    <input type="text" value="Text Input"><br>
    <input type="password" value="password"><br>
    <input type="radio" name="gender" checked> Male
    <input type="radio" name="gender"> Female<br>
    <input type="checkbox" checked> Agree<br>
    <select>
      <option>Option 1</option>
      <option selected>Option 2</option>
    </select><br>
    <input type="submit" value="Submit">
    <input type="reset" value="Reset">
  </form>

  <!-- Content Filters -->
  <p class="content">Hello World</p>
  <p></p>
  <p><span>Has Span</span></p>
  <p class="hidden">Hidden Para</p>
  <p>Visible Para</p>

  <!-- Child Filters -->
  <ul>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
  </ul>
  <ul>
    <li>Only child</li>
  </ul>

  <button id="run">Run Selectors</button>

  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="test.js"></script>
</body>
</html>

```

> test.js

```js
 $("#run").click(function() {
      // 1. Basic Selectors
      $("#title").addClass("highlight");           // by ID
      $(".special").addClass("highlight");         // by class
      $("span").addClass("highlight");             // by tag
      $("*").css("font-style", "italic");          // all elements

      // 2. Grouping & Combining
      $("div, p, .class").css("color", "blue");    // multiple
      $("div p").addClass("highlight");            // all p inside div
      $("div > p").css("border", "1px solid green"); // direct child p
      $("div + p").css("color", "red");            // p right after div
      $("div ~ p").css("font-weight", "bold");     // all p after div

      // 3. Positional Selectors
      $("p:first").css("background", "pink");      // first p
      $("p:last").css("background", "lightgreen"); // last p
      $("p:even").css("text-decoration", "underline"); // even index
      $("p:odd").css("font-size", "20px");         // odd index
      $("p:eq(2)").text("3rd paragraph changed");  // eq()
      $("p:gt(2)").css("color", "purple");         // index > 2
      $("p:lt(2)").css("color", "orange");         // index < 2
      $("p").eq(1).css("background", "lightblue"); // modern eq
      $("p").first().css("border", "2px solid black");
      $("p").last().css("border", "2px dashed black");

      // 4. Attribute Selectors
      $("[href]").css("font-weight", "bold");
      $("a[href='https://google.com']").css("color", "red");
      $("a[href!='#']").css("background", "lightyellow");
      $("a[href^='https']").css("text-decoration", "underline");
      $("a[href$='.jpg']").css("color", "green");
      $("a[href*='google']").css("font-size", "22px");

      // 5. Form Selectors
      $(":input").css("border", "1px solid blue");
      $(":text").val("Edited Text");
      $(":password").val("123456");
      $(":radio:checked").parent().css("background", "lightpink");
      $(":checkbox:checked").parent().css("color", "red");
      $(":submit").css("background", "green").css("color", "white");
      $(":reset").css("background", "orange");
      $(":selected").css("color", "red");
      $(":disabled").css("opacity", "0.5");
      $(":enabled").css("border", "2px dashed orange");

      // 6. Content Filters
      $("p:contains('Hello')").css("background", "cyan");
      $("p:empty").text("This was empty");
      $("p:has(span)").css("border", "2px solid purple");
      $("p:hidden").show().css("color", "brown");
      $("p:visible").css("font-weight", "bold");

      // 7. Child Filters
      $("ul li:first-child").css("color", "red");
      $("ul li:last-child").css("color", "blue");
      $("ul li:nth-child(2)").css("color", "green");
      $("ul li:only-child").css("background", "yellow");

      // 8. Form State Filters
      $(":focus").css("background", "lightgray");

      // 9. Traversing Methods
      $("p").eq(3).css("background", "lightgray");
      $("p").filter(".content").css("border", "2px dotted red");
      $("p").not(".content").css("opacity", "0.8");
      $("p").slice(1, 3).css("color", "brown");
    });
```
---

<br>
<br>
<br>


## 🔹 3. Events

### 1. Mouse Events
```js
.click(handler) → when an element is clicked.
.dblclick(handler) → when double-clicked.
.mouseenter(handler) → when mouse enters the element.
.mouseleave(handler) → when mouse leaves the element.
.hover(handlerIn, handlerOut) → shortcut for mouseenter + mouseleave.
.mousedown(handler) → when mouse button is pressed down.
.mouseup(handler) → when mouse button is released.
.mousemove(handler) → when mouse moves over an element.
```
### 2. Keyboard Events

```js
.keydown(handler) → key is pressed down.
.keypress(handler) → key is pressed (but deprecated in modern browsers).
.keyup(handler) → key is released.
```
### 3. Form Events

```js
.submit(handler) → when a form is submitted.
.change(handler) → when value of input, select, or textarea changes.
.focus(handler) → when element gets focus.
.blur(handler) → when element loses focus.
.select(handler) → when text in an input/textarea is selected.
.input(handler) → when user types (works better than change for live typing).
```

### 4. Document / Window Events
```js
.ready(handler) → when DOM is fully loaded.
.resize(handler) → when window is resized.
.scroll(handler) → when user scrolls.
```

### 5. Event Handling Functions
```js
.on(event, selector, handler) → attach event(s) dynamically (best practice).
.off(event) → remove event handler.
.trigger(event) → manually trigger an event.
.one(event, handler) → run event only once.
```

### 6. Event Object Properties

When you pass a function (event), you get an event object:
```
event.type → type of event (click, keydown, etc.).
event.pageX / event.pageY → mouse position on page.
event.which → which mouse button or key was pressed.
event.target → element that triggered the event.
event.preventDefault() → stop default behavior (like stopping a form submit).
event.stopPropagation() → stop event bubbling.
```

 

```html
<!DOCTYPE html>
<html>
<head>
  <title>jQuery Selectors Demo</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    .box { width: 150px; height: 150px; background: lightblue; margin: 20px; text-align: center; line-height: 150px; cursor: pointer; }
    #output { margin-top: 20px; color: green; font-weight: bold; }
  </style>
</head>
<body>

  <h2>🔹 jQuery Events Demo</h2>

  <!-- Mouse Events -->
  <div class="box" id="mouseBox">Hover / Click Me</div>

  <!-- Keyboard Events -->
  <input type="text" id="keyInput" placeholder="Type here..." />

  <!-- Form Events -->
  <form id="myForm">
    <input type="text" name="username" id="username" placeholder="Enter username" />
    <select id="mySelect">
      <option value="">Choose...</option>
      <option value="js">JavaScript</option>
      <option value="jq">jQuery</option>
    </select>
    <button type="submit">Submit</button>
  </form>

  <p id="output">Event output will appear here...</p>

  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="test.js"></script>
</body>
</html>

```

> test.js
```js
$(document).ready(function () {
    // ---------- Mouse Events ----------
    $("#mouseBox").click(function () {
        $("#output").text("Box clicked!");
    });
    $("#mouseBox").dblclick(function () {
        $("#output").text("Box double clicked!");
    });
    $("#mouseBox").mouseenter(function () {
        $("#output").text("Mouse entered the box!");
    });
    $("#mouseBox").mouseleave(function () {
        $("#output").text("Mouse left the box!");
    });
    $("#mouseBox").mousedown(function () {
        $("#output").text("Mouse button down on box!");
    });
    $("#mouseBox").mouseup(function () {
        $("#output").text("Mouse button released on box!");
    });
    $("#mouseBox").mousemove(function (event) {
        $("#output").text("Mouse moving at X:" + event.pageX + " Y:" + event.pageY);
    });

    // ---------- Keyboard Events ----------
    $("#keyInput").keydown(function () {
        $("#output").text("Key down!");
    });
    $("#keyInput").keyup(function () {
        $("#output").text("Key up!");
    });
    $("#keyInput").keypress(function () {
        $("#output").text("Key pressed!");
    });

    // ---------- Form Events ----------
    $("#username").focus(function () {
        $("#output").text("Username field focused!");
    });
    $("#username").blur(function () {
        $("#output").text("Username field lost focus!");
    });
    $("#username").select(function () {
        $("#output").text("Text selected in username field!");
    });
    $("#username").change(function () {
        $("#output").text("Username value changed!");
    });
    $("#mySelect").change(function () {
        $("#output").text("Dropdown changed to: " + $(this).val());
    });
    $("#username").on("input", function () {
        $("#output").text("Typing: " + $(this).val());
    });
    $("#myForm").submit(function (event) {
        event.preventDefault(); // stop form from refreshing page
        $("#output").text("Form submitted with Username: " + $("#username").val());
    });

    // ---------- Window / Document Events ----------
    $(window).resize(function () {
        $("#output").text("Window resized!");
    });
    $(window).scroll(function () {
        $("#output").text("Window scrolled!");
    });

    // Trigger example
    $("#mouseBox").on("contextmenu", function (e) {
        e.preventDefault();
        $("#output").text("Right-click triggered!");
    });
});
```



---

<br>
<br>
<br>
<br>





## 🔹 4. Effects & Animations

.hide() / .show()
.toggle()
.fadeIn() / .fadeOut()
.slideUp() / .slideDown()
.animate()

👉 Example:

$("#btn").click(function() {
  $("#box").slideToggle("slow");
});

🔹 5. DOM Manipulation

.text() → get/set text
.html() → get/set HTML
.val() → get/set input value
.attr() → get/set attributes
.css() → get/set CSS

👉 Example:

$("#change").click(function() {
  $("#title").text("Title Changed!");
  $("#img").attr("src", "new-image.jpg");
});

🔹 6. Adding / Removing Elements

.append() → add inside at end
.prepend() → add inside at beginning
.after() → add after element
.before() → add before element
.remove() → remove element
.empty() → clear content

👉 Example:

$("#add").click(function() {
  $("#list").append("<li>New Item</li>");
});

🔹 7. Traversing (Moving through DOM)
```js
.parent()
.children()
.siblings()
.find()
.closest()
.next() / .prev()
```
👉 Example:
```js
$("#item").parent().css("border", "1px solid red");
```
🔹 8. jQuery Forms

Get values: $("#name").val()
Form events: .submit()

Validation example:
```
$("#myForm").submit(function(e) {
  e.preventDefault();
  let name = $("#name").val();
  if(name === "") {
    alert("Name is required");
  }
});
```

🔹 9. jQuery AJAX
```js
.load() → load data from server
$.get() / $.post()
$.ajax() (full control)
```

👉 Example:
```js
$.get("data.txt", function(data) {
  $("#result").html(data);
});
```
🔹 10. jQuery Advanced

Chaining:
```js
$("#box").css("color", "red").slideUp(1000).slideDown(1000);
```

Event Delegation (for dynamic elements):
```js
$(document).on("click", ".dynamic-btn", function() {
  alert("Dynamic button clicked!");
});
```

Plugins: jQuery UI, sliders, modals, date pickers.

Performance tips: use caching, minimize DOM lookups.

🔹 11. Responsive + jQuery

Toggle menu on mobile:
```js
$("#menu-btn").click(function() {
  $("#nav").toggle();
});
```

✅ By the end, you’ll know how to:
Control DOM elements easily
Handle events and effects
Validate forms
Use AJAX for dynamic content
Build responsive, interactive UI