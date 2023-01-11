# Anime.js
##### Anime.js Research...
```
Anime.js is a JavaScript animation library that allows you to animate elements on a website. It is lightweight and works with CSS, SVG, DOM attributes, and JavaScript Objects. It uses a declarative syntax to specify the animations, making it easy to use and understand. It also has a wide range of built-in easing functions and support for keyframe animations. It was created by Julian Garnier and it's open-source under the MIT license.
```
It is often used for creating complex and subtle animations on a website. Some of the key features of anime.js include: support for various types of animations, like SVG or DOM attributes; wide range of easing functions to control the animation speed; keyframe animations for creating complex, multi-step animations; and a small file size, which can help with website performance.

Researching the Anime.js library is important for frontend developers because it allows them to create complex and subtle animations on a website with ease.

The library uses a declarative syntax to specify the animations, making it easy to understand and use. Additionally, it has a wide range of built-in easing functions and support for keyframe animations which gives developers more control over animation and makes it more flexible.

Animations can enhance the user experience by making a website more interactive and engaging. By having knowledge of a library such as Anime.js, frontend developers are able to implement animations on their websites more efficiently and effectively, which can lead to a better user experience.

Furthermore, since the library is lightweight and efficient, it can help improve the performance of a website, which is important for a good user experience.

Anime.js also has support for SVG, DOM attributes and JavaScript Objects which give developers a wide range of options to target and animate different elements on the web page.

Overall, researching the Anime.js library is important for frontend developers because it allows them to create complex and subtle animations with ease, improve the performance of a website and enhance the user experience.

The documentation tree is comprehensive and comprehensive, it's well organized and easy to follow for anyone looking to use Anime.js for web animations.

# Targets section covers different way to select element to animate.
## The "Targets" section of the Anime.js documentation explains the different ways to select elements to animate.
### Targets Cheat Sheet:

| Target Type | Description | Example |
| --- | --- | --- |
| CSS Selector | Selects elements using a CSS selector. Can't target Pseudo elements using javascript | `anime({targets: '.css-selector-demo .el', translateX: 250});`|
| DOM Node / NodeList | Can be any DOM Node or NodeList. Can use `querySelector` and `querySelectorAll` to select DOM element |  `var elements = document.querySelectorAll('.dom-node-demo .el'); anime({ targets: elements, translateX: 270 });`|
| JavaScript Object | A JavaScript Object with at least one property containing a numerical value. | `var logEl = document.querySelector('.battery-log'); var battery = { charged: '0%', cycles: 120 } anime({ targets: battery, charged: '100%', cycles: 130, round: 1, easing: 'linear', update: function(){logEl.innerHTML = JSON.stringify(battery);}});` |
| Array | An array containing multiple targets, mixed types are accepted. e.g. ['.el', domNode, jsObject] | `var el = document.querySelector('.mixed-array-demo .el-01'); anime({ targets: [el, '.mixed-array-demo .el-02', '.mixed-array-demo .el-03'], translateX: 250 });`


Please note, these are just examples, you may use other animation properties, values or events based on your requirement.


    CSS Selector

    CSS Selector: allows you to select elements using a CSS selector. In this way you can target multiple elements on the page at once and also you can't target Pseudo elements using javascript.


Can be any CSS selector.

Pseudo elements can't be targeted using JavaScript.
Type 	Default 	Example
String 	null 	targets: '.item'
Code example
```
anime({
  targets: '.css-selector-demo .el',
  translateX: 250
});

```
    DOM Node / NodeList
  DOM Node / NodeList: allows you to select DOM nodes or a NodeList, you can use the querySelector and querySelectorAll to select DOM element.

Can be any DOM Node or NodeList.
Type 	Default 	Example
DOM Node 	null 	targets: el.querySelector('.item')
NodeList 	null 	targets: el.querySelectorAll('.item')
Code example
```
var elements = document.querySelectorAll('.dom-node-demo .el');

anime({
  targets: elements,
  translateX: 270
});
```

    JavaScript Object

    JavaScript Object: you can animate properties of a JavaScript Object. The object needs to have at least one property with numerical value.

