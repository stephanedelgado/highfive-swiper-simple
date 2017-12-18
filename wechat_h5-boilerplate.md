---
layout: reveal
---

<!-- Launch .md file from terminal -->
<!-- reveal-md --vertical-separator “\n--\n” --theme solarized h5.md -->

# Simple WeChat H5 boilerplate

All you need to launch the most classic H5 ever!

### [Demo here](https://tgenaitay.github.io/wechat-H5/)


--

## Includes:

- No unnecessary libraries

- No gulp, no bullshit

- Simple swiper

- Optional music

- Optional pagination

- Optional desktop view detector

- SEO-friendly site meta-data

  ​


---

## Swiper: Open Source Library

Website: http://idangero.us/swiper/

--

### 1. Download files: [Swiper GitHub repository](https://github.com/nolimits4web/Swiper/tree/master/dist)

--

### 2. Include Swiper Files 

After that we need to include Swiper's CSS and JS files to our website/app. In your html file:

```html
<!DOCTYPE html>
<html lang="en">

	<head>
    	...
    	<link rel="stylesheet" href="./css/swiper.min.css">
	</head>

	<body>
    	...
    	<script src="https://lib.sinaapp.com/js/jquery/3.1.0/jquery-3.1.0.js"></script>
    	<script src=“./js/swiper.jquery.min.js"></script>
	</body>
	
</html>
```
--

### 3. Add Swiper HTML Layout

Now, we need to add a basic Swiper layout in html body:

```html
<!-- Slider main container -->
<div class="swiper-container">

    <!-- Additional required wrapper -->
    <div class="swiper-wrapper">

        <!-- Slides -->
        <div class="swiper-slide">Slide 1</div>
        <div class="swiper-slide">Slide 2</div>
        <div class="swiper-slide">Slide 3</div>
        ...
        
    </div>
</div>
```
--
### 3. Add Swiper HTML Layout

Let’s see what we’re playing with and **inspect the two classes** `.swiper-container` and `.swiper-wrapper`

--

### 4. Swiper CSS - Style & Sizes

Let’s create a `style.css` file, and include it the `<head>` of our html:

```html
<!DOCTYPE html>
<html lang="en">

	<head>
    	...
    	<link rel="stylesheet" href="./css/swiper.min.css">   
    	<link rel="stylesheet" href="./css/style.css">
	</head>

```
--

### 4. Swiper CSS - Style & Sizes

We can then declare a Swiper size in our CSS file:


```css
body {
  margin: 0;
  font-family: "Arial", sans-serif;
  font-size: 20px;
}

.swiper-container {
	height: 100vh;
	background-color: #4E2381;
	color: #EAEAEA;
}      
```

--

### 5. Initialize Swiper

Finally, we need to initialize Swiper in a separate file:
Let’s create a `main.js` file, and include it at the very end of our html - right before closing `</body>`:

```html
<!DOCTYPE html>
<html lang="en">

	<head>
    	...
	</head>

	<body>
    	...
		<script src=“./js/main.js”></script>
	</body>
	
</html>
```
--

## Inside the main.js

We will use jQuery, call within `document.ready` event to initialize the Swiper 

```javascript
$(document).ready(function () {
    //initialize swiper when document ready  
    
    var mySwiper = new Swiper ('.swiper-container', {
        // Optional parameters
        direction: 'vertical',
        loop: true
    })        
    
});
```

--

