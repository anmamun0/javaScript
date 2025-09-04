# 📘 jQuery Roadmap (Basic → Advanced)
 
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
## Table of Contents
  
<h6>
 
| Topic | Description |
|-------|-------------|
| [🔹 2. Selectors](#-2-selectors) | Select elements from the DOM using IDs, classes, tags, or relationships. |
| [🔹 3. Events](#-3-events) | Handle user interactions like clicks, keyboard input, mouse hover, and form submissions. |
| [🔹 4. Effects & Animations](#-4-effects--animations) | Show, hide, toggle, fade, slide, or animate elements for visual effects. |
| [🔹 5. DOM Manipulation](#-5-dom-manipulation) | Get or set text, HTML, input values, attributes, and CSS properties. |
| [🔹 6. Traversing (DOM Navigation)](#-6-traversing-dom-navigation) | Move through DOM elements to find parents, children, siblings, ancestors, or descendants. |
| [🔹 7. jQuery Forms](#-7-jquery-forms) | Work with form inputs and handle form submission events. |
| [🔹 8. jQuery AJAX](#-8-jquery-ajax) | Perform asynchronous requests to load, get, or post data without reloading the page. |
| [🔹 9. jQuery Advanced](#-9-jquery-advanced) | Advanced features like iteration, data storage, element cloning, queues, and object extension. |
| [🔹 10. Responsive + jQuery](#-10-responsive--jquery) | Handle window resizing, dynamic classes, orientation changes, and responsive element toggling. |

</h6>

---

# 🔹 2. Selectors
[Home](#table-of-contents)

#### 1. Basic Selectors
```js
$("#id")          // select element by ID
$(".class")       // select element by class
$("tag")          // select by tag (e.g., "p", "div")
$("*")            // select all elements
```

#### 2. Grouping & Combining
```js
$("div, p, .class")   // select multiple types
$("div p")            // all <p> inside <div> (descendant)
$("div > p")          // direct child <p> of <div>
$("div + p")          // first <p> immediately after <div>
$("div ~ p")          // all <p> after <div>
```

#### 3. Positional Selectors
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

#### 4. Attribute Selectors
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
#### 6. Content Filters
```js
$("p:contains('Hello')")   // <p> containing "Hello"
$("p:empty")               // empty <p>
$("p:has(span)")           // <p> that has <span> inside
$("p:hidden")              // hidden <p>
$("p:visible")             // visible <p>
```

#### 7. Child Filters
```js
$("ul li:first-child")     // first child <li>
$("ul li:last-child")      // last child <li>
$("ul li:nth-child(2)")    // 2nd child <li>
$("ul li:only-child")      // element that is the only child
```

####  8. Form State Filters
```js
$(":focus")        // element currently focused
```
#### 9. Special Traversing Methods

👉 These are not selectors, but useful:
```js
$("p").eq(2)       // 3rd <p>
$("p").first()     // first <p>
$("p").last()      // last <p>
$("p").filter(".active")   // filter by condition
$("p").not(".active")      // exclude condition
$("p").slice(1, 3) // select 2nd and 3rd <p>
```


#### Example

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


# 🔹 3. Events
[Home](#table-of-contents)

# jQuery Events Summary 
<h6>

| Method | Description |
|--------|-------------|
| `.click(handler)` | Triggered when an element is clicked. |
| `.dblclick(handler)` | Triggered when an element is double-clicked. |
| `.mouseenter(handler)` | Triggered when the mouse enters the element. |
| `.mouseleave(handler)` | Triggered when the mouse leaves the element. |
| `.hover(handlerIn, handlerOut)` | Shortcut for `mouseenter` + `mouseleave`. |
| `.mousedown(handler)` | Triggered when a mouse button is pressed down. |
| `.mouseup(handler)` | Triggered when a mouse button is released. |
| `.mousemove(handler)` | Triggered when the mouse moves over an element. |
| `.keydown(handler)` | Triggered when a key is pressed down. |
| `.keypress(handler)` | Triggered when a key is pressed (**deprecated**). |
| `.keyup(handler)` | Triggered when a key is released. |
| `.submit(handler)` | Triggered when a form is submitted. |
| `.change(handler)` | Triggered when input, select, or textarea value changes. |
| `.focus(handler)` | Triggered when an element gains focus. |
| `.blur(handler)` | Triggered when an element loses focus. |
| `.select(handler)` | Triggered when text in an input/textarea is selected. |
| `.input(handler)` | Triggered when user types (live typing detection). |
| `.ready(handler)` | Triggered when the DOM is fully loaded. |
| `.resize(handler)` | Triggered when the window is resized. |
| `.scroll(handler)` | Triggered when the user scrolls. |
| `.on(event, selector, handler)` | Attach event(s) dynamically (**best practice**). |
| `.off(event)` | Remove an event handler. |
| `.trigger(event)` | Manually trigger an event. |
| `.one(event, handler)` | Run the event handler only once. |

---

## Event Object (Summary)
- `event.type` → Event type (`click`, `keydown`, etc.)  
- `event.pageX / event.pageY` → Mouse position on the page  
- `event.which` → Which mouse button or key was pressed  
- `event.target` → Element that triggered the event  
- `event.preventDefault()` → Stop default behavior (e.g., form submit)  
- `event.stopPropagation()` → Stop event bubbling  

 
</h6>

#### 1. Mouse Events
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
#### 2. Keyboard Events

```js
.keydown(handler) → key is pressed down.
.keypress(handler) → key is pressed (but deprecated in modern browsers).
.keyup(handler) → key is released.
```
#### 3. Form Events

```js
.submit(handler) → when a form is submitted.
.change(handler) → when value of input, select, or textarea changes.
.focus(handler) → when element gets focus.
.blur(handler) → when element loses focus.
.select(handler) → when text in an input/textarea is selected.
.input(handler) → when user types (works better than change for live typing).
```

#### 4. Document / Window Events
```js
.ready(handler) → when DOM is fully loaded.
.resize(handler) → when window is resized.
.scroll(handler) → when user scrolls.
```

#### 5. Event Handling Functions
```js
.on(event, selector, handler) → attach event(s) dynamically (best practice).
.off(event) → remove event handler.
.trigger(event) → manually trigger an event.
.one(event, handler) → run event only once.
```

#### 6. Event Object Properties

When you pass a function (event), you get an event object:
```js
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





# 🔹 4. Effects & Animations
[Home](#table-of-contents)

`.hide()`, `.show()`
`.toggle()`
`.fadeIn()`, `.fadeOut()`,  `.fadeToggle()`, `.fadeTo()	` 
`.slideUp()`, `.slideDown()` 
`.slideUp()`, `.slideDown()` , `.slideToggle()`
`.animate()`	Custom CSS animation
`.stop()`


#### jQuery Effects & Animations Summary

<h6>

| Method | Description |
|--------|-------------|
| `.hide([speed, easing, callback])` | Hides elements (optionally with animation). |
| `.show([speed, easing, callback])` | Shows hidden elements. |
| `.toggle([speed, easing, callback])` | Toggles between show and hide. |
| `.fadeIn([speed, easing, callback])` | Fades in hidden elements. |
| `.fadeOut([speed, easing, callback])` | Fades out visible elements. |
| `.fadeToggle([speed, easing, callback])` | Toggles fade in/out. |
| `.fadeTo(speed, opacity, [easing, callback])` | Fades to a specific opacity. |
| `.slideUp([speed, easing, callback])` | Slides element up (hides it). |
| `.slideDown([speed, easing, callback])` | Slides element down (shows it). |
| `.slideToggle([speed, easing, callback])` | Toggles between slide up/down. |
| `.animate(properties, [speed, easing, callback])` | Animates multiple CSS properties. |
| `.stop([clearQueue, jumpToEnd])` | Stops current animation (and optionally clears queue/jumps to end). |
| **Chaining** | Multiple effects/animations can be chained together. |
  
</h6>



#### 1. Show / Hide / Toggle
```
.hide([speed, easing, callback]) → Hides elements.
.show([speed, easing, callback]) → Shows elements.
.toggle([speed, easing, callback]) → Toggles between show and hide.

$(".box").hide();                 // instantly hide
$(".box").show("slow");           // show slowly
$(".box").toggle(1000);           // toggle with 1s animation
```

#### 2. Fade Effects
```js
.fadeIn([speed, easing, callback]) → Fade in hidden element.
.fadeOut([speed, easing, callback]) → Fade out visible element.
.fadeToggle([speed, easing, callback]) → Toggle fade in/out.
.fadeTo(speed, opacity, easing, callback) → Fade to a specific opacity.
$(".box").fadeIn("slow");
$(".box").fadeOut(2000);
$(".box").fadeToggle(1000);
$(".box").fadeTo(1000, 0.3);   // fade to 30% opacity
```

#### 3. Slide Effects
```js
.slideUp([speed, easing, callback]) → Slide element up (hide).
.slideDown([speed, easing, callback]) → Slide element down (show).
.slideToggle([speed, easing, callback]) → Toggle slide up/down.
$(".menu").slideUp("fast");
$(".menu").slideDown(1000);
$(".menu").slideToggle(1500);
```

#### 4. Custom Animation
- .animate(properties, [speed, easing, callback])
- Animate multiple CSS properties at once.
  
```js
$(".box").animate({
  left: "200px",
  opacity: 0.5,
  height: "300px",
  width: "300px"
}, 2000);
```
#### 5. Stop Animation

- `.stop([clearQueue, jumpToEnd])`
- Stops current animation.

```js
$(".box").stop();           // stop current animation
$(".box").stop(true);       // stop and clear queued animations
$(".box").stop(true, true); // stop and jump to end state
```

#### 6. Chaining
- Multiple animations/effects can be chained.

```js
$(".box")
  .slideUp(1000)
  .slideDown(1000)
  .fadeOut(1000)
  .fadeIn(1000);
```


#### Example

```html
<!DOCTYPE html>
<html>
<head>
  <title>jQuery Selectors Demo</title>
  <style>
       body { font-family: Arial, sans-serif; margin: 20px; }
    .box {
      width: 150px; height: 150px;
      background: lightcoral;
      margin: 20px auto;
      position: relative;
      text-align: center;
      line-height: 150px;
      color: white; font-weight: bold;
      border-radius: 10px;
    }
    .btns { margin-top: 20px; }
    button {
      margin: 5px; padding: 8px 14px;
      border: none; background: steelblue; color: white;
      border-radius: 5px; cursor: pointer;
    }
    button:hover { background: darkblue; }
  </style>
</head>
<body>

  <h2>🔹 jQuery Effects & Animations Demo</h2>

  <div class="box">Box</div>

  <div class="btns">
    <!-- Show/Hide/Toggle -->
    <button id="hide">Hide</button>
    <button id="show">Show</button>
    <button id="toggle">Toggle</button>
    <br>

    <!-- Fade Effects -->
    <button id="fadeIn">Fade In</button>
    <button id="fadeOut">Fade Out</button>
    <button id="fadeToggle">Fade Toggle</button>
    <button id="fadeTo">Fade To (30%)</button>
    <br>

    <!-- Slide Effects -->
    <button id="slideUp">Slide Up</button>
    <button id="slideDown">Slide Down</button>
    <button id="slideToggle">Slide Toggle</button>
    <br>

    <!-- Custom Animation -->
    <button id="animate">Animate</button>
    <button id="stop">Stop</button>
    <br>

    <!-- Chaining -->
    <button id="chain">Chaining Demo</button>
  </div>


  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="test.js"></script>
</body>
</html>

```


```js
$(document).ready(function(){

      // --- Show/Hide/Toggle ---
      $("#hide").click(function(){ $(".box").hide(1000); });
      $("#show").click(function(){ $(".box").show(1000); });
      $("#toggle").click(function(){ $(".box").toggle(1000); });

      // --- Fade Effects ---
      $("#fadeIn").click(function(){ $(".box").fadeIn(1000); });
      $("#fadeOut").click(function(){ $(".box").fadeOut(1000); });
      $("#fadeToggle").click(function(){ $(".box").fadeToggle(1000); });
      $("#fadeTo").click(function(){ $(".box").fadeTo(1000, 0.3); });

      // --- Slide Effects ---
      $("#slideUp").click(function(){ $(".box").slideUp(1000); });
      $("#slideDown").click(function(){ $(".box").slideDown(1000); });
      $("#slideToggle").click(function(){ $(".box").slideToggle(1000); });

      // --- Custom Animation ---
      $("#animate").click(function(){
        $(".box").animate({
          left: "200px",
          opacity: 0.5,
          height: "200px",
          width: "200px"
        }, 2000);
      });

      // --- Stop Animation ---
      $("#stop").click(function(){
        $(".box").stop(true, true); // stop and jump to end
      });

      // --- Chaining ---
      $("#chain").click(function(){
        $(".box")
          .slideUp(1000)
          .slideDown(1000)
          .fadeOut(1000)
          .fadeIn(1000)
          .animate({left: "0px", width: "150px", height: "150px", opacity: 1}, 1000);
      });

    });
```


<br>
<br>
<br>
<br>



 

## 🔹 5. DOM Manipulation
[Home](#table-of-contents)

<h6> 
 
| Method                                                              | Description               |
| ------------------------------------------------------------------- | ------------------------- |
| `.text()`                                                           | Get/set text              |
| `.html()`                                                           | Get/set HTML              |
| `.val()`                                                            | Get/set input value       |
| `.attr()` / `.removeAttr()`                                         | Get/set/remove attributes |
| `.css()`                                                            | Get/set CSS               |
| `.addClass()` / `.removeClass()` / `.toggleClass()` / `.hasClass()` | Manage classes            |
| `.append()` / `.prepend()`                                          | Add inside element        |
| `.after()` / `.before()`                                            | Add outside element       |
| `.remove()` / `.empty()`                                            | Delete elements           |
| `.clone()`                                                          | Clone element             |
| `.replaceWith()`                                                    | Replace element           |
| `.wrap()`                                                           | Wrap element              |

</h6>



#### 1. Content Methods
- ``.text([value])`` > Get → Returns inner text of element(s).  Set → Sets text (replaces existing content).
- ``.html([value])`` > Get → Returns inner HTML (with tags). Set → Inserts HTML inside element.
- ``.val([value])`` > Works for form elements (input, textarea, select).
  
```js
$("#para").text();              // get text
$("#para").text("New text!");   // set new text

$("#box").html();                          // get HTML
$("#box").html("<b>Bold Content</b>");     // set HTML

$("#username").val();              // get input value
$("#username").val("Mamun");       // set value
```


#### 2. Attributes
- ``.attr(name [, value])`` > Get → Value of an attribute. Set → Change or add attribute.
- ``.removeAttr(name)`` - Removes an attribute.
  
```js
// attr
$("img").attr("src");                     // get src
$("img").attr("alt", "Profile Picture");  // set alt
$("img").removeAttr("alt");

$("#change").click(function() {
  $("#title").text("Title Changed!");
  $("#img").attr("src", "new-image.jpg");
});
```
 

#### 3. CSS & Classes
- ``.css(property [, value])`` - Get → Current CSS property. Set → Apply inline CSS.
- ``.addClass(className)`` - Add one or more classes.
- ``.removeClass(className)``  - Remove one or more classes.
- ``.toggleClass(className)`` - Add class if not present, remove if present.
- ``.hasClass(className)`` - Checks if element has a class → returns true/false.

```js
$(".box").css("color");                     // get color
$(".box").css("background", "lightblue");   // set background
$("#box").addClass("highlight big");
$("#box").removeClass("highlight");
$("#box").toggleClass("active");

if ($("#box").hasClass("active")) {
  console.log("Box is active!");
}
```



#### 4. DOM Structure Manipulation
- `.append(content)` Insert content at the end of selected element.
- `.prepend(content)` - Insert content at the beginning.
- `.after(content)` - Insert content after element.
- `.before(content)` - Insert content before element.
- `.remove()` - Removes selected element(s) completely.
- `.empty()` - Removes all child elements but keeps the parent.

```js
$("#list").append("<li>New Item</li>");
$("#list").prepend("<li>First Item</li>");
$("#box").after("<p>After the box</p>");
$("#box").before("<p>Before the box</p>");
$("#box").remove();
$("#box").empty();
```



5. Cloning & Replacing

- ``.clone()`` Creates a copy of an element.
- ``.replaceWith(content)`` - Replace an element with new content.
- ``.wrap(wrapper)`` - Wrap each element with a wrapper.

```js
$("#box").clone().appendTo("#container");
$("#old").replaceWith("<div>New Content</div>");
$("p").wrap("<div class='wrapper'></div>");
```

 

#### 🔹 6. Adding / Removing Elements

```js
.append() → add inside at end
.prepend() → add inside at beginning
.after() → add after element
.before() → add before element
.remove() → remove element
.empty() → clear content
```
👉 Example:
```
$("#add").click(function() {
  $("#list").append("<li>New Item</li>");
});
```

--- 
<br>
<br>
<br>



## 🔹 6. Traversing (DOM Navigation)
[Home](#table-of-contents)


<h6> 
 
| Category                | Method                    | Description                                                         |
| ----------------------- | ------------------------- | ------------------------------------------------------------------- |
| **Parent Traversal**    | `.parent()`               | Selects the immediate parent.                                       |
|                         | `.parents([selector])`    | Selects all ancestors (parent, grandparent, etc.).                  |
|                         | `.parentsUntil(selector)` | Selects ancestors up to (but not including) the selector.           |
| **Children Traversal**  | `.children([selector])`   | Selects direct children only.                                       |
|                         | `.find(selector)`         | Selects all descendants (deep search).                              |
| **Siblings Traversal**  | `.siblings([selector])`   | Selects all siblings.                                               |
|                         | `.next()`                 | Selects the immediately next sibling.                               |
|                         | `.nextAll()`              | Selects all next siblings.                                          |
|                         | `.nextUntil(selector)`    | Selects next siblings up to (but not including) selector.           |
|                         | `.prev()`                 | Selects the immediately previous sibling.                           |
|                         | `.prevAll()`              | Selects all previous siblings.                                      |
|                         | `.prevUntil(selector)`    | Selects previous siblings up to (but not including) selector.       |
| **Closest Traversal**   | `.closest(selector)`      | Selects the nearest ancestor (or itself) that matches the selector. |
| **Filtering Traversal** | `.first()`                | Selects the first element.                                          |
|                         | `.last()`                 | Selects the last element.                                           |
|                         | `.eq(index)`              | Selects element at specific index.                                  |
|                         | `.filter(selector)`       | Keeps only elements that match selector.                            |
|                         | `.not(selector)`          | Excludes elements that match selector.                              |
|                         | `.has(selector)`          | Keeps elements that contain a child matching selector.              |

</h6>

#### 1. Parent Traversal

- ``.parent()`` → Selects the immediate parent of the element.
- ``.parents([selector])`` → Selects all ancestors (parent, grandparent, etc.).
- ``.parentsUntil(selector)`` → Selects ancestors up to but not including the selector.

```js
$(".item").parent();  
$(".item").parents();            // all ancestors  
$(".item").parents("div");       // all ancestor <div>  
$(".item").parentsUntil(".container");  
```

####  2. Children Traversal
- ``.children([selector])`` → Selects direct children only (not nested deeper).
- ``.find(selector)`` → Selects all descendants (deep search).
  
```js
$(".list").children();          // all direct children  
$(".list").children("li");      // only direct <li> children  
$(".list").find("span");        // all <span> inside list (deep)  
```

####  3. Siblings Traversal

- ``.siblings([selector])`` → Selects all siblings of an element.
- ``.next()`` → Selects the immediately next sibling.
- ``.nextAll()`` → Selects all next siblings.
- ``.nextUntil(selector)`` → Selects next siblings up to but not including selector.
- ``.prev()`` → Selects the immediately previous sibling.
- ``.prevAll()`` → Selects all previous siblings.
- ``.prevUntil(selector)`` → Selects previous siblings up to but not including selector.

```js
$(".item").siblings();          
$(".item").siblings(".active"); 
$(".item").next();              
$(".item").nextAll();           
$(".item").nextUntil(".stopHere");
$(".item").prev();              
$(".item").prevAll();           
$(".item").prevUntil(".startHere");
```

#### 4. Closest
.closest(selector) → Finds the nearest ancestor (or itself) that matches the selector.
```js
$(".item").closest("div");  
```

#### 6. Filtering Traversal

- ``.first()`` → First element.
- ``.last()`` → Last element.
- ``.eq(index)`` → Element at specific index.
- ``.filter(selector)`` → Keep only matching elements.
- ``.not(selector)`` → Exclude matching elements.
- ``.has(selector)`` → Keep elements that contain a selector.

```js
$("li").first();             
$("li").last();              
$("li").eq(2);               
$("li").filter(".active");   
$("li").not(".active");      
$("ul").has("li.active");    
```









## 🔹 7. jQuery Forms

<h6>

| **Method / Selector** | **Description**                               | **Example**                         |
| --------------------- | --------------------------------------------- | ----------------------------------- |
| `.val()`              | Get or set value of input, textarea, select   | `$("#name").val("Mamun");`          |
| `.submit()`           | Triggered when form is submitted              | `$("#form").submit(fn);`            |
| `.change()`           | Fires when input/select value changes         | `$("#country").change(fn);`         |
| `.focus()`            | When an input gains focus                     | `$("#email").focus(fn);`            |
| `.blur()`             | When an input loses focus                     | `$("#email").blur(fn);`             |
| `.select()`           | Fires when text is selected in input/textarea | `$("#username").select(fn);`        |
| `:checked`            | Selects checked checkbox/radio                | `$(":checkbox:checked")`            |
| `.prop()`             | Get/set properties (e.g., disabled, checked)  | `$("#btn").prop("disabled", true);` |
| `.serialize()`        | Converts form data → URL-encoded string       | `$("#form").serialize();`           |
| `.serializeArray()`   | Converts form data → array of objects         | `$("#form").serializeArray();`      |

 
</h6>




# jQuery Forms Methods & Events
[Home](#table-of-contents)

#### 1. Getting / Setting Values

.val() → Get or set value of form elements.
```js
$("#name").val();              // get value
$("#name").val("Mamun");       // set value
```

#### 2. Form Events

.submit() → Fires when form is submitted.
```js
$("#myForm").submit(function(e){
  e.preventDefault(); // stop default refresh
  alert("Form submitted!");
});
```

.change() → Fires when value of an input/select changes.
```js
$("#country").change(function(){
  alert("Country changed!");
}); 
```

.focus() / .blur() → Triggered when an input gains/loses focus.
```js
$("#email").focus(function(){
  $(this).css("background", "lightyellow");
});
$("#email").blur(function(){
  $(this).css("background", "");
});
```

.select() → Fires when text inside input/textarea is selected.
```js
$("#username").select(function(){
  alert("Text selected!");
});
```
#### 3. Checkbox / Radio Handling
 
:checked → Get checked elements.
```js
$("input[type='checkbox']:checked").each(function(){
  console.log($(this).val());
});
```

#### 4. Enabling / Disabling Fields

.prop() → Get or set properties.
```js
$("#submitBtn").prop("disabled", true);   // disable
$("#submitBtn").prop("disabled", false);  // enable
```
#### 5. Form Serialization

.serialize() → Converts form data to URL encoded string.
```js
let data = $("#myForm").serialize();
console.log(data);  
// Example output: name=Mamun&email=test@mail.com
```

.serializeArray() → Converts form data into array of objects.

```js
let data = $("#myForm").serializeArray();
console.log(data);  
/*
[
  {name: "name", value: "Mamun"},
  {name: "email", value: "test@mail.com"}
]
*/
```

---

<br>
<br>
<br>




# 🔹 8. jQuery AJAX
[Home](#table-of-contents)

#### Asynchronous JavaScript And XML

Explanation:
- `Asynchronous` → Requests happen in the background without reloading the whole page.
- `JavaScript` → The language used to send/receive the request.
- `And` → Just a connector word .
- `XML` → Originally used for data exchange, but nowadays JSON is more common.

#### So, AJAX = A technique to send/receive data between the browser and server asynchronously using JavaScript (usually with JSON instead of XML).

```js
.load() → load data from server
$.get() / $.post()
$.ajax() (full control)
```

#### 1. Basic AJAX Call

```js
$.ajax({
    url: "file.php",
    method: "GET",
    data: { name: "Mamun" },
    success: function(response) {
        console.log(response);
    },
    error: function(xhr, status, error) {
        console.log(error);
    }
});
```

- `url` → URL of the server-side file
- `method` → GET / POST / PUT / DELETE
- `data` → Data to send
- `success` → Function when request succeeds
- `error` → Function when request fails

#### 2. Shorthand Methods
<h6>

| **Method**                      | **Description** | **Example**                               |
| ------------------------------- | --------------- | ----------------------------------------- |
| `$.get(url, data, success)`     | GET request     | `$.get("file.php", {id:1}, fn);`          |
| `$.post(url, data, success)`    | POST request    | `$.post("file.php", {name:"Mamun"}, fn);` |
| `$.getJSON(url, data, success)` | GET JSON data   | `$.getJSON("data.json", fn);`             |

 
</h6>

#### 3. AJAX Global Events

<h6>

| **Event**      | **Description**                     | **Example**                     |
| -------------- | ----------------------------------- | ------------------------------- |
| `ajaxStart`    | Fires when AJAX request starts      | `$(document).ajaxStart(fn);`    |
| `ajaxStop`     | Fires when all AJAX requests finish | `$(document).ajaxStop(fn);`     |
| `ajaxComplete` | Fires when a request finishes       | `$(document).ajaxComplete(fn);` |
| `ajaxError`    | Fires when request fails            | `$(document).ajaxError(fn);`    |
| `ajaxSend`     | Fires before sending request        | `$(document).ajaxSend(fn);`     |

 
</h6>

#### 4. AJAX Settings Options
 
<h6>
 
 | **Option**        | **Description**                                        |
| ----------------- | ------------------------------------------------------ |
| `url`             | Server URL                                             |
| `type` / `method` | GET / POST / PUT / DELETE                              |
| `data`            | Data to send                                           |
| `dataType`        | Expected response type (`json`, `xml`, `html`, `text`) |
| `async`           | true/false (asynchronous request)                      |
| `timeout`         | Timeout in milliseconds                                |
| `headers`         | Custom HTTP headers                                    |
| `beforeSend`      | Function before request is sent                        |
| `success`         | Function on success                                    |
| `error`           | Function on error                                      |
| `complete`        | Function always runs after request                     |

</h6>
   
#### 5. 5. Load Content into DOM
```js
$("#result").load("file.html"); // Load HTML content into #result
```

 
#### 6. Example Combined AJAX

```js
$.ajax({
    url: "data.php",
    method: "POST",
    data: { user: "Mamun" },
    dataType: "json",
    beforeSend: function() {
        $("#loader").show();
    },
    success: function(response) {
        $("#result").text(response.message);
    },
    error: function(xhr, status, error) {
        alert("Error: " + error);
    },
    complete: function() {
        $("#loader").hide();
    }
});

```


👉 Example:
```js
$.get("data.txt", function(data) {
  $("#result").html(data);
});
```

---
<br>
<br>
<br>




# 🔹 9. jQuery Advanced
[Home](#table-of-contents)

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


#### 1. Advanced Selectors

<h6>

| **Selector**           | **Description**             | **Example**                |
| ---------------------- | --------------------------- | -------------------------- |
| `:first` / `:last`     | First / last element        | `$("p:first")`             |
| `:eq(index)`           | Element at index (0-based)  | `$("p:eq(2)")`             |
| `:even` / `:odd`       | Even / odd elements         | `$("li:even")`             |
| `:not(selector)`       | Exclude selector            | `$("div:not(.active)")`    |
| `:contains(text)`      | Contains specific text      | `$("p:contains('hello')")` |
| `:has(selector)`       | Has child matching selector | `$("div:has(p)")`          |
| `:visible` / `:hidden` | Visible / hidden elements   | `$("div:visible")`         |

 
</h6>

#### 2. Chaining
```js
$("#box")
    .css("background", "blue")
    .slideUp(1000)
    .slideDown(1000)
    .fadeOut(500)
    .fadeIn(500);
```

You can apply multiple methods sequentially on the same element.

#### 3. Callbacks
```js
$("#btn").click(function() {
    $("#box").slideUp(1000, function() {
        alert("SlideUp Complete!");
    });
});
```

Callback is a function executed after animation or event completes.

#### 4. Deferred / Promises

```js
let request = $.ajax({ url: "file.php" });

request.done(function(data) {
    console.log("Success: " + data);
});

request.fail(function(err) {
    console.log("Error: " + err);
});

request.always(function() {
    console.log("Request complete");
});

```
$.Deferred() and .promise() allow better control of async operations.

#### 5. Utilities
<h6>

| **Method**                     | **Description**             | **Example**                |
| ------------------------------ | --------------------------- | -------------------------- |
| `$.each(array, fn)`            | Loop through array / object | `$.each([1,2,3], fn)`      |
| `$.trim(str)`                  | Remove whitespace           | `$.trim(" hello ")`        |
| `$.type(obj)`                  | Get type                    | `$.type([])` → `"array"`   |
| `$.extend(target, obj1, obj2)` | Merge objects               | `$.extend({}, obj1, obj2)` |
| `$.isArray(obj)`               | Check array                 | `$.isArray([1,2])`         |
| `$.isFunction(obj)`            | Check function              | `$.isFunction(fn)`         |
| `$.proxy(fn, context)`         | Change context of function  | `$.proxy(fn, obj)`         |

 
</h6>

#### 6. Event Delegation
```js
$(document).on("click", ".dynamic-btn", function() {
    alert("Button clicked!");
});
```
- Useful for dynamically added elements.
- .on(event, selector, handler) replaces .live() and .delegate().

#### 7. Data Storage

```js
$("#box").data("key", "value");  // Store data
console.log($("#box").data("key")); // Retrieve data
```

- .data() allows storing custom data directly on DOM elements.
- Plugins: jQuery UI, sliders, modals, date pickers.
- Performance tips: use caching, minimize DOM lookups.

---
<br>
<br>
<br>



# 🔹 10. Responsive + jQuery
[Hom](#table-of-contents)

#### Toggle menu on mobile:
```js
$("#menu-btn").click(function() {
  $("#nav").toggle();
});
```

#### 1. Window Resize Event
```js
$(window).resize(function() {
    let width = $(window).width();
    console.log("Window width: " + width);

    if (width < 768) {
        $("#menu").hide();
    } else {
        $("#menu").show();
    }
});
```

- .resize() → Triggered when window size changes.
- Useful for adjusting elements dynamically.

#### 2. Dynamic CSS based on Screen Size
```js
if ($(window).width() < 768) {
    $("body").css("background", "lightblue");
} else {
    $("body").css("background", "white");
}
```
Combine jQuery with conditional statements to apply styles responsively.

#### 3. Responsive Classes
```js
$(window).on("resize", function() {
    if ($(window).width() < 600) {
        $("#box").addClass("small").removeClass("large");
    } else {
        $("#box").addClass("large").removeClass("small");
    }
});
```
.addClass() / .removeClass() → Toggle classes for responsiveness.

#### 4. Hide/Show Navigation on Mobile
```
$("#menu-toggle").click(function() {
    $("#menu").slideToggle();  // Show/hide menu smoothly
});
```
Useful for hamburger menus.

5. Detect Device Orientation
```js
$(window).on("orientationchange", function() {
    if (window.orientation == 0 || window.orientation == 180) {
        console.log("Portrait mode");
    } else {
        console.log("Landscape mode");
    }
});
```

.orientationchange → Detect mobile orientation.

6. Responsive Images

```js
if ($(window).width() < 500) {
    $("#img1").attr("src", "small.jpg");
} else {
    $("#img1").attr("src", "large.jpg");
}
```

.attr() → Change image sources based on screen width.

7. Smooth Scroll & Responsive Sections
```js
$("a.scroll-link").click(function(e) {
    e.preventDefault();
    let target = $(this).attr("href");
    $("html, body").animate({ scrollTop: $(target).offset().top }, 800);
});
```
Smooth scroll improves UX on responsive single-page layouts.