A JavaScript Object with at least one property containing a numerical value.
Type 	Default 	Example
Object 	null 	targets: myObjectProp
Code example

var logEl = document.querySelector('.battery-log');

var battery = {
  charged: '0%',
  cycles: 120
}

anime({
  targets: battery,
  charged: '100%',
  cycles: 130,
  round: 1,
  easing: 'linear',
  update: function() {
    logEl.innerHTML = JSON.stringify(battery);
  }
});


    Array
  

    Array: you can use an array of mixed types (CSS selector, DOM node, JavaScript object) to target multiple elements and animate them at once.

An array containing multiple targets.

Accepts mixed types. E.g. ['.el', domNode, jsObject]
Type 	Default 	Example
Array 	null 	targets: ['.item', el.getElementById('#thing')]
Code example
```
var el = document.querySelector('.mixed-array-demo .el-01');

anime({
  targets: [el, '.mixed-array-demo .el-02', '.mixed-array-demo .el-03'],
  translateX: 250
});

```

```These different options for targeting elements give developers flexibility and control over which elements to animate and how to animate them.```


    Properties covers different way to animate DOM, CSS, SVG, Object properties and attributes

The "Properties" section of the Anime.js documentation explains the different ways to animate elements, including CSS, CSS Transforms, Object properties, DOM attributes, and SVG attributes.

| Property type       | Description                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------|
| CSS Properties      | Any CSS properties can be animated. Prioritize opacity and CSS transforms to prevent choppy animation. |
| CSS Transforms      | Animate CSS transform properties individually. Specify different timing for each transform property. |
| Object Properties   | Any Object property containing a numerical value can be animated. |
| DOM Attributes      | Any DOM attributes containing a numerical value can be animated.  |
| SVG Attributes      | All SVG attributes containing at least one numerical value can be animated. |

  
CSS Properties
  CSS Properties: Allows you to animate any css properties and need to be careful because this can cause layout change and repaint. Prioritizing opacity and CSS transforms can prevent choppy animation.

 
Any CSS properties can be animated.

Most CSS properties will cause layout changes or repaint, and will result in choppy animation. Prioritize opacity and CSS transforms as much as possible.

More details about accepted values in the values section.
Example 	value
opacity 	.5
left 	'100px'
Code example
```
anime({
  targets: '.css-prop-demo .el',
  left: '240px',
  backgroundColor: '#FFF',
  borderRadius: ['0%', '50%'],
  easing: 'easeInOutQuad'
});
```


CSS Transforms
   CSS Transforms: allows you to animate transform properties individually. it is possible to specify different timing for each transform property.


Animate CSS transforms properties individually.

It's possible to specify different timing for each transforms properties, more details in the specific property parameters section.

More details about accepted values in the values section.
Valid properties 	Default unit
'translateX'	'px'
'translateY'	'px'
'translateZ'	'px'
'rotate'	'deg'
'rotateX'	'deg'
'rotateY'	'deg'
'rotateZ'	'deg'
'scale'	—
'scaleX'	—
'scaleY'	—
'scaleZ'	—
'skew'	'deg'
'skewX'	'deg'
'skewY'	'deg'
'perspective'	'px'
Code example
```
anime({
  targets: '.css-transforms-demo .el',
  translateX: 250,
  scale: 2,
  rotate: '1turn'
});

```

Object properties
    Object properties: Any object property containing a numerical value can be animated.

  
Any Object property containing a numerical value can be animated.
More details about accepted values in the values section.
Example 	value
prop1 	50
'prop2' 	'100%'
Code example
```
var objPropLogEl = document.querySelector('.js-object-log');

var myObject = {
  prop1: 0,
  prop2: '0%'
}

anime({
  targets: myObject,
  prop1: 50,
  prop2: '100%',
  easing: 'linear',
  round: 1,
  update: function() {
    objPropLogEl.innerHTML = JSON.stringify(myObject);
  }
});
```

