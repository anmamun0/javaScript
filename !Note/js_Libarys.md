# JavaScript Libraries Collection

A curated list of popular JavaScript libraries for various web development needs.

## 📌 Library Comparison Table
<h6> 

| **Library**     | **Best For**                 | **Why Use It?** |
|---------------|----------------------------|----------------|
| [**Quill.js**](#-1-quilljs)   | Rich text editor          | Perfect for **blogs, CMS, and forms** with customizable toolbars and themes. |
| [**Swiper.js**](#-2-swiperjs)  | Touch slider              | Ideal for **carousels and slideshows**, supports mobile gestures. |
| [**AOS.js**](#-3-aosjs)       | Scroll animations         | Adds smooth animations on scroll for **landing pages and portfolios**. |
| [**Chart.js**](#-4-chartjs)     | Data visualization        | Helps create **interactive charts and graphs** for dashboards and analytics. |
| [**GSAP.js**](#-5-gsapjs)      | Advanced animations       | Used for **high-performance animations and interactive UIs**. |
| [**TinyMCE**](#-6-tinymce)      | Advanced text editor      | Provides a **word-processor-like experience** with formatting, spell check, and media embedding. |
| [**Glide.js**](#-7-glidejs)     | Lightweight slider        | A **faster, lightweight alternative to Swiper.js**, supports **Vue.js & React**. |
| [**Three.js**](#-8-threejs)    | 3D graphics               | Enables the creation of **3D models, animations, and interactive elements** for games and VR. |
| [**Lenis.js**](#-9-lenisjs)     | Smooth scrolling          | Ensures **buttery smooth scrolling** with optimized performance. |
| [**Anime.js**](#-10-animejs)     | Advanced animations       | Supports **SVG, DOM elements, and JavaScript objects** for smooth, complex animations. |
| [**Masonry.js**](#-11-masonryjs)   | Grid layouts              | Creates **Pinterest-style layouts**, ensuring elements are arranged properly. |
| [**Plyr.js**](#-12-plyrjs)      | Custom video players      | Modern, lightweight **video player** with themes, captions, and controls. |
| [**Howler.js**](#-13-howlerjs)    | Audio playback            | Best for **handling multiple audio tracks**, supports **looping, crossfade, and spatial audio**. |
| [**Tippy.js**](#-14-tippyjs)     | Tooltips                  | Provides **highly customizable tooltips** that enhance user experience. |
| [**FullPage.js**](#-15-fullpagejs)   | Full-screen scrolling    | Ideal for **portfolios and one-page websites** with smooth transitions. |


</h6>

## 📌 Installation & Usage

Each library has its own setup and installation method. You can typically install them using npm or a CDN.

```sh
npm install swiper chart.js gsap quill animejs masonry-layout three fullpage.js plyr howler tippy.js lenis
```


#### JavaScript Libraries Overview

<h5> 

- This project showcases the best libraries for enhancing web development with powerful features for animations, text editing, media playback, and more. Each section contains an example and why you should consider using these libraries for your web projects. 
</h5>

---

### 🔥 1. Quill.js 
#### 📌 Why use it?

- Provides a modern WYSIWYG editor.
- Highly customizable (themes, toolbar, keyboard shortcuts).
- Works with React, Vue, Angular, and vanilla JavaScript.

#### 📝 Example: Rich Text Editor
```html
<!-- Include Quill.js CSS -->
<link href="https://cdn.quilljs.com/1.3.6/quill.snow.css" rel="stylesheet">

<!-- Create the editor container -->
<div id="editor"></div>

<!-- Include Quill.js JavaScript -->
<script src="https://cdn.quilljs.com/1.3.6/quill.js"></script>

<script>
  // Initialize Quill editor with 'snow' theme
  var quill = new Quill('#editor', { theme: 'snow' });
</script>

```


```
 <!-- Rich Text Editor -->
<div>
  <label for="description" class="block text-sm font-semibold text-gray-700">Course Description</label>                      
    <!-- Rich Text Editor (contenteditable div) -->

  <div id="editor" class="mt-2 bg-white rounded-lg border border-gray-300 p-3 resize-none overflow-auto shadow-sm focus:ring-1 focus:ring-slate-400 focus:outline-none"  contenteditable="true" style="height: calc(1.5em * 9);">
  </div>
                                
  <!-- Hidden Input Field -->
    <input type="hidden" id="description" name="description" required />

</div>

// Initialize Quill.js editor
var quill = new Quill('#editor', {
  theme: 'snow',
  placeholder: "Write the course description here...",
  modules: {
    toolbar: [
      [{ header: [1, 2, 3, 4, 5, 6, false] }],
      [{ font: [] }],
      [{ size: ['small', false, 'large', 'huge'] }],
      ['bold', 'italic', 'underline', 'strike'],
      [{ color: [] }, { background: [] }],
      [{ script: 'sub' }, { script: 'super' }],
      [{ list: 'ordered' }, { list: 'bullet' }],
      [{ indent: '-1' }, { indent: '+1' }],
      [{ direction: 'rtl' }],
      [{ align: [] }],
      ['blockquote', 'code-block'],
      ['link', 'image', 'video'],
      ['clean'] // Remove formatting button
    ]
  }
});
```

### 🎡 2. Swiper.js 
##### 📌 Why use it?

- Best for image carousels, sliders, and scrolling sections.
- Supports touch gestures (mobile-friendly).
- High performance with smooth animations.
🖼 Example: Image Slider

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.css">
<div class="swiper">
  <div class="swiper-wrapper">
    <div class="swiper-slide"><img src="https://source.unsplash.com/400x300/?nature" /></div>
    <div class="swiper-slide"><img src="https://source.unsplash.com/400x300/?city" /></div>
    <div class="swiper-slide"><img src="https://source.unsplash.com/400x300/?ocean" /></div>
  </div>
  <div class="swiper-pagination"></div>
</div>
<script src="https://cdn.jsdelivr.net/npm/swiper/swiper-bundle.min.js"></script>
<script>
  new Swiper('.swiper', { pagination: { el: '.swiper-pagination', clickable: true } });
</script>

```




### 🔎 3. AOS.js 
##### 📌 Why use it?

- Adds scroll animations to elements.
- Works with CSS animations.
- Improves user engagement.
✨ Example: Scroll Animation

```
<link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css">
<div data-aos="fade-up">Fade Up Animation</div>
<script src="https://unpkg.com/aos@next/dist/aos.js"></script>
<script> AOS.init(); </script>

```


### 📊 4. Chart.js 
##### 📌 Why use it?

- Makes beautiful charts (bar, line, pie, etc.).
- Lightweight and easy to integrate.
- Great for dashboards and reports.
📈 Example: Line Chart


```
<canvas id="myChart"></canvas>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  new Chart(document.getElementById('myChart'), {
    type: 'line',
    data: { labels: ['Jan', 'Feb', 'Mar'], datasets: [{ label: 'Sales', data: [10, 20, 30], borderColor: 'blue' }] }
  });
</script>

```


### 🌙 5. GSAP.js 
##### 📌 Why use it?

- Best for smooth, high-performance animations.
- Can animate SVG, text, and DOM elements.
- Used in professional web design.
🚀 Example: Smooth Animation

```
<div id="box" style="width:100px;height:100px;background:red;"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script> gsap.to("#box", { x: 300, duration: 2, ease: "bounce.out" }); </script>

```




### 📝 6. TinyMCE 
##### 📌 Why use it?

- Similar to Quill.js, but more advanced.
- Provides a complete word-processor-like experience.
- Comes with built-in spell check, image uploading, and formatting.
Example: Text Editor


```
<script src="https://cdn.tiny.cloud/1/no-api-key/tinymce/5/tinymce.min.js"></script>
<textarea id="myeditor"></textarea>
<script>
  tinymce.init({ selector: '#myeditor' });
</script>

```


### 🏆 7. Glide.js 
##### 📌 Why use it?

- Faster and lighter than Swiper.js.
- Works with Vue.js & React.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@glidejs/glide/dist/css/glide.core.min.css">
<div class="glide">
  <div class="glide__track" data-glide-el="track">
    <ul class="glide__slides">
      <li class="glide__slide">1</li>
      <li class="glide__slide">2</li>
      <li class="glide__slide">3</li>
    </ul>
  </div>
</div>
<script src="https://cdn.jsdelivr.net/npm/@glidejs/glide"></script>
<script> new Glide('.glide').mount(); </script>

```

### 🎨 8. Three.js 
##### 📌 Why use it?

- Create 3D models, animations, and interactive elements.
- Used for games, VR, and web experiments.
Example: 3D Cube

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
  let scene = new THREE.Scene();
  let camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
  let renderer = new THREE.WebGLRenderer();
  document.body.appendChild(renderer.domElement);
  let geometry = new THREE.BoxGeometry();
  let material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
  let cube = new THREE.Mesh(geometry, material);
  scene.add(cube);
  camera.position.z = 5;
  function animate() { requestAnimationFrame(animate); cube.rotation.x += 0.01; cube.rotation.y += 0.01; renderer.render(scene, camera); }
  animate();
</script>

```

 
### 🔥 9. Lenis.js 
##### 📌 Why use it?

- Provides buttery smooth scrolling effects.
- Works with GSAP, LocomotiveScroll.
Example: Smooth Scroll


```
<script src="https://cdn.jsdelivr.net/npm/@studio-freight/lenis"></script>
<script>
  const lenis = new Lenis();
  function raf(time) { lenis.raf(time); requestAnimationFrame(raf); }
  requestAnimationFrame(raf);
</script>

```


### 🎭 10. Anime.js 
##### 📌 Why use it?

- Better control over animations than GSAP.
- Can animate SVG, CSS, and JS objects.
Example: Animated Box

```
<div id="box" style="width:100px;height:100px;background:red;"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
<script>
  anime({ targets: '#box', translateX: 250, duration: 2000, easing: 'easeOutElastic' });
</script>

```




### 🏗 11. Masonry.js 
##### 📌 Why use it?

- Creates Pinterest-style layouts.
- Auto-resizes images & cards.
Example: Masonry Layout

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/masonry/4.2.2/masonry.pkgd.min.js"></script>
<script>
  new Masonry('.grid', { itemSelector: '.grid-item', columnWidth: 200 });
</script>

```



### 🎥 12. Plyr.js 
#####📌 Why use it?

- A beautiful alternative to YouTube/Vimeo players.
- Supports captions, themes, and keyboard shortcuts.
Example: Custom Video Player


```
<link rel="stylesheet" href="https://cdn.plyr.io/3.6.8/plyr.css">
<video id="player" controls>
  <source src="video.mp4" type="video/mp4">
</video>
<script src="https://cdn.plyr.io/3.6.8/plyr.js"></script>
<script> const player = new Plyr('#player'); </script>

```



### 🎙 13. Howler.js 

##### 📌 Why use it?

- Better than the default HTML5 Audio API.
- Supports looping, crossfade, and 3D sound.
Example: Play Audio

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/howler/2.2.3/howler.min.js"></script>
<script>
  var sound = new Howl({ src: ['sound.mp3'] });
  sound.play();
</script>

```



### 🛠 14. Tippy.js 

#####📌 Why use it?

- Beautiful tooltips for buttons and icons.
- Works with Popper.js.
Example: Tooltip



```
<button id="myButton">Hover me</button>
<script src="https://unpkg.com/@popperjs/core@2"></script>
<script src="https://unpkg.com/tippy.js@6"></script>
<script> tippy('#myButton', { content: 'I am a tooltip!' }); </script>


```

### 🎯 15. FullPage.js 
##### 📌 Why use it?

- Creates full-screen, smooth-scrolling websites.
- Used for portfolio, one-page websites.
Example: Full-Screen Sections

```
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/4.0.17/fullpage.min.css">
<div id="fullpage">
  <div class="section">Welcome</div>
  <div class="section">About</div>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/4.0.17/fullpage.min.js"></script>
<script> new fullpage('#fullpage'); </script>

```