Add more swiper effects: more at [swiper api doc](http://idangero.us/swiper/api/)

```javascript
var mySwiper = new Swiper ('.swiper-container', {
    direction: 'vertical',
    speed: 500,
    effect: 'slide',
    keyboardControl: true,
    loop: false
})
```


---

## Navigation

[Different ways to go between pages!](http://idangero.us/swiper/demos)

--

### Pagination

#### html:
```html
 <!-- If we need pagination -->
 <div class="swiper-pagination"></div>
```
#### js:

```js
var mySwiper = new Swiper ('.swiper-container', {
    // Optional parameters
    direction: 'vertical',
    loop: true,
    
    // If we need pagination
    pagination: '.swiper-pagination',
})        
```

--

### Arrows

#### html:
```html
<!-- If we need navigation buttons -->
<div class="swiper-button-prev"></div>
<div class="swiper-button-next"></div>
```
#### js:

```js
var mySwiper = new Swiper ('.swiper-container', {
    ...
    
    // If we need navigation arrows
    nextButton: '.swiper-button-next',
    prevButton: '.swiper-button-prev',
    
    ...
})        
```

--

### Scrollbar

#### html:
```html
<!-- If we need scrollbar -->
<div class="swiper-scrollbar"></div>
```
#### js:

```js
var mySwiper = new Swiper ('.swiper-container', {
    ...
    
    // If we need a scrollbar
    scrollbar: '.swiper-scrollbar',
    
    ...
})        
```


---

## Animations

#### html (head):

Download the css file at [Animate.css](https://daneden.github.io/animate.css) and link it in the `<head>`

```html
<head>
...
	<link rel=“stylesheet” href=“./css/swiper.min.css”>   
	<link rel=“stylesheet” href=“./css/animate.css”>
	<link rel=“stylesheet” href=“./css/style.css”>
</head>
```

--

#### html (body):

```html
<body>
...
	<!-- Slider main container -->
	<div class="swiper-container">
		<!-- Additional required wrapper -->
		<div class="swiper-wrapper">
      		<!-- My slides -->
      		<!-- Get all animation names from https://daneden.github.io/animate.css -->
          <div class="swiper-slide slide-1">
      			<h2 class="animated" data-ani-name="slideInRight" data-ani-duration="1.3s" data-ani-delay="0s">Experimental core</h2>
      			<p class="animated" data-ani-name="slideInRight" data-ani-duration="1.6s" data-ani-delay="0s">Photography exhibition. From 				sweeping landscape scenes to powerful portraits captured by daring individuals, photography in London offers a full-exposure 				of thought-provoking, visually captivating art. Look away from the Instagram feed for just a minute and go explore.</p>
				<!--<div class=“polygon polygon-left animated” data-ani-name=“slideInLeft” data-ani-duration=“1s” data-ani-delay=“0.5s”>
      			</div>	-->
      		</div>
          <div class="swiper-slide slide-2”>
      			<h2 class="animated" data-ani-name="slideInLeft" data-ani-duration="1.3s" data-ani-delay="0s">Abstract painting</h2>
      			<p class="animated" data-ani-name="slideInLeft" data-ani-duration="1.6s" data-ani-delay="0s">Photography exhibition. From 				sweeping landscape scenes to powerful portraits captured by daring individuals, photography in London offers a full-exposure 				of thought-provoking, visually captivating art. Look away from the Instagram feed for just a minute and go explore.</p>
      		</div>
          <div class="swiper-slide slide-3”>
      			<h2 class="animated" data-ani-name="slideInRight" data-ani-duration="1.3s" data-ani-delay="0s">Documenting photography</h2>
      			<p class="animated" data-ani-name="slideInRight" data-ani-duration="1.6s" data-ani-delay="0s">Photography exhibition. From 				sweeping landscape scenes to powerful portraits captured by daring individuals, photography in London offers a full-exposure 				of thought-provoking, visually captivating art. Look away from the Instagram feed for just a minute and go explore.</p>
      		</div>          
      </div>
  </div>
...
</body>
```
We can test the animation by removing attributes and adding `.slideInRight` and `.infinite`  class

--

#### js (in swiper):
But we want the animations to only play when each slide appears:

```js
var mySwiper = new Swiper ('.swiper-container', {
    ...
    onInit: function (swiper) {
        initAnimation();
        // get items ready for animations
        playAnimations(swiper);
        // play animations of the first slide
    },
    onSlideChangeStart: function (swiper) {
        playAnimations(swiper);
        // play animations at each slide
    },
 
    loop: false
})
```
--

#### js (after swiper):

```js
function initAnimation() {
    $('.animated').each(function () {
            $(this).attr('data-origin-class', $(this).attr('class'));
            var aniDuration = $(this).data('ani-duration');
            var aniDelay = $(this).data('ani-delay');
            $(this).css({
                'visibility': 'hidden',
                'animation-duration': aniDuration,
                'animation-delay': aniDelay,
            });
        });
    }

function clearAnimations() {
    $('.animated').each(function () {
        $(this).css({ 'visibility': 'hidden' });
        $(this).attr('class', $(this).data('origin-class'));
    });
}

function playAnimations(mySwiper) {

    clearAnimations();
    // put back original class

    var aniItems = mySwiper.slides[mySwiper.activeIndex].querySelectorAll('.animated');
    // select items of current slide

    $(aniItems).each(function () {
        $(this).css({ 'visibility': 'visible' });
        var aniName = $(this).data('ani-name');
        $(this).addClass(aniName);
        // add class to launch animation
    });
}
```

---

## Fontawesome
can be used for icons

```html
<head>
   ...
    <link href="https://apps.bdimg.com/libs/fontawesome/4.1.0/css/font-awesome.min.css" rel="stylesheet">
    ...
</head>
```

---

## Smart Navigation

#### html:
```html
<button class="arrow-up“><i class="fa fa-angle-double-up" aria-hidden="true"></i></button>
```

#### js:
```js
var $upArrow = $('.arrow-up');

var mySwiper = new Swiper ('.swiper-container', {
	...
    onReachEnd: function (swiper) {
    	$upArrow.hide();
    },
    onSlidePrevStart: function (swiper) {
        $upArrow.show();
    },
    loop: false
})
```

---

## How to make a polygon
We can use [clippy](https://bennettfeely.com/clippy) and declare the `clip-path` css attribute:

```css
.polygon {
  height: 100vh;
  background-size: cover;
  background-position: center;
}

.polygon-left {
  -webkit-clip-path: polygon(0 40%, 100% 29%, 100% 100%, 0% 100%);
  clip-path: polygon(0 40%, 100% 29%, 100% 100%, 0% 100%);
}

.polygon-right {
  -webkit-clip-path: polygon(0 29%, 100% 40%, 100% 100%, 0% 100%);
  clip-path: polygon(0 29%, 100% 40%, 100% 100%, 0% 100%);
}

.polygon-content {
  position: absolute;
  padding: 0 3%;
}
```

---

## Audio

```html
<button class="btn-music"><i class="fa fa-music"></i></button>
<audio loop><source src="audios/background.mp3" type="audio/mpeg"></audio>
```

---

## Mobile-Only

```html
<div id="orientLayer" class="mod-orient-layer">
    <div class="mod-orient-layer-content">
        <i class="mod-orient-layer-icon-orient"></i>
        <div class="mod-orient-layer-desc">为了更好的体验，请使用竖屏浏览</div>
        <div class="mod-orient-layer-desc">For a better experience, please view in mobile</div>
    </div>
</div>
```


---

## Loading Toast

#### html:
```html
<div class="loading-overlay">
    <img src="images/loading.svg">
</div>
```
and at the end of main.js

#### js:
```js
$('.loading-overlay').slideUp();
// hide loading animation since everything is ready
```


---

## Site Title, Icon, SEO (Meta), Viewport

```html
<head>
    <meta charset="UTF-8">
    <title>Wechat H5 Boilerplate</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <meta name="keywords" content="wechat h5 template lewagon workshop swiper js animation">
    <meta name="description" content="A nifty multi-page h5 template with swiper.js - Le Wagon">
	<link rel="shortcut icon" type="image/png" href="images/favicon.png"/>

    ...
</head>
```


---



# Let's get started with your own H5! 