DOM Attributes
  DOM attributes: Any DOM attributes containing a numerical value can be animated.


Any DOM Attributes containing a numerical value can be animated.
More details about accepted values in the values section.
Example 	value
value 	1000
volume 	0
data-custom 	'3 dogs'
Code example
```
anime({
  targets: '.dom-attribute-demo input',
  value: [0, 1000],
  round: 1,
  easing: 'easeInOutExpo'
});
```


SVG Attributes
    SVG Attributes: SVG attributes containing at least one numerical value can be animated


Like any other DOM attributes, all SVG attributes containing at least one numerical value can be animated.
More details about accepted values in the values section and SVG animation in the SVG section.
Example 	value
points 	'64 68.64 8.574 100 63.446 67.68 64 4 64.554 67.68 119.426 100'
scale 	1
baseFrequency 	0
Code example
```
anime({
  targets: ['.svg-attributes-demo polygon', 'feTurbulence', 'feDisplacementMap'],
  points: '64 128 8.574 96 8.574 32 64 0 119.426 32 119.426 96',
  baseFrequency: 0,
  scale: 1,
  loop: true,
  direction: 'alternate',
  easing: 'easeInOutExpo'
});
```

Each of these animation types provides developers with different options for creating animations, giving them flexibility and control over the animation. Additionally, the More details about accepted values in the values section section of the documentation provides further details on the types of values that can be used to animate elements.


    Property parameters covers the way you could control the animation like Duration, Easing and Round etc.

    Animation parameters: provides details on how to control various aspects of the animation, such as the loop and autoplay settings.

    Values: covers how to define the values used in animations, including different units and functions

    Keyframes: explains how to create animations using keyframes

    Staggering: covers how to create stagger effect on animations

    Timeline: explains how to create and control timeline animations

    Controls: covers how to control the animations like Play/Pause, reverse, seek etc

    Callbacks & Promises: explains how to use callbacks and promises to execute code at certain points during an animation.

    SVG: provides information on how to use the library to animate SVG elements.

    Easings: covers the different easing functions available in the library and how to create custom easing functions

    Helpers: provides information on some useful helper functions like remove, get, set and random etc.

The documentation tree is like this:     

    Targets
    CSS Selector
    DOM Node / NodeList
    JavaScript Object
    Array
    
    Properties
    CSS Properties
    CSS Transforms
    Object properties
    DOM Attributes
    SVG Attributes
    
    Property parameters
    Duration
    Delay
    end delay
    Easing
    Round
    Specific property parameters
    Function based parameters
    
    Animation parameters
    Direction
    Loop
    Autoplay
    
    Values
    Unitless
    Specific unit
    Relative
    Colors
    From To
    Function based values
    
    Keyframes
    Animation keyframes
    Property keyframes
    
    Staggering
    Staggering basics
    Start value
    Range value
    From value
    Direction
    Easing
    Grid
    Axis
    
    Staggering
    Staggering basics
    Start value
    Range value
    From value
    Direction
    Easing
    Grid
    Axis

    Timeline
    Timeline basics
    Time Offsets
    Parameters inheritance
    
    Controls
    Play / Pause
    Restart
    Reverse
    Seek
    Timeline controls
    
    Callbacks & Promises
    Update
    Begin & Complete
    loopBegin & loopComplete
    Change
    changeBegin & changeComplete
    Finished promise
    
    SVG
    Motion path
    Morphing
    Line drawing
    
    Easings
    Linear
    Penner's functions
    Cubic Bézier Curve
    Spring
    Elastic
    Steps
    Custom easing function
    
    
    Helpers
    remove
    get
    set
    random
    tick
    running
    Suspend on visibility change
    
    
    
# Anime.js
##### Anime.js Research...
```
Anime.js is a JavaScript animation library that allows you to animate elements on a website. It is lightweight and works with CSS, SVG, DOM attributes, and JavaScript Objects. It uses a declarative syntax to specify the animations, making it easy to use and understand. It also has a wide range of built-in easing functions and support for keyframe animations. It was created by Julian Garnier and it's open-source under the MIT license.
```
It is often used for creating complex and subtle animations on a website. Some of the key features of anime.js include: support for various types of animations, like SVG or DOM attributes; wide range of easing functions to control the animation speed; keyframe animations for creating complex, multi-step animations; and a small file size, which can help with website performance.

Researching the Anime.js library is important for frontend developers because it allows them to create complex and subtle animations on a website with ease.

The library uses a declarative syntax to specify the animations, making it easy to understand and use. Additionally, it has a wide range of built-in easing functions and support for keyframe animations which gives developers more control over animation and makes it more flexible.

Animations can enhance the user experience by making a website more interactive and engaging. By having knowledge of a library such as Anime.js, frontend developers are able to implement animations on their websites more efficiently and effectively, which can lead to a better user experience.

Furthermore, since the library is lightweight and efficient, it can help improve the performance of a website, which is important for a good user experience.

Anime.js also has support for SVG, DOM attributes and JavaScript Objects which give developers a wide range of options to target and animate different elements on the web page.

Overall, researching the Anime.js library is important for frontend developers because it allows them to create complex and subtle animations with ease, improve the performance of a website and enhance the user experience.

The documentation tree is comprehensive and comprehensive, it's well organized and easy to follow for anyone looking to use Anime.js for web animations.

# Targets section covers different way to select element to animate.
## The "Targets" section of the Anime.js documentation explains the different ways to select elements to animate.
### Targets Cheat Sheet:

| Target Type | Description | Example |
| --- | --- | --- |
| CSS Selector | Selects elements using a CSS selector. Can't target Pseudo elements using javascript | `anime({targets: '.css-selector-demo .el', translateX: 250});`|
| DOM Node / NodeList | Can be any DOM Node or NodeList. Can use `querySelector` and `querySelectorAll` to select DOM element |  `var elements = document.querySelectorAll('.dom-node-demo .el'); anime({ targets: elements, translateX: 270 });`|
| JavaScript Object | A JavaScript Object with at least one property containing a numerical value. | `var logEl = document.querySelector('.battery-log'); var battery = { charged: '0%', cycles: 120 } anime({ targets: battery, charged: '100%', cycles: 130, round: 1, easing: 'linear', update: function(){logEl.innerHTML = JSON.stringify(battery);}});` |
| Array | An array containing multiple targets, mixed types are accepted. e.g. ['.el', domNode, jsObject] | `var el = document.querySelector('.mixed-array-demo .el-01'); anime({ targets: [el, '.mixed-array-demo .el-02', '.mixed-array-demo .el-03'], translateX: 250 });`


Please note, these are just examples, you may use other animation properties, values or events based on your requirement.


    CSS Selector

    CSS Selector: allows you to select elements using a CSS selector. In this way you can target multiple elements on the page at once and also you can't target Pseudo elements using javascript.


Can be any CSS selector.

Pseudo elements can't be targeted using JavaScript.
Type 	Default 	Example
String 	null 	targets: '.item'
Code example
```
anime({
  targets: '.css-selector-demo .el',
  translateX: 250
});

```
    DOM Node / NodeList
  DOM Node / NodeList: allows you to select DOM nodes or a NodeList, you can use the querySelector and querySelectorAll to select DOM element.

Can be any DOM Node or NodeList.
Type 	Default 	Example
DOM Node 	null 	targets: el.querySelector('.item')
NodeList 	null 	targets: el.querySelectorAll('.item')
Code example
```
var elements = document.querySelectorAll('.dom-node-demo .el');

anime({
  targets: elements,
  translateX: 270
});
```

    JavaScript Object

    JavaScript Object: you can animate properties of a JavaScript Object. The object needs to have at least one property with numerical value.

A JavaScript Object with at least one property containing a numerical value.
Type 	Default 	Example
Object 	null 	targets: myObjectProp
Code example

var logEl = document.querySelector('.battery-log');

var battery = {
  charged: '0%',
  cycles: 120
}

anime({
  targets: battery,
  charged: '100%',
  cycles: 130,
  round: 1,
  easing: 'linear',
  update: function() {
    logEl.innerHTML = JSON.stringify(battery);
  }
});


    Array
  

    Array: you can use an array of mixed types (CSS selector, DOM node, JavaScript object) to target multiple elements and animate them at once.

An array containing multiple targets.

Accepts mixed types. E.g. ['.el', domNode, jsObject]
Type 	Default 	Example
Array 	null 	targets: ['.item', el.getElementById('#thing')]
Code example
```
var el = document.querySelector('.mixed-array-demo .el-01');

anime({
  targets: [el, '.mixed-array-demo .el-02', '.mixed-array-demo .el-03'],
  translateX: 250
});

```

```These different options for targeting elements give developers flexibility and control over which elements to animate and how to animate them.```


    Properties covers different way to animate DOM, CSS, SVG, Object properties and attributes

The "Properties" section of the Anime.js documentation explains the different ways to animate elements, including CSS, CSS Transforms, Object properties, DOM attributes, and SVG attributes.

| Property type       | Description                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------|
| CSS Properties      | Any CSS properties can be animated. Prioritize opacity and CSS transforms to prevent choppy animation. |
| CSS Transforms      | Animate CSS transform properties individually. Specify different timing for each transform property. |
| Object Properties   | Any Object property containing a numerical value can be animated. |
| DOM Attributes      | Any DOM attributes containing a numerical value can be animated.  |
| SVG Attributes      | All SVG attributes containing at least one numerical value can be animated. |

  
CSS Properties
  CSS Properties: Allows you to animate any css properties and need to be careful because this can cause layout change and repaint. Prioritizing opacity and CSS transforms can prevent choppy animation.

 
Any CSS properties can be animated.

Most CSS properties will cause layout changes or repaint, and will result in choppy animation. Prioritize opacity and CSS transforms as much as possible.

More details about accepted values in the values section.
Example 	value
opacity 	.5
left 	'100px'
Code example
```
anime({
  targets: '.css-prop-demo .el',
  left: '240px',
  backgroundColor: '#FFF',
  borderRadius: ['0%', '50%'],
  easing: 'easeInOutQuad'
});
```


CSS Transforms
   CSS Transforms: allows you to animate transform properties individually. it is possible to specify different timing for each transform property.


Animate CSS transforms properties individually.

It's possible to specify different timing for each transforms properties, more details in the specific property parameters section.

More details about accepted values in the values section.
Valid properties 	Default unit
'translateX'	'px'
'translateY'	'px'
'translateZ'	'px'
'rotate'	'deg'
'rotateX'	'deg'
'rotateY'	'deg'
'rotateZ'	'deg'
'scale'	—
'scaleX'	—
'scaleY'	—
'scaleZ'	—
'skew'	'deg'
'skewX'	'deg'
'skewY'	'deg'
'perspective'	'px'
Code example
```
anime({
  targets: '.css-transforms-demo .el',
  translateX: 250,
  scale: 2,
  rotate: '1turn'
});

```

Object properties
    Object properties: Any object property containing a numerical value can be animated.

  
Any Object property containing a numerical value can be animated.
More details about accepted values in the values section.
Example 	value
prop1 	50
'prop2' 	'100%'
Code example
```
var objPropLogEl = document.querySelector('.js-object-log');

var myObject = {
  prop1: 0,
  prop2: '0%'
}

anime({
  targets: myObject,
  prop1: 50,
  prop2: '100%',
  easing: 'linear',
  round: 1,
  update: function() {
    objPropLogEl.innerHTML = JSON.stringify(myObject);
  }
});
```

DOM Attributes
  DOM attributes: Any DOM attributes containing a numerical value can be animated.


Any DOM Attributes containing a numerical value can be animated.
More details about accepted values in the values section.
Example 	value
value 	1000
volume 	0
data-custom 	'3 dogs'
Code example
```
anime({
  targets: '.dom-attribute-demo input',
  value: [0, 1000],
  round: 1,
  easing: 'easeInOutExpo'
});
```


SVG Attributes
    SVG Attributes: SVG attributes containing at least one numerical value can be animated


Like any other DOM attributes, all SVG attributes containing at least one numerical value can be animated.
More details about accepted values in the values section and SVG animation in the SVG section.
Example 	value
points 	'64 68.64 8.574 100 63.446 67.68 64 4 64.554 67.68 119.426 100'
scale 	1
baseFrequency 	0
Code example
```
anime({
  targets: ['.svg-attributes-demo polygon', 'feTurbulence', 'feDisplacementMap'],
  points: '64 128 8.574 96 8.574 32 64 0 119.426 32 119.426 96',
  baseFrequency: 0,
  scale: 1,
  loop: true,
  direction: 'alternate',
  easing: 'easeInOutExpo'
});
```

Each of these animation types provides developers with different options for creating animations, giving them flexibility and control over the animation. Additionally, the More details about accepted values in the values section section of the documentation provides further details on the types of values that can be used to animate elements.


    Property parameters covers the way you could control the animation like Duration, Easing and Round etc.

    Animation parameters: provides details on how to control various aspects of the animation, such as the loop and autoplay settings.

    Values: covers how to define the values used in animations, including different units and functions

    Keyframes: explains how to create animations using keyframes

    Staggering: covers how to create stagger effect on animations

    Timeline: explains how to create and control timeline animations

    Controls: covers how to control the animations like Play/Pause, reverse, seek etc

    Callbacks & Promises: explains how to use callbacks and promises to execute code at certain points during an animation.

    SVG: provides information on how to use the library to animate SVG elements.

    Easings: covers the different easing functions available in the library and how to create custom easing functions

    Helpers: provides information on some useful helper functions like remove, get, set and random etc.

The documentation tree is like this:     

    Targets
    CSS Selector
    DOM Node / NodeList
    JavaScript Object
    Array
    
    Properties
    CSS Properties
    CSS Transforms
    Object properties
    DOM Attributes
    SVG Attributes
    
    Property parameters
    Duration
    Delay
    end delay
    Easing
    Round
    Specific property parameters
    Function based parameters
    
    Animation parameters
    Direction
    Loop
    Autoplay
    
    Values
    Unitless
    Specific unit
    Relative
    Colors
    From To
    Function based values
    
    Keyframes
    Animation keyframes
    Property keyframes
    
    Staggering
    Staggering basics
    Start value
    Range value
    From value
    Direction
    Easing
    Grid
    Axis
    
    Staggering
    Staggering basics
    Start value
    Range value
    From value
    Direction
    Easing
    Grid
    Axis

    Timeline
    Timeline basics
    Time Offsets
    Parameters inheritance
    
    Controls
    Play / Pause
    Restart
    Reverse
    Seek
    Timeline controls
    
    Callbacks & Promises
    Update
    Begin & Complete
    loopBegin & loopComplete
    Change
    changeBegin & changeComplete
    Finished promise
    
    SVG
    Motion path
    Morphing
    Line drawing
    
    Easings
    Linear
    Penner's functions
    Cubic Bézier Curve
    Spring
    Elastic
    Steps
    Custom easing function
    
    
    Helpers
    remove
    get
    set
    random
    tick
    running
    Suspend on visibility change
