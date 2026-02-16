### EaselJS Setup and GSAP Animation Examples

Source: https://gsap.com/docs/v3/Plugins/EaselPlugin

Provides a comprehensive example of setting up an EaselJS stage and animating a circle with GSAP. It covers drawing, caching, positioning, and tweening various properties including tint, scale, position, rotation, and saturation.

```javascript
//setup stage and create a Shape into which we'll draw a circle later...
var canvas = document.getElementById("myCanvas"),
  stage = new createjs.Stage(canvas),
  circle = new createjs.Shape(),
  g = circle.graphics;

//draw a red circle in the Shape
g.beginFill(createjs.Graphics.getRGB(255, 0, 0));
g.drawCircle(0, 0, 100);
g.endFill();

//in order for the ColorFilter to work, we must cache() the circle
circle.cache(-100, -100, 200, 200);

//place the circle at 200,200
circle.x = 200;
circle.y = 200;

//add the circle to the stage
stage.addChild(circle);

//setup a "tick" event listener so that the EaselJS stage gets updated on every frame/tick
gsap.ticker.add(() => stage.update());
stage.update();

//tween the tint of the circle to green and scale it to half-size
gsap.to(circle, {
  duration: 2,
  scaleX: 0.5,
  scaleY: 0.5,
  easel: { tint: 0x00ff00 },
});

//tween to a different tint that is only 50% (mixing with half of the original color) and animate the scale, position, and rotation simultaneously.
gsap.to(circle, {
  duration: 3,
  scaleX: 1.5,
  scaleY: 0.8,
  x: 250,
  y: 150,
  rotation: 180,
  easel: { tint: "#0000FF", tintAmount: 0.5 },
  delay: 3,
  ease: "elastic",
});

//then animate the saturation down to 0
gsap.to(circle, { duration: 2, easel: { saturation: 0 }, delay: 6 });
```

--------------------------------

### Configure MotionPathHelper with Options

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

This example shows how to create a MotionPathHelper instance with a configuration object, allowing customization of path properties like width, color, opacity, and animation parameters such as start, end, duration, and ease.

```javascript
MotionPathHelper.create("#elementID", {
  path: "#path",
  pathWidth: 5,
  pathColor: "red",
  pathOpacity: 0.6,
  selected: true,
  start: 0.1,
  end: 1,
  duration: 5,
  ease: "power2.inOut",
});
```

--------------------------------

### GSAP Basic Tween Example

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/bgSize

A basic GSAP tween demonstration, likely used to illustrate animation principles or as a starting point for more complex animations. This example is embedded from CodePen and requires no specific setup beyond including GSAP.

```html
<iframe src="https://codepen.io/GreenSock/embed/89bd92e9114108e96874df09a424e8aa?default-tab=result&theme-id=41164" style="width:100%; height: 300px; border: none;"></iframe>
```

--------------------------------

### Set Custom Start Position on Motion Path

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example shows how to specify a custom starting point along the motion path using the `start` property. A value of `0.3` means the animation will begin at 30% of the path's length.

```javascript
start: 0.3
```

--------------------------------

### Import GSAP from a Module File

Source: https://gsap.com/docs/v3/Installation

Imports GSAP and registered plugins from a custom module file. This allows for cleaner imports in other parts of your project.

```javascript
import { gsap, DrawSVGPlugin } from "../gsap.js";
```

--------------------------------

### Register GSAP TextPlugin

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

This code snippet shows how to register the TextPlugin with GSAP, which is necessary before using its text animation capabilities. Ensure this line is included in your project setup.

```javascript
gsap.registerPlugin(TextPlugin)
```

--------------------------------

### GSAP Basic Tween Example

Source: https://gsap.com/docs/v3/Plugins/Flip

A basic example demonstrating a GSAP tween animation. This snippet is useful for understanding fundamental GSAP animation principles.

```html
<!DOCTYPE html>
<html>
<head>
<title>GSAP Basic Tween</title>
<style>
.box {
  width: 100px;
  height: 100px;
  background-color: blue;
}
</style>
</head>
<body>

<div class="box"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.5/gsap.min.js"></script>
<script>
// GSAP animation code would go here
gsap.to(".box", { duration: 2, x: 300, rotation: 360, ease: "power2.inOut" });
</script>

</body>
</html>
```

--------------------------------

### GSAP SlowMo Ease Examples

Source: https://gsap.com/docs/v3/Eases/SlowMo

Provides examples of using the SlowMo ease in GSAP. The first shows default usage, the second demonstrates custom `linearRatio` and `power` values, and the third illustrates using `yoyoMode` for syncing tweens.

```javascript
//use the default SlowMo ease (linearRatio of 0.7 and power of 0.7)
gsap.to(myText, {duration: 5, x: 600, ease: "slow"});
```

```javascript
//this gives the exact same effect as the line above, but uses a different syntax
gsap.to(myText, {duration: 5, x: 600, ease: "slow(0.5, 0.8)"});
```

```javascript
//now let's create an opacity tween that syncs with the above positional tween, fading it in at the beginning and out at the end
gsap.from(myText, {duration: 5, opacity: 0, ease: "slow(0.5, 0.8, true)"});
```

--------------------------------

### Create a GSAP Module File

Source: https://gsap.com/docs/v3/Installation

Creates a centralized module file to export GSAP core and specific plugins. This approach helps avoid duplicate plugin registrations in module environments.

```javascript
export * from "gsap";
export * from "gsap/DrawSVGPlugin";

import { gsap } from "gsap";
import { DrawSVGPlugin } from "gsap/DrawSVGPlugin";

gsap.registerPlugin(DrawSVGPlugin);
```

--------------------------------

### startTime()

Source: https://gsap.com/docs/v3/GSAP/Tween

Gets or sets the time at which the animation begins on its parent timeline. This allows for precise control over the animation's start time.

```APIDOC
## POST /docs/v3/GSAP/Tween/startTime().md

### Description
Gets or sets the time at which the animation begins.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/startTime().md

### Parameters
#### Path Parameters
- **value** (Number) - Required - The start time.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Number | self** (Number | self) - Returns the start time or self.

#### Response Example
N/A
```

--------------------------------

### Get and Set Animation Start Time (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/startTime%28%29

Demonstrates how to get the current start time of an animation and how to set a new start time using the startTime() method in GSAP. This method is part of the GSAP animation library.

```javascript
//gets current start time
var start = tl.startTime();

//sets
tl.startTime(2);
```

--------------------------------

### Register GSAP Plugins

Source: https://gsap.com/docs/v3/Installation

Registers multiple GSAP plugins at once. This is recommended to ensure plugins are not removed by tree-shaking in build tools and to make them available for use.

```javascript
gsap.registerPlugin(MotionPathPlugin, ScrollToPlugin, TextPlugin);
```

--------------------------------

### Get and Set Animation startTime in GSAP

Source: https://gsap.com/docs/v3/GSAP/Tween/startTime%28%29

This snippet demonstrates how to use the startTime method in GSAP v3. It shows how to retrieve the current start time of an animation and how to set a new start time, returning the animation instance for chaining.

```javascript
//gets current start time
var start = myAnimation.startTime();

//sets the start time
myAnimation.startTime(2);
```

--------------------------------

### Demonstrating revert() vs. progress(0) (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/revert%28%29

This example illustrates the difference between `progress(0)` and `revert()`. While `progress(0)` resets the animation to its start, it may leave inline styles. `revert()` not only resets but also removes these inline styles.

```javascript
let tween = gsap.to(".box", { opacity: 0 });

// Using progress(0) might leave inline styles
tween.progress(0).pause();
// <div class="box" style="opacity: 1"></div>

// Using revert() removes inline styles added by the animation
tween.revert();
// <div class="box"></div> (inline styles removed)
```

--------------------------------

### Minimal PhysicsPropsPlugin Usage Example

Source: https://gsap.com/docs/v3/Plugins/PhysicsPropsPlugin

Demonstrates the basic usage of PhysicsPropsPlugin to animate the 'x' and 'y' properties of an object. It uses velocity and acceleration for 'x', and velocity and friction for 'y'. The duration of the tween is set to 2 seconds.

```javascript
gsap.to(obj, {
  duration: 2,
  physicsProps: {
    x: { velocity: 100, acceleration: 200 },
    y: { velocity: -200, friction: 0.1 },
  },
});
```

--------------------------------

### Import GSAP Core

Source: https://gsap.com/docs/v3/Installation

Imports the core GSAP library. This is the first step to using GSAP's animation capabilities in your JavaScript code.

```javascript
import { gsap } from "gsap";
```

--------------------------------

### GSAP v3 Immediate Render and Overwrite Example

Source: https://gsap.com/docs/v3/GSAP/gsap

Shows the usage of 'immediateRender' to force immediate rendering and 'overwrite' to manage conflicting tweens.

```javascript
gsap.from(".myElement", {
  opacity: 0,
  immediateRender: true, // Renders immediately on instantiation
  overwrite: "auto"      // Automatically handles conflicting tweens
});
```

--------------------------------

### Create a tween with advanced properties and parameters

Source: https://gsap.com/docs/v3/GSAP/Timeline/tweenFromTo%28%29

This example shows how to use tweenFromTo with a vars object to control advanced properties like onComplete, ease, and parameters. It tweens from the start (0) to a 5-second mark and calls a function upon completion.

```javascript
tl.tweenFromTo(0, 5, {
  onComplete: myFunction,
  onCompleteParams: [tl],
  ease: "strong",
});
```

--------------------------------

### SplitText Configuration Options

Source: https://gsap.com/docs/v3/Plugins/SplitText

Demonstrates how to configure SplitText during creation. This example shows splitting only into words and lines, applying a mask to lines, and adding custom class names with auto-incrementing numbers to the line elements.

```javascript
let split = SplitText.create(".split", {
  type: "words, lines", // only split into words and lines (not characters)
  mask: "lines", // adds extra wrapper element around lines with overflow: clip (v3.13.0+)
  linesClass: "line++", // adds "line" class to each line element, plus an incremented one too ("line1", "line2", "line3", etc.)

  // there are many other options - see below for a complete list
});
```

--------------------------------

### Advanced GSAP Observer Configuration

Source: https://gsap.com/docs/v3/Plugins/Observer

An example showcasing more advanced configuration options for the Observer plugin. It listens to multiple event types ('wheel', 'touch', 'scroll', 'pointer') and defines callbacks for 'onUp' and 'onDown' actions, similar to the minimal example but with explicit event types.

```javascript
Observer.create({
  target: window, // can be any element (selector text is fine)
  type: "wheel,touch,scroll,pointer", // comma-delimited list of what to listen for
  onUp: () => previous(),
  onDown: () => next()
});
```

--------------------------------

### Advanced Text Animation Configuration

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Illustrates advanced TextPlugin configuration using an object for the 'text' property. This includes setting the target value, delimiter, and CSS classes for a more controlled animation.

```javascript
//GOOD:
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Your new text",
    newClass: "class2",
    delimiter: " ",
  },
});
```

--------------------------------

### GSAP v3 Animation Configuration Example

Source: https://gsap.com/docs/v3/GSAP/gsap

Demonstrates how to use special properties like 'duration', 'ease', and 'onComplete' within a GSAP animation configuration object.

```javascript
gsap.to(".myElement", {
  x: 100,
  duration: 1,
  ease: "power1.inOut",
  onComplete: function() {
    console.log("Animation Complete!");
  },
  onCompleteParams: ["Animation Complete!"]
});
```

--------------------------------

### JavaScript Usage Example for Image Sequence Scrubber

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/imageSequenceScrub

Example demonstrating how to use the `imageSequence` helper function. It shows the required parameters: an array of image URLs (`urls`), a selector for the canvas element (`canvas`), and a ScrollTrigger configuration object. The `scrub: true` property is crucial for the scrolling effect.

```javascript
imageSequence({
  urls, // Array of image URLs
  canvas: "#image-sequence", // <canvas> object to draw images to
  scrollTrigger: {
    start: 0,   // start at the very top
    end: "max", // entire page
    scrub: true // important!
  }
});
```

--------------------------------

### Relative Start Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Position an animation at the start of the previously inserted animation using the '<' character. This is useful for sequencing animations back-to-back.

```javascript
tl.from(".class", { x: 100 }, "<");
```

--------------------------------

### Usage Example for Progressive Timeline Build (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/progressiveBuild

Demonstrates how to use the `progressiveBuild` helper function. It shows passing multiple functions and a numerical delay value to create a sequenced animation with a 1.5-second pause between `step2` and `step3`.

```javascript
progressiveBuild(
  step1,
  step2,
  1.5, // 1.5-second delay (sprinkle between any two functions)
  step3
);
```

--------------------------------

### Standalone GSAP ScrollTrigger Custom Example

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Demonstrates creating a ScrollTrigger instance independently of an animation. This example uses callbacks like onToggle and onUpdate to react to scroll events, logging progress, direction, and velocity.

```javascript
ScrollTrigger.create({
	trigger: '#id',
	start: 'top top',
	endTrigger: '#otherID',
	end: 'bottom 50%+=100px',
	onToggle: (self) => console.log('toggled, isActive:', self.isActive),
	onUpdate: (self) => {
		console.log(
			'progress:',
			self.progress.toFixed(3),
			'direction:',
			self.direction,
			'velocity',
			self.getVelocity()
		);
	}
});
```

--------------------------------

### Minimal GSAP Physics2D Tween Example

Source: https://gsap.com/docs/v3/Plugins/Physics2DPlugin

A basic example of using the Physics2DPlugin to animate an element's position. It applies a velocity and angle to simulate a projectile motion.

```javascript
gsap.to(element, {
  duration: 2,
  physics2D: { velocity: 300, angle: -60, gravity: 400 },
});
```

--------------------------------

### GSAP Timeline to() Method Example

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Demonstrates the basic usage of the gsap.timeline().to() method as a shorthand for gsap.timeline().add(gsap.to()). This example shows creating a timeline and adding a tween to it.

```javascript
var tl = gsap.timeline();

var tween = gsap.to(element, { duration: 1, x: 100, opacity: 0.5 });
tl.add(tween);

//this line produces the same result as the previous two lines (just shorter)
tl.to(element, { duration: 1, x: 100, opacity: 0.5 });
```

--------------------------------

### GSAP v3 getChildren Example

Source: https://gsap.com/docs/v3/GSAP/Timeline/getChildren%28%29

Demonstrates how to use the getChildren method in GSAP v3 to retrieve child tweens and timelines from a master timeline. It shows how to filter results based on nesting, type (tweens/timelines), and start time.

```javascript
var master = gsap.timeline({ defaults: { duration: 1 } }),
  nested = gsap.timeline();

nested.to("#e1", { duration: 1, x: 100 }).to("#e2", { duration: 2, y: 200 });

master
  .to("#e3", { top: 200 })
  .to("#e4", { left: 100 })
  .to("#e5", { backgroundColor: "red" });

master.add(nested);

var children = master.getChildren(false, true, true);

console.log(children.length); //"3" (2 tweens and 1 timeline)

children = master.getChildren(true, true, true, 0.5);

console.log(children.length); //"5" (4 tweens and 1 timeline)

children = master.getChildren(true, true, false);

console.log(children.length); //"5" (5 tweens)
```

--------------------------------

### Text Animation with Speed Adjustment

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Demonstrates how to use the 'speed' property to automatically adjust the animation duration based on the number of text changes. A higher speed value results in a faster animation.

```javascript
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Your new text",
    speed: 10 // Adjust speed here
  }
});
```

--------------------------------

### Minimal Flip Animation Example

Source: https://gsap.com/docs/v3/Plugins/Flip

Demonstrates the basic workflow of the GSAP Flip plugin. It involves capturing the initial state of elements, making DOM or style changes, and then animating the elements from their captured state to their new state.

```javascript
// grab state
const state = Flip.getState(squares);
  
// Make DOM or styling changes
switchItUp();
  
// Animate from the initial state to the end state
Flip.from(state, {duration: 2, ease: "power1.inOut"});
```

--------------------------------

### Get Previous ScrollTrigger Instance - JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/previous%28%29

The .previous() method returns the ScrollTrigger instance that was processed before the current one during the refresh cycle. This is particularly helpful for setting the start or end points of a ScrollTrigger based on the position of a previous one, as demonstrated in the example where the current trigger starts at the end of the previous trigger.

```javascript
ScrollTrigger.create({
  start: self => self.previous().end, // start at the end of the previous ScrollTrigger
  ...
});
```

--------------------------------

### GSAP v3 Timeline Chaining with fromTo, to, set, and call

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Illustrates chaining multiple GSAP timeline methods, including `fromTo`, `to`, `set`, and `call`, to create complex animation sequences. This example shows how to animate properties, execute functions, and apply stagger effects.

```javascript
//create a timeline that calls myFunction() when it completes
var tl = gsap.timeline({ onComplete: myFunction });

//now we'll use chaining, but break each step onto a different line for readability...

//tween element's x from -100 to 100
tl.fromTo(element, { x: -100 }, { duration: 1, x: 100 })

  //then tween element's y to 50
  .to(element, { duration: 1, y: 50 })

  //then set element's opacity to 0.5 immediately
  .set(element, { opacity: 0 })

  //then call otherFunction()
  .call(otherFunction)

  //finally tween the rotation of all elements with the class "myClass" to 45 and stagger the start times by 0.25 seconds
  .to(".myClass", { duration: 1.5, rotation: 45, stagger: 0.25 });
```

--------------------------------

### Basic RoughEase Animation (Default Configuration)

Source: https://gsap.com/docs/v3/Eases/RoughEase

This example shows the most basic way to apply the RoughEase effect to an animation using its default configuration. It's suitable for quick, rough effects without custom parameters.

```javascript
//use the default values
gsap.from(element, {duration: 1, opacity: 0, ease: "rough"});
```

--------------------------------

### Configure TypeScript Definitions

Source: https://gsap.com/docs/v3/Installation

Configures the TypeScript compiler to locate GSAP's official type definitions. This helps resolve TypeScript errors related to GSAP usage.

```json
{
  "compilerOptions": {
    ...
  },
  "files": [
    "node_modules/gsap/types/index.d.ts"
  ]
}
```

--------------------------------

### Install GSAP v3 with npm

Source: https://gsap.com/docs/v3/GSAP

Installs the GSAP v3 library using the npm package manager. This is the recommended way to include GSAP in your project for easy dependency management.

```bash
npm install gsap
```

--------------------------------

### GSAP Timeline Initialization with Callbacks (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Demonstrates how to initialize a GSAP v3 timeline with various callback functions and their associated parameters. This allows for custom actions to be executed at specific points during the animation's lifecycle, such as on start, completion, or repeat.

```javascript
const myTimeline = gsap.timeline({
  onStart: myStartFunction,
  onStartParams: ["param1", "param2"],
  onComplete: myCompleteFunction,
  onCompleteParams: ["paramA", "paramB"],
  onUpdate: myUpdateFunction,
  onUpdateParams: [1, 2],
  onRepeat: myRepeatFunction,
  onRepeatParams: ["repeat1"],
  onReverseComplete: myReverseCompleteFunction,
  onReverseCompleteParams: ["reverse"],
  onInterrupt: myInterruptFunction,
  onInterruptParams: ["interrupted"]
});
```

--------------------------------

### Get ScrollSmoother Velocity on Button Click (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/getVelocity%28%29

This example shows how to obtain the scroll velocity using .getVelocity() when an event, like a button click, occurs. It first creates a ScrollSmoother instance and then accesses its velocity when the button is clicked.

```javascript
let smoother = ScrollSmoother.create({...});

button.addEventListener("click", () => {
  console.log("velocity:", smoother.getVelocity());
});
```

--------------------------------

### Minimal GSAP ScrollTrigger Animation

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

A basic example of using ScrollTrigger to animate an element. The animation starts when the '.box' element enters the viewport, and the element moves 500 pixels horizontally.

```javascript
gsap.to('.box', {
	scrollTrigger: '.box',
	x: 500
});
```

--------------------------------

### Get and Set Animation Delay in GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Timeline/delay%28%29

Demonstrates how to retrieve the current delay of a GSAP animation and how to set a new delay value. This method is crucial for controlling when animations start and supports chaining for concise code.

```javascript
//gets current delay
var currentDelay = myAnimation.delay();

//sets delay
myAnimation.delay(2);
```

--------------------------------

### Configure Inertia Plugin with Live Snap Points

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example shows how to use 'liveSnap' with a 'points' array and a radius to snap the Draggable element to predefined coordinates within a specified proximity. It allows for snapping to specific points on the screen.

```javascript
Draggable.create(element, {
  inertia: true,
  liveSnap: {
    points: [{x: 0, y: 0}, {x: 100, y: 0}],
    radius: 20
  }
});
```

--------------------------------

### Register PhysicsPropsPlugin with GSAP

Source: https://gsap.com/docs/v3/Plugins/PhysicsPropsPlugin

This code snippet shows how to register the PhysicsPropsPlugin with GSAP, which is necessary before using its physics-based tweening capabilities. It requires the GSAP library to be loaded.

```javascript
gsap.registerPlugin(PhysicsPropsPlugin)
```

--------------------------------

### Define Motion Path using Array of Coordinates (Curved)

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example shows how to define a motion path using an array of objects, each with 'x' and 'y' coordinates. GSAP will plot a curve through these points, automatically including the target's starting coordinates.

```javascript
motionPath: {
  path: [{x:100, y:50}, {x:200, y:0}, {x:300, y:100}]
}
```

--------------------------------

### Import Non-ES Module GSAP

Source: https://gsap.com/docs/v3/Installation

Imports the UMD (Universal Module Definition) version of GSAP using a build tool. This is useful for environments or build tools that do not fully support ES modules.

```javascript
import { gsap } from "gsap/dist/gsap";
```

--------------------------------

### Basic PixiJS Animation with GSAP

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

Demonstrates a minimal example of animating a PixiJS object's line color using GSAP and PixiPlugin. This highlights the simplified syntax for animating PixiJS properties.

```javascript
gsap.to(graphics, { duration: 2, pixi: { lineColor: "purple" } });
```

--------------------------------

### GSAP v3 Data and ID Example

Source: https://gsap.com/docs/v3/GSAP/gsap

Demonstrates attaching custom data to a tween instance using the 'data' property and assigning an ID for later retrieval.

```javascript
const myTween = gsap.to(".myElement", {
  scale: 1.5,
  data: { userId: 123, status: "active" },
  id: "scaleTween"
});

console.log(myTween.data.userId); // Output: 123
const retrievedTween = gsap.getById("scaleTween");
console.log(retrievedTween === myTween); // Output: true
```

--------------------------------

### Immediate Render Override in GSAP fromTo()

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Demonstrates how to disable the default immediate rendering of the starting state in a `fromTo()` tween. By setting `immediateRender: false`, the tween will wait until its scheduled start time to render.

```javascript
tl.fromTo(".class", { x: 100 }, { x: 200 }, { immediateRender: false, delay: 1 });
```

--------------------------------

### Text Animation with CSS Classes

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Applies CSS classes to the old and new text during animation using 'oldClass' and 'newClass' properties. This allows for distinct styling of text before and after the animation.

```javascript
//wraps the old text in <span class="class1"> and the new text in a <span class="class2">
gsap.to("#element", {
    duration: 2,
    text: {
        value: "This is the new text",
        newClass: "class2",
        oldClass: "class1"
    },
    ease: "power2"
});
```

--------------------------------

### Right-to-Left Text Animation

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Configures TextPlugin to animate text introduction from right to left by setting the 'rtl' property to true. This reverses the order of character appearance.

```javascript
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Your new text",
    rtl: true
  }
});
```

--------------------------------

### Example Usage of Debounced Resize Function (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/callAfterResize

Demonstrates how to use the `callAfterResize` function by passing a custom function, `myFunction`, as the callback. This example assumes `myFunction` is defined elsewhere and will be executed after the resize event has stopped.

```javascript
callAfterResize(myFunction);
```

--------------------------------

### Example Usage of GSAP Number Formatting Utilities (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/formatNumber

Demonstrates how to use the `formatNumber` and `getFormatter` functions within GSAP animations. The first example shows updating an element's text with a formatted number during a tween, while the second shows creating and using a custom formatter for incremental display.

```javascript
let obj = { num: 100 };
gsap.to(obj, {
  num: 10500,
  onUpdate: () => (myElement.innerText = "$" + formatNumber(obj.num, 2)),
});
```

```javascript
let formatter = getFormatter(0.01, true); // increment by 0.01, always pad so that there are 2 decimal places

console.log(formatter(5000.1)); // 5,000.10
```

--------------------------------

### Showcase & Demos

Source: https://gsap.com/docs/v3/Plugins/Observer

Provides a link to a CodePen collection showcasing the Observer plugin's capabilities and demonstrating its usage.

```APIDOC
## Showcase & How-to Demos

### Description
This section provides a direct link to a curated collection of demos and examples demonstrating the functionality and practical applications of the GSAP Observer plugin.

### Method
N/A (External Link)

### Endpoint
N/A (External Link)

### Parameters
N/A

### Request Example
N/A

### Response
#### Success Response (N/A)
N/A

#### Response Example
N/A

### External Resources
- **Observer showcase:** [https://codepen.io/collection/KpNYOd/b1f3f64ef53f0b3dc1c7d5fb6203ebc7](https://codepen.io/collection/KpNYOd/b1f3f64ef53f0b3dc1c7d5fb6203ebc7)
```

--------------------------------

### Advanced GSAP ScrollTrigger with Timeline

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This snippet shows an advanced ScrollTrigger setup using a GSAP timeline. It pins the trigger element, defines start and end points, enables smooth scrubbing, and includes snapping functionality with labels.

```javascript
let tl = gsap.timeline({
	scrollTrigger: {
		trigger: '.container',
		pin: true,
		start: 'top top',
		end: '+=500',
		scrub: 1,
		snap: {
			snapTo: 'labels',
			duration: { min: 0.2, max: 3 },
			delay: 0.2,
			ease: 'power1.inOut'
		}
	}
});

tl.addLabel('start')
	.from('.box p', { scale: 0.3, rotation: 45, autoAlpha: 0 })
	.addLabel('color')
	.from('.box', { backgroundColor: '#28a92b' })
	.addLabel('spin')
	.to('.box', { rotation: 360 })
	.addLabel('end');
```

--------------------------------

### GSAP MotionPath Tween Example

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

A basic GSAP tween demonstrating the use of the MotionPathPlugin to animate an element along a specified path. It includes options for path alignment and auto-rotation.

```javascript
gsap.to("#div", {
  motionPath: {
    path: "#path",
    align: "#path",
    alignOrigin: [0.5, 0.5],
    autoRotate: true,
  },
  transformOrigin: "50% 50%",
  duration: 5,
  ease: "power1.inOut",
});
```

--------------------------------

### GSAP v3 seek() Method Examples

Source: https://gsap.com/docs/v3/GSAP/Timeline/seek%28%29

Demonstrates how to use the seek() method in GSAP v3 to jump to different positions on a timeline. It covers seeking to an absolute time, seeking while suppressing events, and seeking to a named label.

```javascript
tl.seek(2);

tl.seek(2, false);

tl.seek("myLabel");
```

--------------------------------

### Relative Start Positioning ('<') in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Positions an animation at the start of the previously inserted animation. The '<' character acts as a pointer to the beginning of the preceding tween.

```javascript
tl.to(".class", { x: 100 }, "<");
```

--------------------------------

### GSAP v3: Define Initial State with startAt

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

The `startAt` property allows you to define initial values for any property, even those not directly involved in the animation. This is useful for setting up a specific visual state before the tween begins its primary animation. For example, setting initial `x` and `opacity` values.

```javascript
gsap.to("#myElement", {
  x: 100,
  opacity: 1,
  startAt: {
    x: -100,
    opacity: 0
  }
});
```

--------------------------------

### Get Scroll Velocity with GSAP ScrollTrigger

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/getVelocity%28%29

This example demonstrates how to use the .getVelocity() method within a ScrollTrigger's onUpdate callback. It logs the scroll velocity to the console whenever the scroll position changes. No external dependencies are required beyond GSAP and its ScrollTrigger plugin.

```javascript
ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
  onUpdate: (self) => console.log("velocity:", self.getVelocity()),
});
```

--------------------------------

### Relative Positioning to Previous Animation Start in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Places an animation at the start of the previously inserted animation using the '<' character. This is useful for sequencing animations back-to-back.

```javascript
tl.fromTo(".class", { x: 100 }, { x: 200 }, "<");
```

--------------------------------

### Configure Inertia Plugin with Snap Object for X and Y

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example illustrates configuring the InertiaPlugin with an object to apply different snapping logic to the 'x' and 'y' properties independently. This allows for distinct snapping rules based on the axis of movement.

```javascript
Draggable.create(element, {
  type: "x,y",
  inertia: true,
  snap: {
    x: [5, 20, 80, 400],
    y: [10, 60, 80, 500]
  }
});
```

--------------------------------

### GSAP v3 Timeline from() Example

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Demonstrates how to use the gsap.from() method to add a tween to a timeline. This is a shorthand for creating a tween and then adding it to the timeline.

```javascript
var tl = gsap.timeline();

var tween = gsap.from(element, { duration: 1, x: 100, opacity: 0.5 });
tl.add(tween);

//this line produces the same result as the previous two lines (just shorter)
tl.from(element, { duration: 1, x: 100, opacity: 0.5 });
```

--------------------------------

### Relative Start Positioning in GSAP v3 Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

Inserts a function call at the start of the previously inserted animation. The '<' character acts as a pointer to the beginning of the preceding animation.

```javascript
tl.call(myFunction, null, "<");
```

--------------------------------

### GSAP v3 Timeline fromTo Method Example

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Demonstrates how to use the `fromTo` method to add a tween to a GSAP timeline. This method is a shorthand for `timeline.add(gsap.fromTo(...))` and simplifies timeline creation.

```javascript
var tl = gsap.timeline();

var tween = gsap.fromTo(element, { x: -100 }, { duration: 1, x: 100 });
tl.add(tween);

//this line produces the same result as the previous two lines (just shorter)
tl.fromTo(element, { x: -100 }, { duration: 1, x: 100 });
```

--------------------------------

### Basic SplitText Instance Creation

Source: https://gsap.com/docs/v3/Plugins/SplitText

Illustrates how to create a SplitText instance by providing a selector, element, or an array of elements. The resulting instance provides access to arrays of split characters, words, and lines.

```javascript
// the target can be selector text, an element, or an Array of elements
let split = SplitText.create(".headline");

// Array of characters
split.chars

// Array of words
split.words

// Array of lines
split.lines
```

--------------------------------

### GSAP v3: Stagger Animation Start Times

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

When animating multiple targets, the `stagger` property allows you to offset the start times of each animation. A simple value like `stagger: 0.1` introduces a 0.1-second delay between each target's animation start. More complex staggering can be achieved using a stagger object.

```javascript
gsap.to(".myClass", {
  x: 100,
  stagger: 0.1
});
```

--------------------------------

### GSAP v3 Callback Parameters Example

Source: https://gsap.com/docs/v3/GSAP/gsap

Illustrates how to pass custom parameters to GSAP animation callbacks using 'onCompleteParams' and 'onInterruptParams'.

```javascript
function handleComplete(message) {
  console.log(message);
}

gsap.to(".myElement", {
  y: 50,
  onComplete: handleComplete,
  onCompleteParams: ["Tween finished successfully"]
});

function handleInterrupt(reason) {
  console.log("Animation interrupted: " + reason);
}

gsap.to(".anotherElement", {
  opacity: 0,
  onInterrupt: handleInterrupt,
  onInterruptParams: ["due to overwrite"]
});
```

--------------------------------

### Add Animation to Timeline (Relative to Previous Start with Offset)

Source: https://gsap.com/docs/v3/GSAP/Timeline/add%28%29

Adds an animation to a GSAP timeline with a time offset relative to the start of the previous animation. The '<' indicates the start, and a number or percentage specifies the offset.

```javascript
tl.add(animation, "<+=3");
tl.add(animation, "<3");
```

--------------------------------

### Draggable startX Property

Source: https://gsap.com/docs/v3/Plugins/Draggable/startX

The startX property is a read-only number that indicates the starting horizontal position of the Draggable instance when a drag operation begins. Its interpretation depends on the `type` configuration of the Draggable.

```APIDOC
## Draggable startX Property

### Description

The `startX` property is a read-only number that represents the initial horizontal position of the Draggable instance at the beginning of the most recent drag operation. This value is relative to the element's CSS transform translation or other configured properties.

### Method

GET (Read-only property)

### Endpoint

N/A (This is a property of a Draggable instance, not an API endpoint)

### Parameters

This property does not take any parameters.

### Request Example

```javascript
// Assuming 'draggableInstance' is an initialized Draggable instance
const initialX = draggableInstance.startX;
console.log(initialX);
```

### Response

#### Success Response (Property Value)

- **startX** (Number) - The starting horizontal position (e.g., CSS `translateX`, `left`, or rotation value) when the drag began.

#### Response Example

```json
150.5
```

### Details

For `type: "x,y"`, `startX` refers to the CSS `transform: translateX(...)` value.
For `type: "top,left"`, `startX` refers to the CSS `left` value.
For `type: "rotation"`, `startX` refers to the rotation in degrees.
```

--------------------------------

### GSDevTools.create Method

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

This snippet shows the static `create` method of the GSDevTools class, which is used to initialize and instantiate GSDevTools with an optional configuration object. This is the primary way to integrate GSDevTools into your project.

```javascript
GSDevTools.create(config?: object): GSDevTools;
```

--------------------------------

### Minimal EaselJS Animation with GSAP

Source: https://gsap.com/docs/v3/Plugins/EaselPlugin

Demonstrates a basic setup for animating EaselJS objects using GSAP. It includes updating the EaselJS stage on each tick and tweening the 'tint' and 'scale' properties of a circle.

```javascript
gsap.ticker.add(() => stage.update());

gsap.to(circle, {
  duration: 2,
  scaleX: 0.5,
  scaleY: 0.5,
  easel: { tint: 0x00ff00 },
});
```

--------------------------------

### Create GSDevTools Instance (Minimal)

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Creates a minimal GSDevTools instance with default settings. This enables the visual UI for debugging animations on the global timeline. No specific animation instance is linked.

```javascript
GSDevTools.create();
```

--------------------------------

### Add Animation to Timeline (Relative to Previous Start)

Source: https://gsap.com/docs/v3/GSAP/Timeline/add%28%29

Adds an animation to a GSAP timeline at the start of the previously added animation. The '<' character signifies the start of the preceding animation.

```javascript
tl.add(animation, "<");
```

--------------------------------

### Initialize Timeline with Repeat Count (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/repeat%28%29

Shows how to set the initial repeat value for a GSAP timeline when it is created using the vars parameter. This is a common way to configure timeline repetitions from the start.

```javascript
var tl = gsap.timeline({ repeat: 2 });
```

--------------------------------

### GSAP v3 Default Snapping Example

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/getDirectionalSnapFunc

Demonstrates the default behavior of GSAP's snap utility, where values are snapped to the closest increment.

```javascript
let snap = gsap.utils.snap(5); // returns a function that snaps any value to the closest increment of 5
console.log(snap(2)); // 0
console.log(snap(3.5)); // 5
console.log(snap(19)); // 20
```

--------------------------------

### Word-by-Word Text Animation

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Configures TextPlugin to animate text replacement word by word. This is achieved by setting the 'delimiter' property to a space character within the text configuration object.

```javascript
//replaces word-by-word because the delimiter is " " (a space)
gsap.to("#element", {
    duration: 2,
    text: {
        value: "This is the new text",
        delimiter: " "
    },
    ease: "none"
});
```

--------------------------------

### Batching Flip Animations

Source: https://gsap.com/docs/v3/Plugins/Flip

Demonstrates how to use `Flip.batch()` to create multiple coordinated Flip animations. This is essential when dealing with dynamic UI updates in frameworks where elements might be added or removed.

```javascript
import { gsap } from "gsap";
import { Flip } from "gsap/Flip";
gsap.registerPlugin(Flip);

// Assume 'elements' is an array of DOM elements that will be animated
const elements = gsap.utils.toArray(".your-class");

// Record the initial state before any DOM changes
const state = Flip.getState(elements);

// Perform DOM manipulations here (e.g., adding/removing elements, changing styles)

// Animate the changes
Flip.from(state, {
  targets: elements,
  duration: 1,
  ease: "power1.inOut",
  onComplete: () => console.log("Flip animation complete")
});
```

--------------------------------

### play()

Source: https://gsap.com/docs/v3/GSAP/Tween

Begins playing the tween forward, optionally from a specific time. This allows for precise control over the animation's starting point.

```APIDOC
## POST /docs/v3/GSAP/Tween/play().md

### Description
Begins playing forward, optionally from a specific time.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/play().md

### Parameters
#### Path Parameters
- **from** (Number) - Optional - Specifies the time to start from.
- **suppressEvents** (Boolean) - Optional - Whether to suppress events.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **self** (self) - Returns self.

#### Response Example
N/A
```

--------------------------------

### Get Scroll Position with ScrollTrigger Awareness (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/getScrollLookup

The `getScrollLookup` function returns a utility function that calculates the scroll position of a target element. It accounts for ScrollTrigger pinning, container animations, and viewport resizing. It takes a selector or element array as targets and an optional configuration object for start position, pinned container, and container animation.

```javascript
/*
Returns a FUNCTION that you can feed an element to get its scroll position.
- targets: selector text, element, or Array of elements
- config: an object with any of the following optional properties:
- start: defaults to "top top" but can be anything like "center center", "100px 80%", etc. Same format as "start" and "end" ScrollTrigger values.
- containerAnimation: the horizontal scrolling tween/timeline. Must have an ease of "none"/"linear".
- pinnedContainer: if you're pinning a container of the element(s), you must define it so that ScrollTrigger can make the proper accommodations.
*/
function getScrollLookup(
  targets,
  { start, pinnedContainer, containerAnimation }
) {
  let triggers = gsap.utils.toArray(targets).map((el) =>
      ScrollTrigger.create({
        trigger: el,
        start: start || "top top",
        pinnedContainer: pinnedContainer,
        refreshPriority: -10,
        containerAnimation: containerAnimation,
      })
    ),
    st = containerAnimation && containerAnimation.scrollTrigger;
  return (target) => {
    let t = gsap.utils.toArray(target)[0],
      i = triggers.length;
    while (i-- && triggers[i].trigger !== t) {}
    if (i < 0) {
      return console.warn("target not found", target);
    }
    return containerAnimation
      ? st.start +
          (triggers[i].start / containerAnimation.duration()) *
            (st.end - st.start)
      : triggers[i].start;
  };
}
```

```javascript
let getPosition = getScrollLookup(".section", {
  containerAnimation: horizontalTween,
  start: "center center",
});

// then later, use the function as many times as you want to look up any of the scroll position of any ".section" element
gsap.to(window, {
  scrollTo: getPosition("#your-element"),
  duration: 1,
});
```

--------------------------------

### Scrub Timeline to Time with GSAP 3 tweenTo and Advanced Options

Source: https://gsap.com/docs/v3/GSAP/Timeline/tweenTo%28%29

This example shows how to use tweenTo to scrub the timeline to a specific time (5 seconds) and apply advanced tweening options. It includes an onComplete callback, custom parameters for the callback, and a 'strong' ease.

```javascript
tl.tweenTo(5, {
  onComplete: myFunction,
  onCompleteParams: [tl],
  ease: "strong",
});
```

--------------------------------

### Observer.create

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Creates a new Observer instance with specified configuration and callbacks.

```APIDOC
## Observer.create

### Description
Creates a new Observer instance according to the configuration details provided.

### Method
POST

### Endpoint
/websites/gsap_v3/Observer.create

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **vars** (Object) - Required - A configuration object with settings and callbacks like `type`, `onChange`, `onUp`, `onDown`, `debounce`, etc.

### Request Example
```json
{
  "vars": {
    "target": "window",
    "type": "wheel,touch",
    "onUp": "() => previous()",
    "onDown": "() => next()"
  }
}
```

### Response
#### Success Response (200)
- **Observer** (Object) - The newly created Observer instance.

#### Response Example
```json
{
  "Observer": "[Observer Instance Object]"
}
```
```

--------------------------------

### Inertia Animation with Min/Max Boundaries

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

This example shows how to use InertiaPlugin with specific velocity and boundary constraints. The 'x' and 'y' properties will animate to a stop within the defined 'min' and 'max' values, ensuring the animation stays within a desired range.

```javascript
gsap.to(obj, {
  inertia: {
    x: {
      velocity: 500,
      max: 1024,
      min: 0,
    },
    y: {
      velocity: -300,
      max: 720,
      min: 0,
    },
  },
});
```

--------------------------------

### Add Pause at Start of Previous Animation (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/addPause%28%29

Positions a pause at the beginning of the most recently added animation. The '<' character acts as a pointer to the start of that animation.

```javascript
tl.addPause("<");
```

--------------------------------

### GSAP Physics2D Tween with Friction

Source: https://gsap.com/docs/v3/Plugins/Physics2DPlugin

This example shows how to apply friction to a physics-based tween, gradually slowing down the object's movement over the specified duration.

```javascript
gsap.to(element, {
  duration: 2,
  physics2D: { velocity: 300, angle: -60, friction: 0.1 },
});
```

--------------------------------

### Minimal Text Replacement Animation

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Demonstrates the basic usage of GSAP TextPlugin to animate the text content of a DOM element. The text is replaced over a specified duration with a chosen easing function.

```javascript
//replaces yourElement's text with "This is the new text"
gsap.to(yourElement, {
  duration: 2,
  text: "This is the new text",
  ease: "none",
});
```

--------------------------------

### Difference-Based Text Animation

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Enables animating only the differing characters between the old and new text using the 'type: "diff"' property. This optimizes the animation by skipping identical character positions.

```javascript
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Your new text",
    type: "diff"
  }
});
```

--------------------------------

### Get and Set GSAP Timeline Progress (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/progress%28%29

Demonstrates how to get the current progress of a GSAP timeline and how to set it to a specific value. The `progress()` method is used for both operations. Setting the progress returns the timeline instance, enabling method chaining.

```javascript
//gets current progress
var progress = tl.progress();

//sets progress to one quarter finished
tl.progress(0.25);
```

--------------------------------

### Configure Draggable Drag Event Handling

Source: https://gsap.com/docs/v3/Plugins/Draggable

Sets up callback functions and their parameters for the start, during, and end of a drag operation. These callbacks provide access to the Draggable instance and event data.

```javascript
Draggable.create(element, {
  onDragStart: function(event) {
    console.log("Drag started!");
  },
  onDragStartParams: ["startEvent"],
  onDrag: function(event) {
    console.log("Dragging...");
  },
  onDragParams: ["dragEvent"],
  onDragEnd: function(event) {
    console.log("Drag ended!");
  },
  onDragEndParams: ["endEvent"]
});
```

--------------------------------

### GSAP Timeline set() Method Example

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

Demonstrates the basic usage of the timeline.set() method to apply immediate property changes to a target element. This method is a shortcut for adding a gsap.set() tween to the timeline.

```javascript
var tl = gsap.timeline();
var element = document.getElementById('myElement');

// Using gsap.set() and timeline.add()
var setValues = gsap.set(element, { x: 100, opacity: 0.5 });
tl.add(setValues);

// Equivalent and shorter using timeline.set()
tl.set(element, { x: 100, opacity: 0.5 });
```

--------------------------------

### GSAP Timeline: Insert set() at Previous Animation Start

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

Inserts a set() tween at the start of the previously inserted animation in the GSAP timeline. The '<' character acts as a pointer to the beginning of the preceding tween.

```javascript
tl.set(".class", { x: 100 }, "<");
```

--------------------------------

### Get and Set Timeline Repeat Count (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/repeat%28%29

Demonstrates how to get the current repeat value of a GSAP timeline and how to set it to a specific number. This method is versatile, acting as both a getter and a setter.

```javascript
var tl = gsap.timeline({ repeat: 2 });

//gets current repeat value
var repeat = tl.repeat();

//sets repeat to 2
tl.repeat(2);

// Example of chaining
tl.repeat(2).yoyo(true).play();
```

--------------------------------

### Register GSAP v3 Plugins

Source: https://gsap.com/docs/v3/Plugins

Registers multiple GSAP v3 plugins with the GSAP core. This ensures proper integration and prevents issues with build tools. Ensure plugin files are loaded before registration. This example demonstrates registering MotionPathPlugin, ScrollTrigger, and MorphSVGPlugin.

```javascript
gsap.registerPlugin(MotionPathPlugin, ScrollTrigger, MorphSVGPlugin);
```

--------------------------------

### Get and Set GSAP Timeline Yoyo State (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/yoyo%28%29

Demonstrates how to get the current yoyo state of a GSAP timeline and how to set it to true or false. This method is chainable and returns the timeline instance for further configuration.

```javascript
var yoyo = tl.yoyo();
tl.yoyo(true);
```

--------------------------------

### GSAP Tween with Various Easing Options

Source: https://gsap.com/docs/v3/Eases/CustomEase

This example showcases a GSAP tween that utilizes various easing options, including built-in GSAP eases, ease packs, and custom-created eases like CustomBounce. It demonstrates applying different eases to properties like 'y', 'rotation', and 'x'.

```javascript
gsap.to(target, {
  duration: 2.5,
  ease: "Cubic/power2 (power2).out",
  y: -500,
  rotation: 360,
  x: "400%"
});

// Example of creating and using a custom bounce ease
const myBounce = CustomBounce.create("myBounce", {
  strength: 0.7,
  endAtStart: false,
  squash: 1,
  squashID: "myBounce-squash"
});
gsap.to(element, {
  duration: 1,
  y: -100,
  ease: myBounce
});
```

--------------------------------

### Get and Set Tween Iteration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/iteration%28%29

Demonstrates how to use the iteration() method to get the current iteration count of a GSAP tween or set it to a specific value. This method is useful for controlling playback position within repeated tweens.

```javascript
//gets current iteration
var progress = myTween.iteration();

//sets iteration the second iteration
myTween.iteration(2);
```

--------------------------------

### Morph SVG Shape Mapping with shapeIndex (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

The `shapeIndex` property controls how points from the start shape are mapped to the end shape. It acts as an offset, matching a specific point from the start shape to the first point of the end shape. This is useful for inverting or controlling the visual flow of the morph. It only works on closed paths and can be negative to reverse the start path.

```javascript
gsap.to("#square", {
  duration: 1,
  morphSVG: { shape: "#star", shapeIndex: 3 },
});
```

--------------------------------

### Get and Set Animation Paused State (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/paused%28%29

Demonstrates how to get the current paused state of a GSAP animation and how to set it to true or false. The setter returns the animation instance for chaining.

```javascript
//gets current paused state
var paused = tl.paused();

//sets paused state to true, just like pause()
tl.paused(true);

//toggles the paused state
tl.paused(!tl.paused());
```

--------------------------------

### Specifying Targets in Flip.from()

Source: https://gsap.com/docs/v3/Plugins/Flip

Illustrates the correct way to specify `targets` when using `Flip.from()` after capturing state, especially when framework re-renders might create new element instances. This ensures animations apply to the correct elements.

```javascript
// BAD: Omitting targets can lead to animations not applying to new elements
// Flip.from(state, {
//   duration: 1,
// });

// GOOD: Explicitly defining targets ensures Flip animates the correct elements
Flip.from(state, {
  targets: ".your-class", // <-- Correctly targets elements matching the selector
  duration: 1,
  ease: "power1.inOut"
});
```

--------------------------------

### CSS for DrawSVG

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

Provides examples of how to define stroke properties in CSS, which are necessary for DrawSVGPlugin to animate the stroke. This includes setting `stroke-width` and `stroke` color.

```css
/* Define a stroke and stroke-width in CSS: */
.yourPath {
  stroke-width: 10px;
  stroke: red;
}
```

--------------------------------

### InertiaPlugin Linked Properties Example

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

Demonstrates the use of 'linkedProps' to pass multiple properties to a custom 'end' function. This is useful when the stopping logic depends on the values of several related properties, like x and y coordinates.

```javascript
inertia: {
  // ... other properties
  linkedProps: "x,y",
  end: function(values) {
    // 'values' will be an object like {x: 100, y: 140}
    // Return an object with the desired end values
    return { x: 200, y: 300 };
  }
}
```

--------------------------------

### Get ScrollSmoother Velocity on Update (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/getVelocity%28%29

This snippet demonstrates how to get the current scroll velocity using the .getVelocity() method within the onUpdate callback of ScrollSmoother. It logs the velocity in pixels-per-second to the console.

```javascript
ScrollSmoother.create({
  onUpdate: (self) => console.log("velocity:", self.getVelocity()),
});
```

--------------------------------

### Visualize Custom Bounce Ease with SVG (JavaScript)

Source: https://gsap.com/docs/v3/Eases/CustomBounce

This example shows how to use the .getSVGData() method, inherited from CustomEase, to generate SVG path data for visualizing a custom bounce ease. It requires a pre-created CustomBounce ease and an SVG element with an ID.

```javascript
//create a CustomEase with an ID of "hop"
CustomBounce.create("myBounce", {
  strength: 0.6,
  squash: 3,
  squashID: "myBounce-squash",
});

//draw the ease visually in the SVG that has an ID of "ease" at 500px by 400px:
CustomEase.getSVGData("myBounce", { width: 500, height: 400, path: "#ease" });
```

--------------------------------

### Draggable startDrag Method

Source: https://gsap.com/docs/v3/Plugins/Draggable/startDrag%28%29

Forces a Draggable instance to begin dragging, simulating user interaction.

```APIDOC
## Draggable startDrag Method

### Description
Forces the Draggable to begin dragging. This method requires the original event object to accurately measure distances and determine the starting point of the drag.

### Method
`startDrag( event:Object, align:Boolean ) : void`

### Parameters
#### Path Parameters
* None

#### Query Parameters
* None

#### Request Body
* None

### Parameters
#### Event Object
* **event** (Object) - Required - The mouse, touch, or pointer event that initiated the drag. This is crucial for calculating distances and positions.
* **align** (Boolean) - Optional - If `true`, the target element will be immediately moved to align with the pointer if it's not already.

### Request Example
```javascript
// Assuming 'myDraggable' is an instance of Draggable and 'originalEvent' is a valid event object
myDraggable.startDrag(originalEvent, true);
```

### Response
#### Success Response (void)
This method does not return a value.

#### Response Example
N/A
```

--------------------------------

### Get and Set Yoyo State in GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Tween/yoyo%28%29

Demonstrates how to get the current yoyo state of a GSAP tween and how to set it to true. This method is part of the GSAP animation library and is used to control the back-and-forth motion of repeating tweens.

```javascript
//gets current yoyo state
var yoyo = myAnimation.yoyo();

//sets yoyo to true
myAnimation.yoyo(true);
```

--------------------------------

### Scrub Timeline to Label with GSAP 3 tweenTo

Source: https://gsap.com/docs/v3/GSAP/Timeline/tweenTo%28%29

This example demonstrates how to use the tweenTo method to scrub the timeline's playhead to a specific label. It's a straightforward way to navigate to a marked point on the timeline.

```javascript
tl.tweenTo("myLabel2");
```

--------------------------------

### ExpoScaleEase with Custom Base Ease

Source: https://gsap.com/docs/v3/Eases/ExpoScaleEase

Shows how to use ExpoScaleEase with a custom base ease, such as 'power2.inOut'. This allows for more control over the acceleration and deceleration of the scaling animation. The starting and ending scale values, along with the custom ease, are passed to the 'expoScale' function.

```javascript
//scale from 0.5 to 3 using "power2.inOut" ...
gsap.fromTo(
  "#image",
  { scale: 0.5 },
  { duration: 1, scale: 3, ease: "expoScale(0.5, 3, power2.inOut)" }
);
```

--------------------------------

### Kill Specific Properties for a Target - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/kill%28%29

This example demonstrates killing specific properties ('x' and 'y') for a particular target object ('myObject') within an animation.

```javascript
// kill only the "x" and "y" properties of the animation of the target "myObject":
animation.kill(myObject, "x,y");
```

--------------------------------

### Padding Trailing Spaces

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Uses 'padSpace: true' to add non-breaking space characters when the new text is shorter than the old text. This prevents the old text from collapsing visually.

```javascript
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Shorter text",
    padSpace: true
  }
});
```

--------------------------------

### Absolute Time Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Insert an animation at a specific time (in seconds) from the start of the timeline. This method is straightforward for precise timing.

```javascript
tl.from(".class", { x: 100 }, 3);
```

--------------------------------

### Using fromTo with CSSRulePlugin for Undefined Styles

Source: https://gsap.com/docs/v3/Plugins/CSSRulePlugin

Explains and demonstrates how to use `gsap.fromTo()` with CSSRulePlugin when the style property is not initially defined in the CSS rule. This ensures a predictable starting point for the animation, preventing it from animating from a default like 'transparent'.

```javascript
// Example assuming '.myClass::before' has no initial color defined
var rule = CSSRulePlugin.getRule(".myClass::before");
gsap.fromTo(rule, { duration: 3, cssRule: { color: "transparent" } }, { duration: 3, cssRule: { color: "blue" } });
```

--------------------------------

### Create a GSAP distribute function

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/distribute%28%29

This snippet demonstrates how to create a distributor function using `gsap.utils.distribute`. The function takes configuration options to define how values are distributed, such as a base value, total amount, starting point, grid layout, and easing. The returned function can then be used to calculate a distributed value for a specific element's index.

```javascript
let distributor = gsap.utils.distribute({
  base: 50,
  amount: 100,
  from: "center",
  grid: "auto",
  axis: "y",
  ease: "power1.inOut",
});

let targets = gsap.utils.toArray(".box");

let distributedValue = distributor(2, targets[2], targets);
```

--------------------------------

### paused() - Get or Set Animation Paused State

Source: https://gsap.com/docs/v3/GSAP/Timeline/paused%28%29

The paused() method in GSAP v3 allows you to get the current paused state of an animation or set it to either paused or resumed. It can also be used for toggling the state.

```APIDOC
## GET / SET paused()

### Description
Gets or sets the animation's paused state. When used as a getter, it returns a boolean indicating if the animation is currently paused. When used as a setter, it accepts a boolean value to set the paused state and returns the animation instance for chaining.

### Method
GET / SET (Instance Method)

### Endpoint
`animationInstance.paused( [value:Boolean] )`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Get current paused state
var isPaused = animation.paused();

// Set paused state to true
animation.paused(true);

// Toggle paused state
animation.paused(!animation.paused());

// Set paused state and chain other methods
animation.paused(true).delay(1).timeScale(0.5);
```

### Response
#### Success Response (Getter)
- **pausedState** (Boolean) - `true` if the animation is paused, `false` otherwise.

#### Success Response (Setter)
- **animationInstance** (Object) - The animation instance itself, allowing for method chaining.

#### Response Example (Getter)
```json
{
  "pausedState": true
}
```

#### Response Example (Setter)
```javascript
// Returns the animation instance for chaining
{
  // ... animation instance properties ...
}
```

### Details
This method controls whether an animation is actively playing or stopped. A paused animation does not advance its progress. It's important to note that this state is independent of ancestor timelines; if a parent timeline is paused, the child animation will appear paused even if its own `paused()` state is `false`. Setting `paused` to `true` is equivalent to calling the `pause()` method, and setting it to `false` is equivalent to calling `resume()`.

You can also set the initial paused state when creating an animation by passing `paused: true` within the `vars` object.
```

--------------------------------

### onPressInit Callback Function - GSAP Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

The onPressInit function is called before the starting values are recorded during the onPress event. This allows modifications before any dragging begins. It always fires before onPress.

```javascript
onPressInit: function() {
  // 'this' refers to the Draggable instance
  console.log("Initializing press values...");
  // Modify Draggable properties or state here before onPress fires
}
```

--------------------------------

### GSAP Timeline Control and Callbacks

Source: https://gsap.com/docs/v3/GSAP/Timeline

Demonstrates creating a GSAP timeline with repeat, repeatDelay, and onComplete callbacks. It also shows adding tweens, using relative sequencing, reversing, adding labels, playing from labels, and nesting timelines.

```javascript
var tl = gsap.timeline({ repeat: 3, repeatDelay: 1, onComplete: myFunction });

tl.to(".class", { duration: 1, x: 200, y: 100 });
tl.to("#id", { duration: 0.8, opacity: 0 }, "+=0.5");
tl.reverse();

tl.addLabel("spin", 3);
tl.to(".class", { duration: 2, rotation: "+=360" }, "spin");

tl.play("spin");

var nested = gsap.timeline();
nested.to(".class2", { duration: 1, x: 200 });
tl.add(nested, "+=3");
```

--------------------------------

### totalTime Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/totalTime%28%29

Gets or sets the position of the playhead according to the totalDuration, which includes any repeats and repeatDelays.

```APIDOC
## totalTime

### Description
Gets or sets the position of the playhead according to the `totalDuration` which includes any repeats and repeatDelays.

### Method
GET / SET

### Endpoint
N/A (Method within an animation instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### **time** (Number) - Optional
Omitting the parameter returns the current value (getter). Defining the parameter sets the value (setter). Negative values are interpreted from the end of the animation.

#### **suppressEvents** (Boolean) - Optional
(default = `false`) If `true`, no events or callbacks will be triggered when the playhead moves to the new position.

### Request Example
```javascript
// Getter example
var currentTime = animation.totalTime();

// Setter example
animation.totalTime(5); // Sets the playhead to 5 seconds
animation.totalTime(-2); // Sets the playhead to 2 seconds before the end
animation.totalTime(2, true); // Sets the playhead to 2 seconds without triggering events
```

### Response
#### Success Response (Getter)
- **totalTime** (Number) - The current total time of the animation's playhead.

#### Success Response (Setter)
- **self** (Object) - The animation instance itself, for easier chaining.

#### Response Example (Getter)
```json
{
  "totalTime": 5.2
}
```

#### Response Example (Setter)
```json
{
  "animationInstance": "[Instance Object]"
}
```

### Details
Gets or sets the position of the playhead according to the `totalDuration` which **includes any repeats and repeatDelays**. For example, if a tween has a `duration` of 2 and a `repeat` of 3, `totalTime` will go from 0 to 8 during the course of the tween (plays once then repeats 3 times, making 4 total cycles) whereas `time` will go from 0 to 2 a total of 4 times. If you added a `repeatDelay` of 1, that would make the `totalTime` go from 0 to 11 over the course of the tween.

This method serves as both a getter and setter. Omitting the parameter returns the current value (getter), whereas defining the parameter sets the value (setter) and returns the instance itself for easier chaining.

`totalTime` will never exceed the `totalDuration`, nor will it be less than 0 (values will be clipped appropriately). Negative values will be interpreted from the **END** of the animation. For example, -2 would be 2 seconds before the end. If the animation's `totalDuration` is 6 and you do `tl.totalTime(-2)`, it will jump to a `totalTime` of 4.
```

--------------------------------

### Get or Set Animation Reversed State (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/reversed%28%29

This snippet demonstrates how to use the reversed() method in GSAP v3. It shows how to get the current reversed state of an animation, set it to a specific boolean value (true for reversed, false for forward), and toggle the state. This method is useful for controlling playback direction and enabling chaining of animation properties.

```javascript
//gets current orientation
var isReversed = tl.reversed();

//sets the orientation to reversed
tl.reversed(true);

//toggles the orientation
tl.reversed(!tl.reversed());
```

--------------------------------

### Using prepareText for Custom Splitting Logic

Source: https://gsap.com/docs/v3/Plugins/SplitText

Illustrates the use of the `prepareText` function to modify text chunks before splitting. This is particularly useful for languages without spaces, allowing for custom word boundary detection.

```javascript
const split = new SplitText("#myElement", {
  type: "words",
  prepareText: function(rawText, parent) {
    // Example: Insert a character to mark potential word breaks in Chinese
    return rawText.replace(/([一-鿿])/g, '$1\u200B');
  }
});
```

--------------------------------

### ScrollTrigger.sort() API

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/static

This section details the ScrollTrigger.sort() static method, its parameters, return value, and provides usage examples.

```APIDOC
## ScrollTrigger.sort()

### Description
Sorts the internal Array of ScrollTrigger instances to control the order in which they refresh() (calculate their start/end values). This is typically only needed if ScrollTriggers are created out of their natural page order.

### Method
`ScrollTrigger.sort( [func:Function] )`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters

```

--------------------------------

### GSAP v3 Directional Snapping Usage Example

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/getDirectionalSnapFunc

Illustrates how to use the `getDirectionalSnapFunc` to snap values in a specific direction (greater or lesser) using a numeric increment.

```javascript
let snap = getDirectionalSnapFunc(5); // returns a function that snaps any value to the closest increment of 5 in a particular direction
console.log(snap(2, 1)); // 5
console.log(snap(3.5, -1)); // 0
console.log(snap(19, -1)); // 15
```

--------------------------------

### Get Velocity

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/VelocityTracker/.get%28%29

Retrieves the current velocity of a specified property managed by GSAP v3.

```APIDOC
## GET /websites/gsap_v3

### Description
Returns the current velocity of the given property.

### Method
GET

### Endpoint
/websites/gsap_v3

### Parameters
#### Query Parameters
- **property** (string) - Required - The property for which to retrieve the velocity.

### Response
#### Success Response (200)
- **velocity** (Number) - The current velocity of the property.

#### Response Example
```json
{
  "velocity": 150.75
}
```
```

--------------------------------

### Immediate Render Override in GSAP

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Control whether a 'from()' tween renders its starting state immediately or waits until the tween begins. By default, 'immediateRender' is true for 'from()' tweens.

```javascript
// Override default immediateRender behavior
tl.from(".class", { x: 100 }, { immediateRender: false });
```

--------------------------------

### GSAP v3 Tween with Custom Ease Properties

Source: https://gsap.com/docs/v3/Eases

An example of a GSAP tween that applies a specific ease, 'Cubic/power2 (power2).out', and demonstrates how to configure custom ease properties like strength, points, and taper.

```javascript
gsap.to(target, {
  duration: 2.5,
  ease: "Cubic/power2 (power2).out",
  // Custom ease properties can be configured here if applicable
  // For example, for RoughEase:
  // ease: "rough({ strength: 1, points: 20, taper: "none", randomize: ["x"], clamp: [] })"
  // For ExpoScaleEase:
  // ease: "expoScale(0.5, 7, "none")"
  // For CustomEase:
  // ease: CustomEase.create("custom", "0"),
  // For CustomWiggle:
  // ease: create("custom", "myWiggle", {
  //   wiggles: 10,
  //   type: "easeInOut"
  // }),
  // For CustomBounce:
  // ease: create("custom", "myBounce", {
  //   strength: 0.7,
  //   endAtStart: false,
  //   squash: 1,
  //   squashID: "myBounce-squash"
  // }),
  y: -500,
  rotation: 360,
  x: "400%"
});

```

--------------------------------

### repeatDelay()

Source: https://gsap.com/docs/v3/GSAP/Tween

Gets or sets the amount of time in seconds between repeats. This allows for control over the timing of repeated animations.

```APIDOC
## POST /docs/v3/GSAP/Tween/repeatDelay().md

### Description
Gets or sets the amount of time in seconds between repeats.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/repeatDelay().md

### Parameters
#### Path Parameters
- **value** (Number) - Required - The delay in seconds.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Number | self** (Number | self) - Returns the delay or self.

#### Response Example
N/A
```

--------------------------------

### GSAP v3 Chaining Timeline Methods

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Illustrates chaining multiple GSAP timeline methods, including from(), to(), set(), and call(), to create complex animation sequences. This showcases the power of GSAP for building intricate animations efficiently.

```javascript
//create a timeline that calls myFunction() when it completes
var tl = gsap.timeline({ onComplete: myFunction });

//now we'll use chaining, but break each step onto a different line for readability...

//tween element's x from -100
tl.from(element, { duration: 1, x: -100 })

  //then tween element's y to 50
  .to(element, { duration: 1, y: 50 })

  //then set element's opacity to 0.5 immediately
  .set(element, { opacity: 0 })

  //then call otherFunction()
  .call(otherFunction)

  //finally tween the rotation of all elements with the class "myClass" to 45 and stagger the start times by 0.25 seconds
  .to(".myClass", { duration: 1.5, rotation: 45, stagger: 0.25 });
```

--------------------------------

### killTweensOf Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/killTweensOf%28%29

This section details the killTweensOf method, explaining its parameters, return value, and providing usage examples.

```APIDOC
## killTweensOf

### Description
Kills all of the tweens inside this timeline that affect the provided `targets`. You can optionally specify specific properties that you want killed.

### Method
`killTweensOf( targets:Selector text | Array | Object
```

--------------------------------

### Get and Set GSAP Animation Time Scale

Source: https://gsap.com/docs/v3/GSAP/Timeline/timeScale%28%29

Demonstrates how to get the current timeScale of a GSAP animation and how to set a new timeScale value. The timeScale property controls the speed of the animation, where 1 is normal speed, 0.5 is half speed, and 2 is double speed. This method can be used as both a getter and a setter.

```javascript
//gets current timeScale
var currentTimeScale = tl.timeScale();

//sets timeScale to half-speed
tl.timeScale(0.5);
```

--------------------------------

### Get Scroll Position for GSAP ScrollTrigger Animation (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/getScrollPosition

This JavaScript function calculates the scroll position for a GSAP ScrollTriggered animation at a specified progress value. It handles animations with and without a `containerAnimation` and returns the calculated scroll position, which can be used with GSAP's `scrollTo` tween.

```javascript
function getScrollPosition(animation, progress) {
  let p = gsap.utils.clamp(0, 1, progress || 0),
    st = animation.scrollTrigger,
    containerAnimation = st.vars.containerAnimation;
  if (containerAnimation) {
    let time = st.start + (st.end - st.start) * p;
    st = containerAnimation.scrollTrigger;
    return (
      st.start + (st.end - st.start) * (time / containerAnimation.duration())
    );
  }
  return st.start + (st.end - st.start) * p;
}
```

--------------------------------

### gsap.utils.getUnit

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/getUnit%28%29

Extracts the unit from a string. It assumes the string starts with a number followed by a unit.

```APIDOC
## gsap.utils.getUnit

### Description
Returns the unit of a given string where the number comes first, then the unit. Isolates the unit inside a string where the number is first, then the unit.

### Method
Utility Function

### Endpoint
N/A

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
gsap.utils.getUnit("50%"); // "%"
gsap.utils.getUnit("100vw"); // "vw"
```

### Response
#### Success Response (200)
- **unit** (String) - The extracted unit from the input string.

#### Response Example
```json
{
  "unit": "%"
}
```
```

--------------------------------

### Apply Units with unitize() in JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/unitize%28%29

Demonstrates how to use GSAP's unitize() utility to wrap other functions, ensuring their results have a specific unit appended. It also shows how to dynamically use the input unit if none is specified.

```javascript
// Get a function that always applies "px" to the result (and strips off any units from the input)
var clamp = gsap.utils.unitize(gsap.utils.clamp(0, 100), "px");

// now the result always gets "px" added:
console.log(clamp(132)); // "100px"
console.log(clamp("-20%")); // "0px" (notice the unit change)
console.log(clamp(50)); // "50px"

// or use whatever unit is in the input:
var wrap = gsap.utils.unitize(gsap.utils.wrap(0, 100)); // no specific unit is declared in unitize()
console.log(wrap("150px")); // "50px"
console.log(wrap("130%")); // "30%"

// another example of forcing a unit like "%"
var map = gsap.utils.unitize(gsap.utils.mapRange(-10, 10, 0, 100), "%");
console.log(map(0)); // "50%"
console.log(map("5px")); // "75%"

// useful in modifier functions:
gsap.to(".class", {
  x: 1000,
  modifiers: {
    //the value fed into this function will have unit - this strips it off to feed in a raw number to wrap() and then slaps "px" onto the result.
    x: gsap.utils.unitize(gsap.utils.wrap(0, window.innerWidth), "px"),
  },
});

```

--------------------------------

### Get and Set Tween Repeat Count - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/repeat%28%29

This snippet demonstrates how to use the GSAP v3 repeat method to get the current repeat count of a tween and how to set a new repeat count. The method is versatile, acting as both a getter and a setter. When used as a setter, it returns the tween instance for chaining.

```javascript
// Gets current repeat
var progress = myTween.repeat();

// Sets repeat to 2
myTween.repeat(2);
```

--------------------------------

### Get and Set Timeline Total Duration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/totalDuration%28%29

Demonstrates how to use the totalDuration method to get the current total duration of a GSAP timeline or set a new total duration. Setting the total duration adjusts the timeScale to fit the content within the specified time. This method is part of the GSAP animation library.

```javascript
//gets total duration
var total = tl.totalDuration();

//adjusts the timeScale of the timeline so that it fits into exactly 10 seconds on its parent timeline
tl.totalDuration(10);
```

--------------------------------

### Create MotionPathHelper for a New Path

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

This snippet illustrates how to initialize MotionPathHelper for a new motion path by providing an element selector. The helper will create a basic path that can then be edited interactively.

```javascript
// just pass the element or selector text:
MotionPathHelper.create("#id");
```

--------------------------------

### Absolute Time Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Inserts an animation at an exact time in seconds from the start of the timeline. This method is straightforward for precise timing.

```javascript
tl.fromTo(".class", { x: 100 }, { x: 200 }, 3);
```

--------------------------------

### Blend Two Eases in JavaScript with GSAP

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/blendEases

This JavaScript function blends two GSAP easing functions. It takes the starting ease, ending ease, and an optional blending ease as arguments. The function returns a new ease that transitions from the start ease to the end ease based on the blender's value. It handles cases where eases are provided as strings or functions.

```javascript
function blendEases(startEase, endEase, blender) {
  var parse = function (ease) {
      return typeof ease === "function" ? ease : gsap.parseEase("power4.inOut");
    },
    s = gsap.parseEase(startEase),
    e = gsap.parseEase(endEase),
    blender = parse(blender);
  return function (v) {
    var b = blender(v);
    return s(v) * (1 - b) + e(v) * b;
  };
}
//example usage:
gsap.to("#target", {
  duration: 2,
  x: 100,
  ease: blendEases("back.in(1.2)", "bounce"),
});
```

--------------------------------

### Configure Draggable with Custom Inertia Object

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example shows how to provide a custom inertia object to fine-tune the momentum-based motion after release. This allows for advanced control over properties like 'min', 'max', and specific 'end' values for the inertia tween.

```javascript
Draggable.create(element, {
  inertia: {
    top: {
      min: 0,
      max: 1000,
      end: [0, 200, 400, 600]
    }
  }
});
```

--------------------------------

### GSAP v3 Tween Properties Example (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

Demonstrates the usage of common properties within the 'vars' object for GSAP v3 tweens. This includes setting animation duration, ease, delay, and defining callback functions for events like onComplete and onUpdate.

```javascript
gsap.to(".myElement", {
  x: 100,
  duration: 1,
  ease: "power2.inOut",
  delay: 0.5,
  onComplete: myCompleteFunction,
  onUpdate: myUpdateFunction,
  repeat: -1,
  repeatDelay: 1,
  overwrite: "auto",
  paused: false,
  immediateRender: true,
  lazy: true,
  inherit: true,
  data: { custom: "info" },
  callbackScope: this
});

function myCompleteFunction() {
  console.log("Animation complete!");
}

function myUpdateFunction() {
  console.log("Animation updating...");
}
```

--------------------------------

### Setting and Getting GSAP Animation Event Callbacks

Source: https://gsap.com/docs/v3/GSAP/Tween/eventCallback%28%29

Demonstrates how to set and retrieve event callbacks for GSAP animations using the eventCallback method. This includes setting callbacks with parameters and deleting them by passing null. It also shows how to chain multiple eventCallback calls.

```javascript
gsap.to(obj, {
	duration: 1,
	x: 100,
	onComplete: myFunction,
	onCompleteParams: ['param1', 'param2']
});

// Equivalent using eventCallback:
myAnimation.eventCallback('onComplete', myFunction, ['param1', 'param2']);

// Deleting an event callback:
myAnimation.eventCallback('onUpdate', null);

// Chaining event callbacks:
myAnimation
	.eventCallback('onComplete', completeHandler)
	.eventCallback('onUpdate', updateHandler, ['param1'])
	.play(1);
```

--------------------------------

### repeat()

Source: https://gsap.com/docs/v3/GSAP/Tween

Gets or sets the number of times the tween should repeat after its first iteration. This is useful for creating looping animations.

```APIDOC
## POST /docs/v3/GSAP/Tween/repeat().md

### Description
Gets or sets the number of times that the tween should repeat.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/repeat().md

### Parameters
#### Path Parameters
- **value** (Number) - Required - The number of repeats.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Number | self** (Number | self) - Returns the repeat value or self.

#### Response Example
N/A
```

--------------------------------

### getDirection() Method

Source: https://gsap.com/docs/v3/Plugins/Draggable/getDirection%28%29

Retrieves the direction of the Draggable instance. This can be measured from the start of the drag, the current velocity, or in relation to another specified element.

```APIDOC
## GET /websites/gsap_v3/getDirection

### Description
Returns the `direction` (`"right"` | `"left"` | `"up"` | `"down"` | `"left-up"` | `"left-down"` | `"right-up"` | `"right-down"`) as measured from either where the drag started (the default), the moment-by-moment velocity, or its proximity to another element that you define.

### Method
GET

### Endpoint
/websites/gsap_v3/getDirection

### Parameters
#### Path Parameters
None

#### Query Parameters
* **from** (String | Element) - Optional - Specifies the reference point for measuring direction. Can be "start" (default), "velocity" (requires InertiaPlugin), or a target element.

### Request Example
```json
{
  "from": "start" 
}
```

### Response
#### Success Response (200)
* **direction** (String) - The measured direction of the drag.

#### Response Example
```json
{
  "direction": "right-up"
}
```
```

--------------------------------

### Define Motion Path using Configuration Object

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Illustrates using a configuration object for the motion path, which allows for advanced settings like aligning to another path, setting auto-rotation, defining start and end points, and more. The 'path' property within this object can accept any of the previously mentioned path formats.

```javascript
motionPath: {
  path: "#pathID",
  align: "#pathID",
  alignOrigin: [0.5, 0.5],
  autoRotate: true,
  start: 0.25,
  end: 0.75
}
```

--------------------------------

### ScrollSmoother Wrapper API

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/wrapper%28%29

This section details the .wrapper() method of the GSAP ScrollSmoother instance, which allows you to get or set the wrapper element for scrolling.

```APIDOC
## .wrapper()

### Description
Gets or sets the wrapper element for the ScrollSmoother instance. This element defines the boundaries for the scrolling behavior.

### Method
GET/SET

### Endpoint
N/A (Instance method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None (for getter)

- **element** (String | Element) - Optional - The element to be used as the wrapper. This can be a CSS selector string (e.g., `"#my-wrapper"`) or a direct DOM element reference. If not provided, the method acts as a getter.

### Request Example
#### Getter
```javascript
let wrapperElement = smoother.wrapper();
```

#### Setter
```javascript
// Set the wrapper to the element with the ID "main-content"
smoother.wrapper("#main-content");
```

### Response
#### Success Response (Getter)
- **wrapperElement** (Element) - The current wrapper DOM element.

#### Success Response (Setter)
- **self** (ScrollSmoother) - The ScrollSmoother instance itself, allowing for method chaining.

#### Response Example (Getter)
```json
{
  "wrapperElement": "<div id=\"main-content\">...</div>"
}
```

#### Response Example (Setter)
```json
{
  "instance": "ScrollSmoother"
}
```
```

--------------------------------

### ScrollSmoother .content()

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/content%28%29

Gets or sets the content element for the ScrollSmoother instance. This element defines the scrollable area.

```APIDOC
## .content()

### Description
Gets or sets the content element for the ScrollSmoother instance. This element defines the scrollable area.

### Method
GET / SET

### Endpoint
N/A (Instance method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
#### Getter
```javascript
let content = smoother.content();
```

#### Setter
```javascript
// set the content to the element with #content id
smoother.content("#content");
```

### Response
#### Success Response (Getter)
- **Element** (Element) - The current content element.

#### Success Response (Setter)
- **self** (ScrollSmoother) - The ScrollSmoother instance itself, allowing for chaining.

#### Response Example (Getter)
```json
{
  "example": "<div id=\"myContent\">...</div>"
}
```

#### Response Example (Setter)
```json
{
  "example": "[ScrollSmoother instance]"
}
```
```

--------------------------------

### Nesting GSAP Timelines for Modular Animations

Source: https://gsap.com/docs/v3/GSAP/Timeline

Illustrates how to create modular and maintainable animations by nesting GSAP timelines within a master timeline. This approach allows for building complex animation sequences in manageable sections.

```javascript
function intro() {
  var tl = gsap.timeline();
  //...add animations here...
  return tl;
}

function middle() {
  var tl = gsap.timeline();
  //...add animations here...
  return tl;
}

function conclusion() {
  var tl = gsap.timeline();
  //...add animations here...
  return tl;
}

// stitch them together in a master timeline...
var master = gsap.timeline();
master
  .add(intro())
  .add(middle(), "+=2") //with a gap of 2 seconds
  .add(conclusion(), "-=1"); //overlap by 1 second
```

--------------------------------

### Draggable with Inertia and Bounds

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example shows how to create a draggable element with inertia effects and defined bounds. It requires both Draggable and InertiaPlugin to be registered. The element will be constrained within the '#container' element and will decelerate smoothly after being flicked.

```javascript
gsap.registerPlugin(Draggable, InertiaPlugin);

Draggable.create('#myElement', {
	bounds: '#container',
	inertia: true,
	resistance: 0.5,
	// other configurations...
});
```

--------------------------------

### progress()

Source: https://gsap.com/docs/v3/GSAP/Tween

Gets or sets the tween's progress, a value between 0 and 1 indicating the playhead's position. This allows for direct control over the animation's progress.

```APIDOC
## POST /docs/v3/GSAP/Tween/progress().md

### Description
Gets or sets the tween's progress.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/progress().md

### Parameters
#### Path Parameters
- **value** (Number) - Required - The progress value (0-1).
- **suppressEvents** (Boolean) - Optional - Whether to suppress events.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Number | self** (Number | self) - Returns the progress or self.

#### Response Example
N/A
```

--------------------------------

### Configure Draggable with onThrowComplete Callback

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example shows how to define an 'onThrowComplete' callback function for the InertiaPlugin. This function is called once the inertia tween has finished, signaling the end of the momentum-based motion after the user releases the element.

```javascript
Draggable.create(element, {
  inertia: true,
  onThrowComplete: function() {
    console.log('Inertia tween complete!');
  }
});
```

--------------------------------

### repeat Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/repeat%28%29

The repeat method allows you to get or set the number of times a GSAP timeline should repeat after its initial playback. It can also be used for chaining other methods.

```APIDOC
## GET/SET repeat

### Description
Gets or sets the number of times that the timeline should repeat after its first iteration. Use `-1` for indefinite repeats.

### Method
GET/SET

### Endpoint
N/A (This is a method of a GSAP timeline instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Getter: Get the current repeat value
var currentRepeat = myTimeline.repeat();

// Setter: Set the repeat value to 2
myTimeline.repeat(2);

// Chaining: Set repeat and yoyo, then play
myTimeline.repeat(2).yoyo(true).play();
```

### Response
#### Success Response (Getter)
- **repeatValue** (Number) - The current number of repeats.

#### Success Response (Setter)
- **instance** (Object) - The GSAP timeline instance itself, allowing for chaining.

#### Response Example (Getter)
```json
{
  "repeatValue": 1
}
```

#### Response Example (Setter)
```json
{
  "instance": "[GSAP Timeline Object]"
}
```

### Details
- The `repeat` property should be an integer.
- Setting `yoyo` to `true` will cause repeats to alternate between forward and backward playback.
- `repeatDelay` can be used to add a time gap between repeats.
- The initial `repeat` value can be set via the `vars` parameter during timeline creation: `gsap.timeline({ repeat: 2 });`
```

--------------------------------

### GSAP 3: Play Animation from Current Position

Source: https://gsap.com/docs/v3/GSAP/Tween/play%28%29

Starts playing a GSAP animation from its current playback position. This is the default behavior when no arguments are provided.

```javascript
myAnimation.play();
```

--------------------------------

### Register GSAP EasePack Plugin

Source: https://gsap.com/docs/v3/Eases/RoughEase

This code snippet shows how to register the EasePack plugin, which is necessary to use eases like RoughEase. It's a one-time setup required before using any EasePack features.

```javascript
gsap.registerPlugin(EasePack)
```

--------------------------------

### ScrollTrigger Configuration Options

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This section details the various configuration options available for ScrollTrigger, including callbacks, start position definitions, animation toggle actions, class toggling, and trigger element selection.

```APIDOC
## ScrollTrigger Configuration Options

### Description
Configuration options for ScrollTrigger, including callbacks, start position, toggle actions, class toggling, and trigger element.

### Parameters

#### Callback Functions

- **onInterrupt** (Function) - A function called when snapping is interrupted (e.g., user scrolls mid-snap).
- **onComplete** (Function) - A function called when snapping completes.

#### Start Position

- **start** (String | Number | Function) - Determines the starting position of the ScrollTrigger. Can be a string (e.g., \"top center\"), a number (scroll value), or a function that returns a string or number. Defaults to \"top bottom\" (or \"top top\" if `pin: true`).
  - **String Format**: Describes positions relative to the trigger and scroller (e.g., \"top center\", \"bottom 80%\"). Supports keywords (top, bottom, center, left, right), percentages, and pixel values. Can also use relative values like \"top bottom-=100px\".
  - **Number Format**: An exact scroll value (e.g., `200`).
  - **Function Format**: A function that returns a position string or number, receiving the ScrollTrigger instance as a parameter.
  - **`clamp()`**: (v3.12+) Wraps the start value in `clamp()` to keep it within page bounds (0 to max scroll position). Example: `start: \"clamp(top bottom)\"`.

#### Animation Control

- **toggleActions** (String) - Controls animation playback at four toggle points: onEnter, onLeave, onEnterBack, and onLeaveBack (in that order). Default is `play none none none`. Keywords include: \"play\", \"pause\", \"resume\", \"reset\", \"restart\", \"complete\", \"reverse\", and \"none\". Example: `toggleActions: \"play pause resume reset\".

#### Class Toggling

- **toggleClass** (String | Object) - Adds/removes a class when the ScrollTrigger is active/inactive.
  - **String**: Class name to add to the `trigger` element (e.g., `toggleClass: \"active\"`).
  - **Object**: For toggling classes on other elements. Syntax: `toggleClass: {targets: ".my-selector", className: "active"}`. `targets` can be a selector, element, or array of elements.
  - Note: `toggleActions` do not apply to `toggleClass`. Use callbacks for alternative class management.

#### Trigger Element

- **trigger** (String | Element) - The element (or selector text) used to calculate the ScrollTrigger's start position. Defaults to the element the ScrollTrigger is applied to.
```

--------------------------------

### Staggered DrawSVG Animation

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

Shows how to animate multiple SVG elements with staggered start times using DrawSVGPlugin. Each element with the class 'draw-me' will begin drawing 0.1 seconds after the previous one.

```javascript
//draws all elements with the "draw-me" class applied with staggered start times 0.1 seconds apart
gsap.from('.draw-me', { duration: 1, stagger: 0.1, drawSVG: 0 });
```

--------------------------------

### ScrollTrigger Progress

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/progress

Accesses the read-only progress of a ScrollTrigger instance. This value ranges from 0 (start) to 1 (end), with 0.5 representing the middle.

```APIDOC
## GET /scroll-trigger/progress

### Description
Retrieves the current progress of the ScrollTrigger instance. This is a read-only property indicating the position of the trigger relative to its start and end points.

### Method
GET

### Endpoint
/scroll-trigger/progress

### Parameters
#### Query Parameters
- **instanceId** (string) - Required - The unique identifier for the ScrollTrigger instance.

### Response
#### Success Response (200)
- **progress** (number) - The overall progress of the ScrollTrigger instance, where 0 is the start, 0.5 is the middle, and 1 is the end.

#### Response Example
```json
{
  "progress": 0.75
}
```
```

--------------------------------

### Absolute Time Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Inserts an animation at a specific absolute time (in seconds) from the start of the timeline. This is useful for precise timing of elements.

```javascript
tl.to(".class", { x: 100 }, 3);
```

--------------------------------

### GSAP v3 Play Animation Forward

Source: https://gsap.com/docs/v3/GSAP/Timeline/play%28%29

Starts GSAP animation playback forward from the current position or a specified time. Optionally suppresses events during the initial move to the 'from' time.

```javascript
tl.play();
tl.play(2);
tl.play(2, false);
```

--------------------------------

### Draggable with Axis Locking and Callbacks

Source: https://gsap.com/docs/v3/Plugins/Draggable

This example demonstrates how to lock dragging to a specific axis and utilize callback functions for different drag events. It shows how to respond to actions like pressing, dragging, and releasing the element.

```javascript
Draggable.create('#myRotatableElement', {
	type: 'rotation',
	lockAxis: true, // Locks movement to the initial drag direction
	onPress: function() {
		console.log('Pressed!');
	},
	onDrag: function() {
		console.log('Dragging...');
	},
	onRelease: function() {
		console.log('Released!');
	}
});
```

--------------------------------

### Position Animations in GSAP Timeline (Relative to Last Animation)

Source: https://gsap.com/docs/v3/GSAP/Timeline

Illustrates positioning animations relative to the start (`<`) or end (`>`) of the most recently added animation, including offsets.

```javascript
tl.to(".class", { x: 100 }, "<");
tl.to(".class", { x: 100 }, ">");
tl.to(".class", { x: 100 }, "<1");
tl.to(".class", { y: 100 }, "<-2");
tl.to(".class", { x: 100, duration: 1 }, ">1");
tl.to(".class", { y: 100, duration: 1 }, ">-2");
```

--------------------------------

### Create a basic GSAP Tween

Source: https://gsap.com/docs/v3/GSAP

Demonstrates creating a basic animation (Tween) using GSAP. The `gsap.to()` method animates specified properties of target elements over a given duration. In this example, it rotates and moves elements with the class 'box'.

```javascript
// This is a Tween
gsap.to(".box", { rotation: 27, x: 100, duration: 1 });

//And this is a Timeline, containing three sequenced tweens
let tl = gsap.timeline();
tl.to("#green", {duration: 1, x: 786})
  .to("#blue", {duration: 2, x: 786})
  .to("#orange", {duration: 1, x: 786})

```

--------------------------------

### GSAP MotionPath Tween with Custom Path Properties

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

An example of using GSAP's MotionPathPlugin to animate an element through custom properties (not just x/y coordinates). This demonstrates how the plugin smooths velocity changes between defined values, with adjustable curviness.

```javascript
gsap.to(element, {
  motionPath: {
    path: [
      { scale: 0 },
      { scale: 1 },
      { scale: 0.5 },
      { scale: 1.5 },
      { scale: 1 }
    ],
    curviness: 2 // or 0 for straight lines
  },
  duration: 3,
  ease: "power1.inOut"
});
```

--------------------------------

### eventCallback Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/eventCallback%28%29

The eventCallback method allows you to get or set animation event callbacks such as onComplete, onUpdate, onStart, onReverseComplete, and onRepeat, including any parameters to be passed to the callback function.

```APIDOC
## eventCallback

### Description
Gets or sets an event callback like `onComplete`, `onUpdate`, `onStart`, `onReverseComplete`, or `onRepeat` along with any parameters that should be passed to that callback.

### Method
`eventCallback( type:String, callback:Function, params:Array )`

### Parameters
#### Path Parameters
* **type** (String) - Required - The type of event callback (e.g., `"onComplete"`, `"onUpdate"`, `"onStart"`, `"onRepeat"`). This is case-sensitive.
* **callback** (Function) - Optional - The function to be executed when the event occurs. Defaults to `null`.
* **params** (Array) - Optional - An array of parameters to pass to the callback function. Defaults to `null`.

### Returns
`Function | self` - If only the `type` is provided, it returns the current callback function. If `callback` and/or `params` are provided, it sets the callback and returns the animation instance for chaining.

### Details
This method can be used to set or retrieve event callbacks after an animation instance has been created. It's functionally equivalent to defining these callbacks in the constructor's `vars` object initially. Providing `null` for the `callback` parameter will delete the associated event callback.

Note that each event type can only have one associated callback. Setting a new value will overwrite any existing one.

### Request Example
```javascript
// Setting an onComplete callback
myAnimation.eventCallback("onComplete", myFunction, ["param1", "param2"]);

// Deleting an onUpdate callback
myAnimation.eventCallback("onUpdate", null);

// Getting the current onStart callback
let currentStartCallback = myAnimation.eventCallback("onStart");

// Chaining multiple event callbacks
myAnimation.eventCallback("onComplete", completeHandler)
           .eventCallback("onUpdate", updateHandler, ["param1"]);
```

### Response
#### Success Response (Getter)
- **callbackFunction** (Function) - The currently assigned callback function for the specified event type.

#### Success Response (Setter)
- **animationInstance** (Object) - The animation instance itself, allowing for method chaining.

#### Response Example (Getter)
```json
{
  "callbackFunction": "function() { ... }"
}
```

#### Response Example (Setter)
```json
{
  "animationInstance": "[GSAP Animation Object]"
}
```
```

--------------------------------

### GSAP v3 Timeline addPause Examples

Source: https://gsap.com/docs/v3/GSAP/Timeline/addPause%28%29

Demonstrates various ways to use the addPause method to insert pauses into a GSAP timeline. It covers pausing at specific seconds, labels, relative to labels, and with callback functions and parameters.

```javascript
timeline.addPause(2);

timeline.addPause("yourLabel");

timeline.addPause("yourLabel+=3", yourFunction);

timeline.addPause(4, yourFunction, ["param1", "param2"]);
```

--------------------------------

### Register GSAP ScrollTrigger Plugin

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This code snippet demonstrates how to register the ScrollTrigger plugin with GSAP, which is necessary before using any of its features. It's a one-time setup for your project.

```javascript
gsap.registerPlugin(ScrollTrigger)
```

--------------------------------

### eventCallback Method

Source: https://gsap.com/docs/v3/GSAP/Tween/eventCallback%28%29

The eventCallback method allows you to get or set animation event callbacks such as onComplete, onUpdate, onStart, onRepeat, and others. It can also accept parameters to be passed to the callback function.

```APIDOC
## eventCallback

### Description
Gets or sets an event callback like `"onComplete", "onUpdate", "onStart"` or or `"onRepeat"` along with any parameters that should be passed to that callback.

### Method
`eventCallback( type:String, callback:Function, params:Array )`

### Parameters
#### Path Parameters
* **type** (String) - Required - The type of event callback, like `"onComplete", "onUpdate", "onStart"` or or `"onRepeat"`. This is case-sensitive.
* **callback** (Function) - Optional - The function that should be called when the event occurs. Defaults to `null`.
* **params** (Array) - Optional - An array of parameters to pass the callback. Defaults to `null`.

### Returns
* `Function` - The current callback function if only `type` is provided (getter).
* `self` - The animation instance itself for chaining if `callback` and/or `params` are provided (setter).

### Details
This method is used to manage callbacks for animation events. You can set callbacks initially via the constructor's `vars` parameter or dynamically after the animation instance has been created using `eventCallback()`. Setting a new callback for an event type will overwrite the previous one. Use `null` for the `callback` parameter to delete an event callback.

### Request Example (Setter)
```javascript
myAnimation.eventCallback('onComplete', myFunction, ['param1', 'param2']);
```

### Request Example (Getter)
```javascript
const onUpdateCallback = myAnimation.eventCallback('onUpdate');
```

### Request Example (Deleting Callback)
```javascript
myAnimation.eventCallback('onUpdate', null);
```

### Response Example (Setter - returns instance for chaining)
```javascript
myAnimation
	.eventCallback('onComplete', completeHandler)
	.eventCallback('onUpdate', updateHandler, ['param1'])
	.play(1);
```

### Response Example (Getter - returns callback function)
```javascript
// Assuming an onUpdate callback was previously set
const currentUpdateHandler = myAnimation.eventCallback('onUpdate');
console.log(currentUpdateHandler); // Outputs the function reference
```
```

--------------------------------

### GSAP SnapPlugin: Snap to Array Values

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/Snap

This example shows how to configure the SnapPlugin to snap a tween property to the closest value present in a provided array. The plugin modifies the property's value dynamically during the tween. GSAP core is the only dependency.

```javascript
gsap.to(".class", {
  x: 1000,
  snap: {
    x: [0, 50, 150, 500], // x snaps to the closest value in this array
  },
});
```

--------------------------------

### Create Stepped Animation with GSAP

Source: https://gsap.com/docs/v3/Eases/SteppedEase

This example demonstrates how to use the SteppedEase to create an animation with a defined number of steps. It requires the GreenSock Animation Platform (GSAP) library. The input is an object with properties to animate, duration, target values, and the ease function.

```javascript
gsap.to(obj, {duration: 2, x: 100, ease: "steps(5)"});
```

--------------------------------

### Create GSAP Observer for Mouse Wheel and Touch Gestures

Source: https://gsap.com/docs/v3/Plugins/Observer

Demonstrates the minimal usage of the Observer plugin to create an observer instance. It targets the window and listens for 'wheel' and 'touch' events, triggering 'previous()' on 'onUp' and 'next()' on 'onDown'. This is useful for implementing scroll-like navigation.

```javascript
Observer.create({
  target: window, // can be any element (selector text is fine)
  type: "wheel,touch", // comma-delimited list of what to listen for
  onUp: () => previous(),
  onDown: () => next()
});
```

--------------------------------

### Align Element to Motion Path using Direct Element Reference

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example shows aligning the animated element to a motion path by providing a direct reference to the path's DOM element. This offers more control when the element is already referenced in your code.

```javascript
align: myPathElementReference
```

--------------------------------

### Define Motion Path using Direct Element Reference

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example demonstrates defining the motion path by providing a direct reference to an SVG path DOM element. This approach is useful when you already have a reference to the element in your JavaScript.

```javascript
let myPath = document.querySelector("#pathID");
...
motionPath: {
  path: myPath
}
```

--------------------------------

### Reverse Animation

Source: https://gsap.com/docs/v3/GSAP/Timeline/reverse%28%29

Reverses the playback of an animation. You can specify a starting point for the reverse playback and control whether events are suppressed during the initial jump.

```APIDOC
## POST /websites/gsap_v3/reverse

### Description
Reverses the playback of a GSAP animation. This method allows you to control the direction of animation playback, including the orientation of tweens and their eases. It also affects the animation's `time` and `totalTime` properties, moving them towards zero.

### Method
POST

### Endpoint
`/websites/gsap_v3/reverse`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **from** (*): Optional - The time or label from which to begin playing in reverse. Defaults to the current playhead position. Use `0` to start from the end. Negative values are relative to the end.
- **suppressEvents** (Boolean): Optional - If `true` (default), events and callbacks are suppressed during the initial move to the `from` position. Set to `false` to trigger events.

### Request Example
```json
{
  "from": 2,
  "suppressEvents": false
}
```

### Response
#### Success Response (200)
- **self** (*): Returns the animation instance itself, enabling method chaining.

#### Response Example
```json
{
  "self": "[Animation Instance]"
}
```

### Details
The `reverse()` method is crucial for creating dynamic animations. By default, it reverses playback from the current playhead position without triggering intermediate events. You can specify a precise starting point using the `from` parameter, which can be a numerical time value or a label for timeline instances. Setting `from` to `0` will initiate reverse playback from the very end of the animation. Negative values for `from` indicate a time relative to the animation's end. The `suppressEvents` parameter offers fine-grained control over callback execution during the initial repositioning of the playhead before reverse playback begins. To check if an animation is currently in reverse mode, use the `reversed()` method.
```

--------------------------------

### Define Motion Path using Array of Property Values

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example shows how to define a motion path by providing an array of objects, where each object specifies property values (e.g., scale, rotation) to animate through. GSAP will smooth the velocity changes between these values.

```javascript
motionPath: {
  path: [{scale:0.5, rotation:10}, {scale:1, rotation:-10}, {scale:0.8, rotation:3}]
}
```

--------------------------------

### InertiaPlugin End Value Examples

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

Illustrates different ways to define the 'end' property in InertiaPlugin for precise control over where a tween stops. This includes setting a fixed number, an array of snap-to values, or a custom function for complex logic.

```javascript
// Exact end value
end: 100,

// Snap-to values (closest value in the array will be used)
end: [0, 100, 200, 300],

// Custom function for snapping to 10-degree increments
end: function(naturalValue) {
  return Math.round(naturalValue / 10) * 10;
}
```

--------------------------------

### Create GSAP Observer Instance

Source: https://gsap.com/docs/v3/Plugins/Observer

Creates a new Observer instance based on the provided configuration object. This is the primary method for initializing an Observer with specific settings.

```javascript
const observer = Observer.create(vars);
```

--------------------------------

### Kill Animation by Target - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/kill%28%29

This example shows how to use the kill() method to stop animations associated with a specific target object. If the tween has multiple targets, only those specified will be affected.

```javascript
// kill all parts of the animation related to the target "myObject" (if the tween has multiple targets, the others will not be affected):
animation.kill(myObject);
```

--------------------------------

### MorphSVG Configuration with Map Property

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Shows how to configure MorphSVG using the 'map' property to control how segments are matched between the start and end shapes. Options include 'size', 'position', and 'complexity', allowing for customized morphing behavior.

```javascript
gsap.to("#id", {
  duration: 1,
  morphSVG: { shape: "#otherID", map: "complexity" },
});
```

--------------------------------

### startTime Method (Getter/Setter)

Source: https://gsap.com/docs/v3/GSAP/Timeline/startTime%28%29

The startTime method allows you to retrieve or set the specific time an animation begins on its parent timeline. This is useful for precise control over animation sequencing and timing.

```APIDOC
## startTime

### Description
Gets or sets the time at which the animation begins on its parent timeline (after any delay that was defined).

### Method
GET/SET

### Endpoint
N/A (This is a method of a GSAP object, not a REST endpoint)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Getter: Get the current start time
var currentTime = animation.startTime();

// Setter: Set the start time to 2 seconds
animation.startTime(2);
```

### Response
#### Success Response (Getter)
- **startTime** (Number) - The current start time of the animation on its parent timeline.

#### Success Response (Setter)
- **self** (Object) - The GSAP animation instance itself, allowing for chaining.

#### Response Example (Getter)
```json
{
  "startTime": 1.5
}
```

#### Response Example (Setter)
```json
{
  "animationInstance": "[GSAP Animation Object]"
}
```

### Details
Gets or sets the time at which the animation begins on its parent timeline (after any `delay` that was defined). For example, if a tween starts at exactly 3 seconds into the timeline on which it is placed, the tween's `startTime` would be 3. The `startTime` may be automatically adjusted to make the timing appear seamless if the parent timeline's `smoothChildTiming` property is `true` and a timing-dependent change is made on-the-fly, like `reverse()` is called or `timeScale()` is changed, etc. See the documentation for the [`smoothChildTiming`](/docs/v3/GSAP/Timeline/smoothChildTiming.md) property of timelines for more details. This method serves as both a getter and setter. Omitting the parameter returns the current value (getter), whereas defining the parameter sets the value (setter) and returns the instance itself for easier chaining.
```

--------------------------------

### Absolute Time Positioning in GSAP v3 Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

Inserts a function call at a specific absolute time (in seconds) from the start of the timeline. This is a fundamental method for sequencing animations.

```javascript
tl.call(myFunction, null, 3);
```

--------------------------------

### Add Pause at Absolute Time (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/addPause%28%29

Inserts a pause exactly at a specified number of seconds from the start of the timeline. This is a straightforward method for precise timing.

```javascript
tl.addPause(3);
```

--------------------------------

### GSAP SnapPlugin: Snap to Closest Whole Number

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/Snap

This example demonstrates how to use the SnapPlugin to snap specific tween properties to the closest whole number. It targets properties listed in a comma-delimited string. No external dependencies are required beyond GSAP core.

```javascript
gsap.to(".class", {
  x: 1000,
  y: 250,
  snap: "x,y",
});
```

--------------------------------

### GSAP Timeline Initialization with Timing and Repeat Options (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Illustrates the initialization of a GSAP v3 timeline with timing-related properties such as initial delay, repeat count, repeat delay, and pause state. It also includes `autoRemoveChildren` and `smoothChildTiming` for managing child animations.

```javascript
const myTimeline = gsap.timeline({
  delay: 1,
  repeat: 2,
  repeatDelay: 0.5,
  paused: true,
  autoRemoveChildren: true,
  smoothChildTiming: true
});
```

--------------------------------

### reversed() Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/reversed%28%29

This method allows you to get or set the reversed state of a GSAP animation. When set, it determines if the animation should play backwards. It functions as both a getter and a setter.

```APIDOC
## reversed()

### Description
Gets or sets the animation's reversed state, indicating whether or not the animation should be played backwards. This value is not affected by `yoyo` repeats and it does not take into account the reversed state of ancestor timelines.

### Method
GET / SET

### Endpoint
Not applicable (method of an animation instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Gets current reversed state
var isReversed = animationInstance.reversed();

// Sets the animation to be reversed
animationInstance.reversed(true);

// Toggles the reversed state
animationInstance.reversed(!animationInstance.reversed());
```

### Response
#### Success Response (Getter)
- **reversedState** (Boolean) - The current reversed state of the animation.

#### Success Response (Setter)
- **self** (Object) - The animation instance itself, for chaining.

#### Response Example (Getter)
```json
{
  "reversedState": false
}
```

#### Response Example (Setter)
```json
{
  "message": "Instance returned for chaining"
}
```
```

--------------------------------

### GSAP Timeline: Relative Positioning with '<' and '>' Prefixes

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

Positions a set() tween relative to the start ('<') or end ('>') of the previous animation. Numbers following '<' or '>' are interpreted as relative offsets in seconds or percentages.

```javascript
// 3 seconds past the start of the previous animation
tl.set(".class", { x: 100 }, "<+=3");

// Same as "<+=3" (implied '+=')
tl.set(".class", { x: 100 }, "<3");

// 0.5 seconds before the end of the previous animation
tl.set(".class", { x: 100 }, ">-0.5");

// 25% into the previous animation (from its start)
tl.set(".class", { x: 100 }, "<25%");

// 25% of the inserting animation's duration past the start of the previous animation
tl.set(".class", { x: 100 }, "<+=25%");

// Same as ">-75%" (negative 75% from the end of the previous animation)
tl.set(".class", { x: 100 }, ">-75%");
```

--------------------------------

### reversed()

Source: https://gsap.com/docs/v3/GSAP/Tween

Gets or sets the animation's reversed state, indicating whether the animation should play backwards. This allows for checking and setting the animation's direction.

```APIDOC
## POST /docs/v3/GSAP/Tween/reversed().md

### Description
Gets or sets the animation's reversed state.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/reversed().md

### Parameters
#### Path Parameters
- **value** (Boolean) - Required - The reversed state.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Boolean | self** (Boolean | self) - Returns the reversed state or self.

#### Response Example
N/A
```

--------------------------------

### Progress API

Source: https://gsap.com/docs/v3/GSAP/Timeline/progress%28%29

The `progress()` method in GSAP v3 allows you to get or set the current progress of a timeline. Progress is represented as a value between 0 and 1, indicating the position of the virtual playhead.

```APIDOC
## GET/SET progress

### Description
Gets or sets the timeline's progress, a value between 0 and 1 indicating the position of the virtual playhead (excluding repeats). 0 is the beginning, 0.5 is halfway, and 1 is complete.

### Method
GET/SET

### Endpoint
`tl.progress()` or `tl.progress(value, suppressEvents)`

### Parameters
#### Query Parameters
- **value** (Number) - Optional - The progress value to set (between 0 and 1). If omitted, the current progress is returned.
- **suppressEvents** (Boolean) - Optional - If `true`, no events or callbacks will be triggered when the playhead moves to the new position. Defaults to `false`.

### Request Example
```javascript
// Gets current progress
var currentProgress = tl.progress();

// Sets progress to one quarter finished and suppresses events
tl.progress(0.25, true);

// Sets progress to halfway and triggers events
tl.progress(0.5);
```

### Response
#### Success Response (200)
- **Number** - The current progress value if used as a getter.
- **self** (Object) - The timeline instance itself if used as a setter, allowing for chaining.

#### Response Example
```json
// Getter example
{
  "progress": 0.75
}

// Setter example (returns the instance for chaining)
{
  "instance": tl
}
```

### Details
If the timeline has a non-zero `repeat` defined, `progress` and `totalProgress` will differ. `progress` excludes repeats and `repeatDelays`, while `totalProgress` includes them. For example, if a timeline repeats once, `totalProgress` will be 0.5 at the end of the first cycle, while `progress` will be 1. This method serves as both a getter and setter. Omitting the parameter returns the current value (getter), whereas defining the parameter sets the value (setter) and returns the instance itself for easier chaining, like `tl.progress(0.5).play();`.
```

--------------------------------

### currentLabel Getter/Setter

Source: https://gsap.com/docs/v3/GSAP/Timeline/currentLabel%28%29

The currentLabel method in GSAP v3 can be used to get the current label or set a new label. It returns the current label string when used as a getter, and the instance itself for chaining when used as a setter.

```APIDOC
## currentLabel

### Description
Gets the closest label that is at or before the current time, or jumps to a provided label. This method serves as both a getter and setter.

### Method
GET / POST (conceptual, as this is a method within a library, not a REST endpoint)

### Endpoint
`currentLabel(value?: String): String | self`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
**Getter:**
```javascript
// Assuming 'myAnimation' is a GSAP animation object
let currentLabel = myAnimation.currentLabel(); 
```

**Setter:**
```javascript
// Assuming 'myAnimation' is a GSAP animation object
myAnimation.currentLabel('myLabel'); 
```

### Response
#### Success Response (200)
- **currentLabel** (String) - The current label string when used as a getter.
- **self** (Object) - The GSAP animation instance when used as a setter, allowing for chaining.

#### Response Example
**Getter Response:**
```json
{
  "currentLabel": "someLabel"
}
```

**Setter Response:**
```json
{
  "instance": "[GSAP Animation Instance]"
}
```
```

--------------------------------

### MorphSVG Configuration with Custom Origin

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Illustrates setting a custom origin for rotational morphing in MorphSVG. This allows for more controlled and visually appealing rotations by defining specific origin points for the start and end shapes.

```javascript
gsap.to("#shape1", {
  duration: 2,
  morphSVG: {
    shape: "#shape2",
    type: "rotational",
    origin: "20% 60%", //or "20% 60%,35% 90%" if there are different values for the start and end shapes.
  },
});
```

--------------------------------

### Create and Kill GSAP DevTools Instance

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Demonstrates how to create a GSAP DevTools instance with a specific ID and then subsequently kill (destroy) that instance using its reference. This is useful for managing multiple DevTools instances or cleaning up resources.

```javascript
GSDevTools.create({id:"main"})
```

```javascript
GSDevTools.getById("main").kill()
```

--------------------------------

### Get Velocity of Draggable Element with InertiaPlugin

Source: https://gsap.com/docs/v3/Plugins/Draggable

Demonstrates how to retrieve the velocity of a Draggable element after it has been released, provided InertiaPlugin is loaded and inertia is enabled. It logs the x-velocity and the duration of the tween to the console.

```javascript
Draggable.create('#movableID', {
	type: 'x,y',
	inertia: true,
	onDragEnd: function () {
		console.log(
			'x velocity is: '
				+ InertiaPlugin.getVelocity(this.target, 'x')
				+ ' and the duration is '
				+ this.tween.duration()
				+ ' seconds.'
		);
	}
});
```

--------------------------------

### JavaScript Usage Examples for Stop Overscroll

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/stopOverscroll

Demonstrates how to use the `stopOverscroll` function. It shows the basic call to disable overscroll globally and how to target a specific element using a CSS selector.

```javascript
stopOverscroll();

// or specify an element
stopOverscroll("#viewport");
```

--------------------------------

### Handling Framework Rendering with Flip

Source: https://gsap.com/docs/v3/Plugins/Flip

Provides strategies for integrating GSAP Flip animations with JavaScript frameworks like React, Vue, or Angular. It addresses the asynchronous nature of framework rendering and suggests solutions using `requestAnimationFrame` or `useLayoutEffect`.

```javascript
// Using requestAnimationFrame to wait for the next render cycle
requestAnimationFrame(() => {
  Flip.from(state, {
    targets: ".your-class",
    duration: 1,
    ease: "power1.inOut"
  });
});

// Example for React's useLayoutEffect (conceptual)
/*
import React, { useLayoutEffect, useRef } from 'react';
import { gsap } from 'gsap';
import { Flip } from 'gsap/Flip';
gsap.registerPlugin(Flip);

function MyComponent() {
  const elementRef = useRef(null);

  useLayoutEffect(() => {
    const state = Flip.getState(elementRef.current);
    // Perform DOM updates or state changes that trigger re-render
    // ...
    Flip.from(state, {
      targets: elementRef.current,
      duration: 1,
      ease: "power1.inOut"
    });
  }, [/* dependencies */]);

  return <div ref={elementRef}>...</div>;
}
*/
```

--------------------------------

### Set Align Origin for Centering

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This example shows how to set the `alignOrigin` property to `[0.5, 0.5]`, which centers the target element on the motion path. This is often used in conjunction with `align` to precisely position elements.

```javascript
alignOrigin: [0.5, 0.5]
```

--------------------------------

### Add Animation to Timeline (Absolute Time)

Source: https://gsap.com/docs/v3/GSAP/Timeline/add%28%29

Adds an animation to a GSAP timeline at a specific time in seconds from the start of the timeline. This is useful for precise sequencing of animations.

```javascript
tl.add(animation, 3);
```

--------------------------------

### Get ScrollSmoother Wrapper Element (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/wrapper%28%29

Retrieves the current wrapper element associated with the ScrollSmoother instance. This is useful for inspecting or manipulating the scroll container.

```javascript
let wrapper = smoother.wrapper();
```

--------------------------------

### Draggable Event Callbacks

Source: https://gsap.com/docs/v3/Plugins/Observer/static

This section details the various callback functions that can be configured for the Draggable plugin to respond to user interactions like dragging and hovering.

```APIDOC
## Draggable Plugin Event Callbacks

### Description

This documentation describes the event callback functions provided by the GSAP v3 Draggable plugin. These functions allow developers to execute custom logic in response to specific user interactions with a draggable element.

### Method

N/A (These are configuration options for the Draggable plugin)

### Endpoint

N/A (These are configuration options for the Draggable plugin)

### Parameters

#### onDragStart
- **type**: Function
- **description**: Function to call when the user presses down on the target and then begins dragging (subject to `dragMinimum`). This only applies to "touch" and/or "pointer" types.

#### onDrag
- **type**: Function
- **description**: Function to call when the user moves the pointer/touch/mouse **while pressing** on the target element (only applies to "touch" and/or "pointer" types).

#### onDragEnd
- **type**: Function
- **description**: Function to call when the user stops dragging on the target element (only applies to "touch" and/or "pointer" types).

#### onLeft
- **type**: Function
- **description**: Function to call when motion is detected toward the left direction.

#### onLockAxis
- **type**: Function
- **description**: Function to call when the axis gets locked (requires `lockAxis: true`). You can check which axis via the Observer's `axis` property ("x" or "y").

#### onHover
- **type**: Function
- **description**: Function to call when the pointer/mouse hovers over the target ("pointerenter"/"mouseenter" event).

#### onHoverEnd
- **type**: Function
- **description**: Function to call when the pointer/mouse moves off the target ("pointerleave"/"mouseleave" event).

### Request Example

```javascript
Draggable.create("#myElement", {
  onDragStart: function() {
    console.log("Drag started!");
  },
  onDrag: function() {
    console.log("Dragging...");
  },
  onDragEnd: function() {
    console.log("Drag ended!");
  },
  onLeft: function() {
    console.log("Moved left");
  },
  lockAxis: true,
  onLockAxis: function(observer, axis) {
    console.log(`Axis locked to: ${axis}`);
  },
  onHover: function() {
    console.log("Hovering!");
  },
  onHoverEnd: function() {
    console.log("Hover ended!");
  }
});
```

### Response

#### Success Response (N/A)

These are callback functions, not API endpoints that return data. The success of these callbacks is determined by the custom logic implemented within them.

#### Response Example

N/A
```

--------------------------------

### Get All GSAP Observer Instances

Source: https://gsap.com/docs/v3/Plugins/Observer

Retrieves an array containing all Observer instances that have been created and not yet killed. This is useful for managing multiple observers, especially in framework scenarios requiring cleanup.

```javascript
const allObservers = Observer.getAll();
```

--------------------------------

### SplitText Configuration Properties

Source: https://gsap.com/docs/v3/Plugins/SplitText

This section details the various properties that can be passed to the SplitText constructor to customize its behavior.

```APIDOC
## **Config Object**

### Description
Configuration options for the SplitText constructor.

### Method
`SplitText.create(target, config)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
* **aria** (string) - Optional - Controls accessibility attributes. Options: "auto" (default), "hidden", "none".
* **autoSplit** (boolean) - Optional - If true, SplitText will re-split when fonts load or element width changes and lines are split. Default: `false`.
* **charsClass** (string) - Optional - CSS class applied to each character element. Can use `++` for auto-incrementing classes.
* **deepSlice** (boolean) - Optional - If true, nested elements spanning multiple lines will be subdivided. Effective only for `lines` type. Default: `true`.
* **ignore** (string | Element | Array<Element>) - Optional - Descendant elements to ignore during splitting.
* **linesClass** (string) - Optional - CSS class applied to each line element. Can use `++` for auto-incrementing classes.
* **mask** ("lines" | "words" | "chars") - Optional - Wraps elements in a `visibility: clip` element for reveal effects. Cannot mask multiple types.
* **onRevert** (Function) - Optional - Callback function executed when the SplitText instance reverts.
* **onSplit** (Function) - Optional - Callback function executed after the text is split.

### Request Example
```javascript
SplitText.create(".split", {
  type: "lines",
  autoSplit: true,
  onSplit: (self) => {
    return gsap.from(self.lines, {
      y: 100,
      opacity: 0,
      stagger: 0.05
    });
  }
});
```

### Response
#### Success Response (200)
SplitText instance with configured properties.

#### Response Example
```json
{
  "instance": "SplitText"
}
```
```

--------------------------------

### Link Animation to Element Visibility (ScrollTrigger)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This example demonstrates how to link a GSAP animation to a specific HTML element, ensuring the animation only plays when that element is within the viewport. This improves performance and guarantees animations are seen by the user.

```javascript
gsap.to("#myElement", {
  scrollTrigger: "#myElement", // Triggers when #myElement is in view
  x: 500,
  duration: 2
});
```

--------------------------------

### GSAP Timeline: Insert set() at Absolute Time

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

Inserts a set() tween at a specific absolute time (in seconds) from the start of the GSAP timeline. This is useful for precise timing of initial states.

```javascript
tl.set(".class", { x: 100 }, 3);
```

--------------------------------

### totalProgress Method

Source: https://gsap.com/docs/v3/GSAP/Tween/totalProgress%28%29

This method allows you to get or set the total progress of a GSAP tween. The progress is a value between 0 and 1, indicating the position of the playhead, including repeats.

```APIDOC
## totalProgress

### Description
Gets or sets the tween's totalProgress, a value between 0 and 1 indicating the position of the virtual playhead (including repeats).

### Method
Getter/Setter

### Endpoint
N/A (This is a method of a GSAP tween instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### **value** (Number) - Optional
If provided, sets the total progress of the tween. If omitted, it returns the current total progress.

#### **suppressEvents** (Boolean) - Optional
If `true`, no events or callbacks will be triggered when the playhead moves to the new position. Defaults to `false`.

### Request Example
```javascript
// Get current total progress
var progress = myTween.totalProgress();

// Set total progress to one quarter finished
myTween.totalProgress(0.25);

// Set total progress and suppress events
myTween.totalProgress(0.5, true);
```

### Response
#### Success Response (Getter)
- **totalProgress** (Number) - The current total progress of the tween (0 to 1).

#### Success Response (Setter)
- **instance** (Object) - The tween instance itself, for chaining.

#### Response Example (Getter)
```json
{
  "totalProgress": 0.75
}
```

#### Response Example (Setter)
```json
{
  "message": "Tween instance returned for chaining"
}
```
```

--------------------------------

### Configurable Draggable Element with Bounds and Callbacks (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/Draggable

Configures a draggable element with specific options including vertical-only movement, bounds, inertia, and custom callbacks for click and drag end events. This example requires the Draggable plugin and optionally InertiaPlugin for momentum-based motion.

```javascript
Draggable.create('#yourID', {
	type: 'y',
	bounds: document.getElementById('container'),
	inertia: true,
	onClick: function () {
		console.log('clicked');
	},
	onDragEnd: function () {
		console.log('drag ended');
	}
});
```

--------------------------------

### Apply GSAP distribute directly in a tween

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/distribute%28%29

This example shows how to use `gsap.utils.distribute` directly within a GSAP tween to animate properties like 'scale'. It configures the distribution to set a base scale for middle elements and a different scale for outer elements, creating a staggered visual effect.

```javascript
gsap.to(".class", {
  scale: gsap.utils.distribute({
    base: 0.5,
    amount: 2.5,
    from: "center",
  }),
});
```

--------------------------------

### Flip.batch

Source: https://gsap.com/docs/v3/Plugins/Flip

Coordinates the creation of multiple Flip animations in a properly sequenced set of steps to avoid cross-contamination.

```APIDOC
## POST /websites/gsap_v3/plugins/flip/batch

### Description
Coordinates the creation of multiple Flip animations in the properly sequenced set of steps to avoid cross-contamination.

### Method
POST

### Endpoint
/websites/gsap_v3/plugins/flip/batch

### Parameters
#### Path Parameters
- **id** (String) - Required - A unique identifier for the batch operation.

#### Query Parameters
None

#### Request Body
None

### Request Example
```json
{
  "message": "This endpoint does not have a request body, but requires an ID in the path."
}
```

### Response
#### Success Response (200)
- **FlipBatch** (Object) - An object representing the batch of Flip animations.

#### Response Example
```json
{
  "message": "Flip batch created successfully."
}
```
```

--------------------------------

### Progress API

Source: https://gsap.com/docs/v3/GSAP/Tween/progress%28%29

The progress() method allows you to get the current progress of a tween (a value between 0 and 1) or set a new progress value. It can also suppress events and callbacks.

```APIDOC
## GET/SET progress

### Description
Gets or sets the tween's progress, a value between 0 and 1 indicating the position of the virtual playhead. This method can also suppress events.

### Method
GET/SET

### Endpoint
N/A (Method on a Tween instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters (Method Arguments)
#### `value` (Number) - Optional
- If omitted, returns the current progress (getter).
- If provided, sets the tween's progress to this value (setter).

#### `suppressEvents` (Boolean) - Optional
- If `true`, no events or callbacks will be triggered when the playhead moves to the new position.
- Defaults to `false`.

### Request Example
```javascript
// Gets current progress
var currentProgress = myTween.progress();

// Sets progress to one quarter finished
myTween.progress(0.25);

// Sets progress and suppresses events
myTween.progress(0.75, true);
```

### Response
#### Success Response
- **progress** (Number | self) - If used as a getter, returns the current progress value (Number). If used as a setter, returns the tween instance itself for chaining (`self`).

#### Response Example
```json
// Getter example response
0.5

// Setter example response (returns the tween instance)
{
  "__gsType": "Tween"
}
```

### Details
- `progress` represents the position within the current cycle, excluding repeats and repeatDelays.
- `totalProgress` includes repeats and repeatDelays.
- Use this method for precise control over the tween's animation state.
- For eased values, refer to the `ratio` property.
```

--------------------------------

### GSAP Tween Minimal Usage

Source: https://gsap.com/docs/v3/GSAP/Tween

Demonstrates the most basic usage of GSAP's tween functionality to animate properties of elements. It requires the GSAP library to be loaded. This example animates rotation and x-translation of elements with the class 'box' over 1 second.

```javascript
gsap.to(".box", { rotation: 27, x: 100, duration: 1 });
```

--------------------------------

### Preserving Spaces in Text Animation

Source: https://gsap.com/docs/v3/Plugins/TextPlugin

Ensures that extra spaces in the text are maintained during animation by setting 'preserveSpaces: true'. GSAP will use non-breaking space characters (`&nbsp;`) to render these spaces correctly in HTML.

```javascript
gsap.to(yourElement, {
  duration: 1,
  text: {
    value: "Your new text with   extra spaces",
    preserveSpaces: true
  }
});
```

--------------------------------

### ScrollSmoother .paused() Method

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/paused%28%29

This method allows you to get or set the paused state of the ScrollSmoother instance. When paused, scrolling is halted, and user interaction with the scrollbar is prevented.

```APIDOC
## .paused()

### Description
Gets or sets the paused state of the ScrollSmoother instance. If `true`, scrolling will immediately stop and user interaction with the scrollbar will be prevented. If `false`, scrolling will resume. This method can also be used to retrieve the current paused state.

### Method
GET / POST

### Endpoint
N/A (Instance method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
##### pause (Boolean) - Optional
If `true`, the instance will be paused. If `false`, the instance will be resumed. If omitted, the current paused state will be returned.

### Request Example
```javascript
// Setter: Pause the instance
smoother.paused(true);

// Setter: Resume the instance
smoother.paused(false);

// Getter: Get the current paused state
let isPaused = smoother.paused(); 
```

### Response
#### Success Response (200)
- **Boolean**: Returns `true` if the instance is currently paused, `false` otherwise.

#### Response Example
```json
// Example of getter response
true
```
```

--------------------------------

### Observer Configuration Properties

Source: https://gsap.com/docs/v3/Plugins/Observer

This section details the various properties that can be included in the configuration object when creating a new Observer instance using `Observer.create()`.

```APIDOC
## **Config Object**

The configuration object that is passed to `Observer.create()` can have any of the following optional properties:

### Property

### Description

#### axis

string - when `lockAxis: true` is set, the first drag movement (with type: "pointer" and/or "touch") after each press will set the `axis` property to "x" or "y", depending on which direction the user moved. You can use the `onLockAxis()` callback to know when it gets set.

#### capture

Boolean - if `true`, it will make the touch/pointer-related listeners use the capture phase. Like doing addEventListener("[type]", func, {capture: true});

#### debounce

Boolean - by default, Observer will debounce events so that deltas are additive over the course of each requestAnimationFrame() tick in order to maximize performance, but you can disable that with `debounce: false` in which case it will check immediately on every event. The debounce affects all callbacks except `onPress`, `onRelease`, `onHover`, `onHoverEnd`, `onClick`, `onDragStart`, and `onDragEnd` because those aren't delta-related.

#### dragMinimum

Number - the minimum distance (in pixels) necessary to be considered "dragging". This can help prevent tiny motions especially on touch devices from indicating intent. For example, just pressing down with a finger on a phone may register slight movement of a few pixels even though the user thinks their finger was stationary. dragMinimum only applies to the initial movement after pressing down, but continued dragging thereafter would only be subject to "tolerance" throttling.

#### id

String - an arbitrary string ID which an be used to get the Observer via [Observer.getById()](/docs/v3/Plugins/Observer/static.getById().md).

#### ignore

Element | String | Array - elements that you'd like the observer to **IGNORE**, so that when a scroll/touch/pointer/mouse event is triggered by one of these elements, it gets ignored completely. It checks the `event.target` to discern if the event should be ignored. You can define `ignore` as an Element reference, selector text like `".ignore-me"`, or an Array of elements (it can be as many as you'd like).

#### lockAxis

Boolean - if `true`, the Observer will watch the direction of the very first drag move after each press (with type: "pointer" and/or "touch") and lock into that direction until the user releases the pointer/touch. So if the first drag is horizontal, then only the horizontal-related callbacks like `onChangeX()` will fire until the pointer/touch is released. There's even an `onLockAxis()` callback that you can tie into.

#### onChange

Function - function to call when there is movement on **either** the y-axis (vertically) **or** the x-axis (horizontally). It will keep calling the function as long as the movement continues (subject to any tolerance threshold).

#### onChangeX

Function - function to call when there is movement on the x-axis (horizontally). It will keep calling the function as long as the movement continues (subject to any tolerance threshold).

#### onChangeY

Function - function to call when there is movement on the y-axis (vertically). It will keep calling the function as long as the movement continues (subject to any tolerance threshold).

#### onClick

Function - function to call when the target is clicked.

#### onDown

Function - function to call when downward motion is detected, meaning the delta values increase (like dragging your finger/mouse DOWNWARD...which makes the `y` coordinate *increase*). If you want to invert only the mouse wheel delta, you can set `wheelSpeed: -1` because it's a multiplier.

#### onDragStart

Function - function to call when the user presses down on the target and then begins dragging (subject to `dragMinimum`). This only applies to "touch" and/or "pointer" types.

#### onDrag

Function - function to call when the user moves the pointer/touch/mouse **while pressing** on the target element (only applies to "touch" and/or "pointer" types).

#### onDragEnd

Function - function to call when the user stops dragging on the target element (only applies to "touch" and/or "pointer" types).

#### onLeft

Function - function to call when motion is detected toward the left direction.

#### onLockAxis

Function - function to call when the axis gets locked (requires `lockAxis: true`). You can check which axis via the Observer's `axis` property ("x" or "y").

#### onHover

Function - function to call when the pointer/mouse hovers over the target ("pointerenter"/"mouseenter" event).

#### onHoverEnd

Function - function to call when the pointer/mouse stops hovering over the target ("pointerleave"/"mouseleave" event).
```

--------------------------------

### totalDuration Method

Source: https://gsap.com/docs/v3/GSAP/Tween/totalDuration%28%29

The totalDuration method in GSAP v3 allows you to get or set the total duration of a tween, including any repeats and repeat delays. It functions as both a getter and a setter.

```APIDOC
## totalDuration

### Description
Gets or sets the total duration of the tween in seconds, including any repeats or repeatDelays. This is different from `duration`, which does not include repeats and repeatDelays.

### Method
Getter/Setter

### Endpoint
N/A (This is a method of a GSAP tween instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters (Setter)
#### value (Number)
- **value** (Number) - Optional - The new total duration to set for the tween. If omitted, the current total duration is returned.

### Request Example (Getter)
```javascript
// Gets the total duration of the tween
var currentTotalDuration = myTween.totalDuration();
```

### Request Example (Setter)
```javascript
// Sets the total duration of the tween to 10 seconds
myTween.totalDuration(10);
```

### Response
#### Success Response (Getter)
- **Number** - The current total duration of the tween in seconds.

#### Success Response (Setter)
- **self** - The tween instance itself, allowing for chaining.

#### Response Example (Getter)
```json
15.5
```

#### Response Example (Setter)
```json
[TweenInstance]
```

### Details
If a tween has a `duration` of 10, a `repeat` of 1, and a `repeatDelay` of 2, its `totalDuration` would be 22 (10 + (10 * 1) + (2 * 1)). The `totalDuration` method provides a way to access or modify this comprehensive duration value. When used as a setter, it returns the tween instance, facilitating method chaining.
```

--------------------------------

### GSAP Flip Plugin: Spin Animation with Function

Source: https://gsap.com/docs/v3/Plugins/Flip/static

Demonstrates how to use a function to control the spin animation for individual targets in GSAP's Flip plugin. This allows for dynamic spin directions or no spin based on element properties.

```javascript
Flip.from(state, {
  spin: (index, target) => {
    if (target.classList.contains("clockwise")) {
      return 1;
    } else if (target.classList.contains("counter-clockwise")) {
      return -1;
    } else {
      return 0;
    }
  }
});
```

--------------------------------

### GSAP wrap: Cycle Array Values

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/wrap%28%29

Demonstrates how to use gsap.utils.wrap to get a value from an array, cycling back to the beginning when the index exceeds the array length. If no index is provided, it returns a function that can be called with an index.

```javascript
let color = gsap.utils.wrap(["red", "green", "yellow"], 5); // "yellow"

let wrapper = gsap.utils.wrap(["red", "green", "yellow"]);
let color = wrapper(5) // "yellow"
```

--------------------------------

### SplitText.create

Source: https://gsap.com/docs/v3/Plugins/SplitText/static

Creates and returns a standalone SplitText instance with specified configuration.

```APIDOC
## SplitText.create

### Description
Creates and returns a standalone SplitText instance.

### Method
`SplitText.create`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
* **target** (Element | String | Array) - Required - The element(s) or selector to split.
* **vars**: Object - Optional - An object containing all of the configuration details for the SplitText.
  * **type**: String - Optional - Defines the types of elements to split into (e.g., "chars,words,lines"). Defaults to "chars,words".
  * **linesClass**: String - Optional - CSS class to add to each line element.
  * **wordsClass**: String - Optional - CSS class to add to each word element.
  * **autoSplit**: Boolean - Optional - If true, the text will be split automatically when the instance is created.
  * **onSplit**: Function - Optional - A callback function that runs after the text has been split.

### Request Example
```javascript
SplitText.create(".headline", {
  type: "lines,words",
  linesClass: "line",
  wordsClass: "word++",
  autoSplit: true,
  onSplit: (self) => {
    return gsap.from(self.lines, {
      yPercent: 100,
      opacity: 0,
      stagger: 0.1
    });
  }
});
```

### Response
#### Success Response (200)
* **SplitText instance** (SplitText) - The newly created SplitText instance.

#### Response Example
```json
{
  "instance": "[SplitText instance object]"
}
```
```

--------------------------------

### Customized ScrambleText Animation

Source: https://gsap.com/docs/v3/Plugins/ScrambleTextPlugin

Provides an example of customizing the ScrambleText animation using a configuration object. This allows control over text content, characters used for scrambling, reveal delay, speed, and CSS classes for new/old text.

```javascript
gsap.to(element, {
  duration: 1,
  scrambleText: {
    text: "THIS IS NEW TEXT",
    chars: "XO",
    revealDelay: 0.5,
    speed: 0.3,
    newClass: "myClass"
  }
});
```

--------------------------------

### Alternate Aria Strategy for Nested Elements (HTML)

Source: https://gsap.com/docs/v3/Plugins/SplitText

Illustrates an alternative approach for complex nested text where the default aria setting might not preserve semantics. This example shows a link within split text that may not be recognized by screen readers, highlighting the need for custom solutions.

```html
<h2 aria-label="This link isn't accessible">
  <div aria-hidden="true">This</div>
  <div aria-hidden="true"><a href="#">link</a></div>
  <div aria-hidden="true">isn't</div>
  <div aria-hidden="true">accessible</div>
</h2>
```

--------------------------------

### Get and Set Animation Time (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/time%28%29

Demonstrates how to use the time() method in GSAP v3 to retrieve the current playhead position and to set the playhead to a specific time. This method is useful for controlling animation playback and seeking to specific points.

```javascript
var currentTime = tl.time();
tl.time(2);
```

--------------------------------

### Get Content Element with GSAP ScrollSmoother v3

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/content%28%29

Retrieves the current content element managed by the ScrollSmoother instance. This is useful for inspecting or interacting with the main scrollable area.

```javascript
let content = smoother.content();
```

--------------------------------

### startY Property

Source: https://gsap.com/docs/v3/Plugins/Observer/startY

The startY property captures the clientY coordinate from the most recent touch or pointer press event, essential for implementing drag functionality.

```APIDOC
## startY

### Description
The `startY` property stores the `clientY` value from the most recent `onPress` event involving a touch or pointer. This value represents the vertical distance from the viewport's top edge.

It is updated only when the `type` configuration includes 'touch' and/or 'pointer'. This property is particularly useful for implementing drag-and-drop or other dragging-related logic.

### Method
N/A (This is a property, not an endpoint)

### Endpoint
N/A (This is a property, not an endpoint)

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (N/A)
N/A

#### Response Example
N/A
```

--------------------------------

### GSAP Flip Plugin: onEnter Callback Example

Source: https://gsap.com/docs/v3/Plugins/Flip/static

Demonstrates the usage of the `onEnter` callback in GSAP's Flip plugin. This callback is invoked when a target element enters the document flow during a flip animation. It receives an array of entering elements, allowing custom animations like fading them in. Any animation returned is added to the flip timeline.

```javascript
onEnter: elements => gsap.fromTo(elements, {opacity: 0}, {opacity: 1})
```

--------------------------------

### Get GSAP Observer Instance by ID

Source: https://gsap.com/docs/v3/Plugins/Observer

Fetches a specific Observer instance by its unique ID, which is defined in the configuration's 'vars' object. Returns undefined if no matching observer is found.

```javascript
const observerById = Observer.getById(id);
```

--------------------------------

### Create and Use a Custom Ease with SVG Path

Source: https://gsap.com/docs/v3/Eases/CustomEase

Demonstrates the minimal usage of CustomEase by creating a custom ease named 'hop' using an SVG path string and then applying it to a GSAP tween. This requires the CustomEase plugin to be registered.

```javascript
CustomEase.create(
  "hop",
  "M0,0 C0,0 0.056,0.442 0.175,0.442 0.294,0.442 0.332,0 0.332,0 0.332,0 0.414,1 0.671,1 0.991,1 1,0 1,0"
);

//now you can reference the ease by ID (as a string):
gsap.to(element, { duration: 1, y: -100, ease: "hop" });
```

--------------------------------

### GSAP v3: Pausing Animations on Creation

Source: https://gsap.com/docs/v3/GSAP/Tween

Setting the 'paused' property to true will immediately pause the animation upon its creation. This is useful when you want to control the start of an animation manually later.

```javascript
const myTween = gsap.to(".myElement", {
  x: 100,
  paused: true // Animation is created in a paused state
});

// Later, to start the animation:
// myTween.play();
```

--------------------------------

### Get and Manage All ScrollSmoother Effects

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/effects%28%29

Illustrates how to retrieve an array of all ScrollTrigger instances currently managing effects within ScrollSmoother and how to iterate through them to perform actions like killing the effects. This is useful for global control over animations.

```javascript
// returns an Array of all the ScrollTrigger instances that are managing the effects
let effects = smoother.effects(); // getter

// kill all the effects:
smoother.effects().forEach((t) => t.kill());
```

--------------------------------

### Get and Set Timeline Iteration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/iteration%28%29

Demonstrates how to retrieve the current iteration count of a GSAP timeline and how to set it to a specific iteration. This method is useful for controlling playback and state within repeated timelines.

```javascript
var tl = gsap.timeline({
  repeat: 4
});

// Gets current iteration
var currentIteration = tl.iteration();
console.log("Current iteration: " + currentIteration); // Output: Current iteration: 1

// Sets iteration to the second iteration
tl.iteration(2);
console.log("Set iteration to: " + tl.iteration()); // Output: Set iteration to: 2

// Chaining example
tl.iteration(3).play();
```

--------------------------------

### Create SplitText Instance with GSAP

Source: https://gsap.com/docs/v3/Plugins/SplitText/static

Demonstrates how to create a new SplitText instance using the SplitText.create() method. This method accepts a target element or selector and a configuration object to customize the splitting behavior, including line and word classes, and an optional callback for animations.

```javascript
SplitText.create(".headline", {
  type: "lines,words",
  linesClass: "line",
  wordsClass: "word++",
  autoSplit: true,
  onSplit: (self) => {
    return gsap.from(self.lines, {
      yPercent: 100,
      opacity: 0,
      stagger: 0.1
    });
  }
});
```

--------------------------------

### Check ScrollTrigger .isActive Status with JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/isActive

This example demonstrates how to create a ScrollTrigger instance and log its 'isActive' status to the console when toggled. It utilizes the 'onToggle' callback to access the ScrollTrigger instance and check its 'isActive' property.

```javascript
ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
  onToggle: (self) => console.log("toggled. active?", self.isActive)
});
```

--------------------------------

### Log ScrollTrigger Progress in JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/progress

This example demonstrates how to access and log the 'progress' of a ScrollTrigger instance using the onUpdate callback. It logs the progress value to the console whenever the scroll position changes within the trigger's bounds. No external dependencies are required beyond GSAP.

```javascript
ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
  onUpdate: (self) => console.log("progress:", self.progress)
});
```

--------------------------------

### iteration() - Get or Set Timeline Iteration

Source: https://gsap.com/docs/v3/GSAP/Timeline/iteration%28%29

The iteration() method allows you to retrieve the current repeat count of a timeline or set it to a specific iteration. This is useful for controlling playback and jumping to different repeat cycles.

```APIDOC
## iteration()

### Description
Gets or sets the iteration (the current repeat) of timelines. The iteration is the current repeat count of a timeline. For example, iteration is `1` the very first time through, then on the first repeat, the iteration would be `2`, then `3`, etc.

### Method
GET/SET (depending on parameter)

### Endpoint
N/A (This is a method of a GSAP timeline instance)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Gets the current iteration
var currentIteration = myTimeline.iteration();

// Sets the timeline to the second iteration
myTimeline.iteration(2);
```

### Response
#### Success Response (Getter)
- **iteration** (Number) - The current iteration count of the timeline.

#### Success Response (Setter)
- **self** (Object) - The timeline instance itself, allowing for chaining.

#### Response Example (Getter)
```json
{
  "iteration": 1
}
```

#### Response Example (Setter)
```json
{
  "message": "Timeline instance returned for chaining"
}
```

### Details
Omitting the parameter returns the current value (getter), whereas defining the parameter sets the value (setter) and returns the instance itself for easier chaining. Setting the iteration will cause the timeline to go to the iteration provided. For example, if the `repeat` is 4, and the playhead is currently on its third repeat, `.iteration(2)` will make the timeline jump back to the second iteration.
```

--------------------------------

### Chaining GSAP Timeline Methods with set()

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

Illustrates how to chain various GSAP timeline methods, including set(), from(), to(), and call(), to create complex animation sequences. The set() method is used here to immediately change the opacity of an element.

```javascript
var tl = gsap.timeline({ onComplete: myFunction });
var element = document.getElementById('myElement');

// Tween element's x from -100
tl.from(element, { duration: 1, x: -100 })

  // Then tween element's y to 50
  .to(element, { duration: 1, y: 50 })

  // Then set element's opacity to 0 immediately
  .set(element, { opacity: 0 })

  // Then call otherFunction()
  .call(otherFunction)

  // Finally tween the rotation of all elements with the class "myClass"
  .to(".myClass", { duration: 1.5, rotation: 45, stagger: 0.25 });

function myFunction() {
  console.log("Timeline complete!");
}

function otherFunction() {
  console.log("Other function called!");
}
```

--------------------------------

### GSAP v3 Relative Value Animation (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween

Animates properties relative to their current values using '+=' or '-=' prefixes. This is useful for animations where the exact starting point is unknown or needs to be dynamic.

```javascript
gsap.to(".class", {x:"-=20"}); // Animates x 20 pixels less than its current value
gsap.to(".class", {x:"+=20"}); // Animates x 20 pixels more than its current value
```

--------------------------------

### Get and Animate a Specific CSS Rule with CSSRulePlugin

Source: https://gsap.com/docs/v3/Plugins/CSSRulePlugin

Shows how to use the static `getRule()` method of CSSRulePlugin to obtain a reference to a specific CSS rule (e.g., a pseudo-element) and then tween its properties. The properties to be animated must be wrapped in a `cssRule` object.

```javascript
var rule = CSSRulePlugin.getRule(".myClass::before"); //get the rule
gsap.to(rule, { duration: 3, cssRule: { color: "blue" } });
```

--------------------------------

### Create and Use a Custom Ease with Cubic-Bezier String

Source: https://gsap.com/docs/v3/Eases/CustomEase

Illustrates how to create a custom ease using a standard CSS cubic-bezier string. The created ease can then be referenced by its assigned name in GSAP tweens. This method is useful for importing eases from tools like cubic-bezier.com.

```javascript
CustomEase.create("easeName", ".17,.67,.83,.67");
gsap.to(element, { duration: 1, x: 100, ease: "easeName" });
```

--------------------------------

### ScrollTrigger Configuration: Markers

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

The `markers` option adds visual indicators to the start and end points of a ScrollTrigger, which is useful for debugging and development. It can be enabled with a boolean `true` for default settings or customized with an object for specific styling.

```javascript
ScrollTrigger.create({
  // ... other ScrollTrigger properties
  markers: true
});

ScrollTrigger.create({
  // ... other ScrollTrigger properties
  markers: {
    startColor: "white",
    endColor: "white",
    fontSize: "18px",
    fontWeight: "bold",
    indent: 20
  }
});
```

--------------------------------

### Get and Set Tween Progress (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/progress%28%29

Demonstrates how to retrieve the current progress of a GSAP tween and how to set it to a specific value. This method is crucial for controlling playback and is often used for seeking to specific points in an animation.

```javascript
// Gets current progress
var progress = myTween.progress();

// Sets progress to one quarter finished
myTween.progress(0.25);
```

--------------------------------

### Minimal RoughEase Usage with expoScale

Source: https://gsap.com/docs/v3/Eases/RoughEase

Demonstrates a minimal usage of GSAP's RoughEase by animating the scale of an element. It shows how to specify the ease directly in the tween configuration.

```javascript
// we're starting at a scale of 1 and animating to 2, so pass those into config()...
gsap.to("#image", { duration: 1, scale: 2, ease: "expoScale(1, 2)" });
```

--------------------------------

### Visual Markers for Development (ScrollTrigger)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Enable visual markers directly within the browser during development to clearly identify the start, end, and trigger points of your ScrollTrigger animations. This aids in debugging and fine-tuning animation behavior.

```javascript
gsap.to(".someElement", {
  opacity: 0,
  scrollTrigger: {
    trigger: ".someElement",
    start: "top 50%",
    end: "bottom 50%",
    markers: {
      startColor: "rgba(0,255,0,1)",
      endColor: "rgba(255,0,0,1)",
      fontSize: "14px",
      indent: 10
    }
  }
});
```

--------------------------------

### Draggable.startDrag

Source: https://gsap.com/docs/v3/Plugins/Draggable

Forces the Draggable instance to begin the dragging process.

```APIDOC
## POST Draggable.startDrag

### Description
Forces the Draggable to begin dragging.

### Method
POST

### Endpoint
/websites/gsap_v3/Plugins/Draggable/startDrag

### Parameters
#### Query Parameters
- **event** (Object) - Required - The event object that triggered the drag.
- **align** (Boolean) - Optional - Whether to align the drag to a specific point.
```

--------------------------------

### Configure Spin Animation in GSAP Flip

Source: https://gsap.com/docs/v3/Plugins/Flip

Demonstrates how to configure the 'spin' property in GSAP's Flip plugin. The 'spin' property can accept a boolean, a number for full rotations, or a function to customize the spin for each target element based on its properties or index. This example shows a function that applies different spin directions based on CSS classes.

```javascript
Flip.from(state, {
  spin: (index, target) => {
    if (target.classList.contains("clockwise")) {
      return 1;
    } else if (target.classList.contains("counter-clockwise")) {
      return -1;
    } else {
      return 0;
    }
  },
})
```

--------------------------------

### Get and Set Animation Total Time (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/totalTime%28%29

Demonstrates how to retrieve the current total playback time of a GSAP animation and how to set it to a specific value. The setter returns the animation instance for chaining. Negative values are relative to the end of the animation.

```javascript
var currentTotalTime = tl.totalTime();

tl.totalTime(5); 

```

--------------------------------

### ScrollTrigger .vars Property

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/vars

The .vars property provides read-only access to the configuration object that was used to create the ScrollTrigger instance. This object contains all the properties passed during initialization, such as trigger, start, and end.

```APIDOC
## ScrollTrigger .vars Property

### Description

The `.vars` property is a read-only object that holds the configuration variables used to create the ScrollTrigger instance. It reflects the initial settings passed to `ScrollTrigger.create()`.

### Method

GET

### Endpoint

N/A (This is a property of an instance, not an endpoint)

### Parameters

No parameters are required to access this property.

### Request Example

```javascript
let st = ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
  // You can add custom properties here
  myCustomData: "some value"
});

// Accessing the vars object
console.log(st.vars);
// Output: {trigger: ".trigger", start: "top center", end: "+=500", myCustomData: "some value"}
```

### Response

#### Success Response (200)

- **vars** (Object) - A read-only object containing the configuration properties used to initialize the ScrollTrigger.

#### Response Example

```json
{
  "trigger": ".trigger",
  "start": "top center",
  "end": "+=500",
  "myCustomData": "some value"
}
```

### Notes

- The `vars` object can also store arbitrary data that ScrollTrigger will ignore, allowing for custom data association with an instance. This is useful for grouping or managing multiple ScrollTriggers.
```

--------------------------------

### ScrollTrigger.sort() with Default and Custom Sorting - JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/static

Demonstrates how to use ScrollTrigger.sort() with its default sorting behavior (by refreshPriority and then start value) and how to provide a custom sorting function. This is useful for managing the order of ScrollTrigger calculations to ensure correct pinning and positioning.

```javascript
ScrollTrigger.create({
  refreshPriority: -1, // lower priority makes it happen later in the refresh() calculations
  ...
});
ScrollTrigger.create({
  ... // if no refreshPriority is defined, it defaults to 0
});
gsap.to(".class", { // works with tweens/timelines too
  opacity: 1,
  scrollTrigger: {
    refreshPriority: 3, // a higher number makes it happen earlier in the refresh() calculations
    ...
  }
});

ScrollTrigger.sort(); // use the defaults (typically best)

// or use a custom function...
ScrollTrigger.sort((a, b) => a.start - b.start);
```

--------------------------------

### Create and Use a CustomWiggle Ease

Source: https://gsap.com/docs/v3/Eases/CustomWiggle

Demonstrates creating a custom wiggle ease named 'myWiggle' with 6 oscillations and then applying it to the 'rotation' property of an element using GSAP's to() method.

```javascript
//Create a wiggle with 6 oscillations (default type:"easeOut")
CustomWiggle.create("myWiggle", {wiggles: 6});

//now use it in an ease. "rotation" will wiggle to 30 and back just as much in the opposite direction, ending where it began.
gsap.to(".class", {duration: 2, rotation: 30, ease: "myWiggle"});
```

--------------------------------

### Basic Draggable Element Creation (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/Draggable

Creates a basic draggable element using GSAP's Draggable plugin. This example makes an element with the ID 'yourID' draggable both vertically and horizontally without any constraints or kinetic motion after release. It requires the Draggable plugin to be loaded.

```javascript
Draggable.create('#yourID');
```

--------------------------------

### repeatDelay Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/repeatDelay%28%29

The repeatDelay method in GSAP v3 allows you to get or set the amount of time in seconds between animation repeats. It can be used as a getter to retrieve the current delay or as a setter to define a new delay.

```APIDOC
## repeatDelay

### Description
Gets or sets the amount of time in seconds between repeats.

### Method
GET / SET

### Endpoint
N/A (This is a method of a GSAP object, not a REST endpoint)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters (Setter)
#### **value** (Number)
- Optional (default = `0`)
- The time in seconds to set as the delay between repeats.

### Request Example (Setter)
```javascript
// Sets the repeat delay to 2 seconds
tl.repeatDelay(2);
```

### Request Example (Getter)
```javascript
// Gets the current repeat delay
var currentDelay = tl.repeatDelay();
```

### Response (Getter)
#### Success Response (200)
- **repeatDelay** (Number) - The current delay in seconds between repeats.

### Response Example (Getter)
```json
{
  "repeatDelay": 1
}
```

### Details
This method serves as both a getter and setter. Omitting the parameter returns the current value (getter), whereas defining the parameter sets the value (setter) and returns the instance itself for easier chaining, like `myTimeline.repeat(2).yoyo(true).play();`

For example, if `repeat` is 2 and `repeatDelay` is 1, the timeline will play initially, then wait for 1 second before it repeats, then play again, then wait 1 second again before doing its final repeat. You can set the initial `repeatDelay` value via the `vars` parameter, like:

```javascript
var tl = gsap.timeline({
  repeat: 2,
  repeatDelay: 1
});
```
```

--------------------------------

### GSAP Timeline Sequencing Without Timelines (using delays)

Source: https://gsap.com/docs/v3/GSAP/Timeline

Illustrates how to create a sequence of animations using only the `delay` property, highlighting the complexity and maintenance issues compared to using GSAP Timelines.

```javascript
gsap.to("#id", { x: 100, duration: 1 });
gsap.to("#id", { y: 50, duration: 2, delay: 1 });
gsap.to("#id", { opacity: 0, duration: 1, delay: 3 });
```

--------------------------------

### Snapping Rotation to Increments (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/Draggable

Implements custom snapping behavior for a spinnable element, forcing the rotation to snap to 90-degree increments after release. This example uses a function within the 'snap' option to define the snapping logic. Requires Draggable and InertiaPlugin.

```javascript
Draggable.create('#yourID', {
	type: 'rotation',
	inertia: true,
	snap: function (value) {
		// This function gets called by InertiaPlugin when the mouse/finger is released and it plots where rotation
		// should normally end and we can alter that value and return a new one instead. This gives us an easy way to
		// apply custom snapping behavior with any logic we want. In this case, we'll just make sure the end value snaps
		// to 90-degree increments but only when the "snap" checkbox is selected.
		return Math.round(value / 90) * 90;
	}
});
```

--------------------------------

### Define Motion Path using Array of XY Coordinates (Curved)

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Shows how to define a motion path using an array of objects, each with 'x' and 'y' coordinates. By default, this creates a curved path passing through these points. The target's starting coordinates are automatically included.

```javascript
motionPath: [{x:100, y:50}, {x:200, y:0}, {x:300, y:100}]
```

--------------------------------

### GSAP v3: Sequencing Animations with Timeline (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/gsap

Illustrates how to create and manage animation sequences using GSAP's Timeline object. This method is recommended for complex sequences, allowing precise control over the timing and overlap of multiple tweens. It provides a more flexible alternative to using individual tween delays.

```javascript
let tl = gsap.timeline(); //create the timeline
tl.to(".class1", { x: 100 })
  .to(".class2", { y: 100, ease: "elastic" })
  .to(".class3", { rotation: 180 });
```

--------------------------------

### Create GSAP Observer Instance with Configuration

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Creates a new GSAP Observer instance using the Observer.create method. This method accepts a configuration object to define event types, targets, and callback functions for scroll-like interactions. It's useful for implementing custom scrolling or touch gestures.

```javascript
Observer.create({
  target: window, // can be any element (selector text is fine)
  type: "wheel,touch", // comma-delimited list of what to listen for ("wheel,touch,scroll,pointer")
  onUp: () => previous(),
  onDown: () => next(),
});
```

--------------------------------

### Get or Set Tween Repeat Delay (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/repeatDelay%28%29

Demonstrates how to retrieve the current repeat delay value and how to set a new repeat delay for a GSAP tween. This method is essential for controlling the timing between animation repeats.

```javascript
//gets current repeatDelay value
var repeatDelay = myTween.repeatDelay();

//sets repeatDelay to 2
myTween.repeatDelay(2);
```

--------------------------------

### Get and Set Scroll Position with GSAP ScrollTrigger

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/scroll%28%29

Demonstrates how to use the .scroll() method to both retrieve the current scroll position and set a new scroll position for a ScrollTrigger instance. This method is essential for programmatically controlling scroll behavior.

```javascript
let st = ScrollTrigger.create({
  trigger: ".class",
  scroller: ".container", 
  start: "top center",
  end: "+=500",
});

// get the current scroll position
let position = st.scroll();

// set the scroll position to 100 pixels
st.scroll(100);
```

--------------------------------

### GSAP v3 Vars Object Configuration

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

The 'vars' object is used to configure GSAP animations. It accepts animatable properties and special properties such as callbacks for lifecycle events. Example shows setting an onComplete callback.

```javascript
gsap.to(".class", {
  opacity: 0.5,
  x: 100,
  onComplete: function() {
    console.log("Animation complete!");
  }
});
```

--------------------------------

### Reverse Animation Playback with GSAP 3

Source: https://gsap.com/docs/v3/GSAP/Tween/reverse%28%29

Demonstrates various ways to use the GSAP 3 reverse() method. This includes reversing from the current playhead position, a specific time, the end of the animation, or a time relative to the end. It also shows how to toggle the reversed state and control event suppression.

```javascript
myAnimation.reverse();

myAnimation.reverse(2);

myAnimation.reverse(2, false);

myAnimation.reverse(0);

myAnimation.reverse(-1);

if (myAnimation.reversed()) {
  myAnimation.play();
} else {
  myAnimation.reverse();
}

myAnimation.reversed(!myAnimation.reversed());
```

--------------------------------

### Example Usage of LottieScrollTrigger Function (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/LottieScrollTrigger

This JavaScript code demonstrates how to use the `LottieScrollTrigger` function to initialize a scroll-driven Lottie animation. It specifies the target element, the path to the Lottie JSON file, and animation speed. Additional ScrollTrigger properties can also be passed.

```javascript
LottieScrollTrigger({
  target: "#animationWindow",
  path: "https://assets.codepen.io/35984/tapered_hello.json",
  speed: "medium",
  scrub: 2, // seconds it takes for the playhead to "catch up"
  // you can also add ANY ScrollTrigger values here too, like trigger, start, end, onEnter, onLeave, onUpdate, etc. See /docs/v3/Plugins/ScrollTrigger
});
```

--------------------------------

### SplitText Configuration Options

Source: https://gsap.com/docs/v3/Plugins/SplitText

This section outlines various configuration options for the SplitText plugin. These options control how text is split, how whitespace is handled, and how elements are tagged.

```javascript
const split = new SplitText("#myElement", {
  type: "chars,words",
  tag: "span",
  wordsClass: "word++",
  reduceWhiteSpace: false,
  smartWrap: true,
  wordDelimiter: "-",
  // ... other options
});
```

--------------------------------

### Get and Set Tween totalProgress in GSAP

Source: https://gsap.com/docs/v3/GSAP/Tween/totalProgress%28%29

Demonstrates how to retrieve the current total progress of a GSAP tween and how to set it to a specific value. The totalProgress is a number between 0 and 1, representing the virtual playhead's position.

```javascript
//gets current total progress
var progress = myTween.totalProgress();

//sets total progress to one quarter finished
myTween.totalProgress(0.25);
```

--------------------------------

### GSAP Invalidate Method

Source: https://gsap.com/docs/v3/GSAP/Tween/invalidate%28%29

The invalidate() method in GSAP v3 allows you to flush internally recorded starting and ending values of an animation. This is useful for restarting an animation without reverting to previously recorded values, enabling new relative animations.

```APIDOC
## invalidate()

### Description
Flushes any internally-recorded starting/ending values which can be useful if you want to restart an animation without reverting to any previously recorded starting values. When an animation is invalidated, it will be re-initialized the next time it renders and its vars object will be re-parsed. The timing of the animation (duration, startTime, delay) will not be affected.

When you invalidate a timeline, it automatically invalidates all of its children.

### Method
`invalidate()`

### Endpoint
N/A (This is a method of a GSAP animation object, not a REST endpoint)

### Parameters
This method does not accept any parameters.

### Request Example
```javascript
// Assuming 'myTween' is a GSAP tween object
myTween.invalidate();
```

### Response
#### Success Response
- **self** (object) - Returns the animation object itself, making chaining easier.

#### Response Example
```javascript
// Example of chaining after invalidate()
myTween.invalidate().restart();
```
```

--------------------------------

### Reverse Animation Playback (GSAP 3)

Source: https://gsap.com/docs/v3/GSAP/Timeline/reverse%28%29

Reverses the playback of a GSAP animation or timeline. By default, it starts from the current playhead position and suppresses events. You can specify a 'from' time and control event suppression.

```javascript
tl.reverse();
tl.reverse(2);
tl.reverse(2, false);
tl.reverse(0);
tl.reverse(-1);
```

--------------------------------

### GSAP 3: Play Animation from Specific Time

Source: https://gsap.com/docs/v3/GSAP/Tween/play%28%29

Starts playing a GSAP animation from a specified time. The animation will jump to this time and begin playing forward. Events and callbacks between the old and new positions are suppressed by default.

```javascript
myAnimation.play(2);
```

--------------------------------

### Get Scroll Position with GSAP ScrollSmoother scrollTop()

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/scrollTop%28%29

Retrieves the current scroll position in pixels using the scrollTop() getter method of the GSAP ScrollSmoother plugin. This is useful for determining the current scroll state.

```javascript
let scroll = smoother.scrollTop();
```

--------------------------------

### Get Previous Timeline Label (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/previousLabel%28%29

Retrieves the name of the label that occurs before a specified time in a GSAP timeline. If no time is provided, the current playhead position is used. Labels at the exact specified time are ignored.

```javascript
tl.previousLabel();
tl.previousLabel(1.5);
// Example usage with tweenTo:
tl.tweenTo(tl.previousLabel());
```

--------------------------------

### onLeaveBack Callback for ScrollTrigger

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

The onLeaveBack callback is triggered when the scroll position moves backward past the 'start' point of the ScrollTrigger. It receives the ScrollTrigger instance as a parameter, allowing access to properties like progress, direction, and isActive.

```javascript
onLeaveBack: ({progress, direction, isActive}) => console.log(progress, direction, isActive)
```

--------------------------------

### Grouping and Managing ScrollTriggers using .vars (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/vars

Illustrates a practical use case for storing custom data within the .vars object, specifically for grouping ScrollTriggers. This example shows how to filter and kill ScrollTriggers belonging to a specific group.

```javascript
// helper function (reusable):
let getGroup = (group) =>
  ScrollTrigger.getAll().filter((t) => t.vars.group === group);

// then, to kill() anything with a group of "my-group":
getGroup("my-group").forEach((t) => t.kill());
```

--------------------------------

### Get Most Recent Timeline Item with recent() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Timeline/recent%28%29

Demonstrates how to use the recent() method to retrieve the most recently added tween or timeline. This is useful for chaining animations or calculating relative timings based on the last added element.

```javascript
var tl = gsap.timeline();

//very long tween
tl.to(e1, { duration: 999, x: 100, repeat: 5 });

//insert this tween at 0.5 seconds (toward the beginning of the timeline)
tl.to(e2, { duration: 1, y: 200 }, 0.5);

//inserts the new tween 3 seconds after the e2 tween which was added most recently.
tl.to(e3, { duration: 1, scaleX: 2 }, tl.recent().endTime() + 3);
```

--------------------------------

### Get and Set Animation Duration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/duration%28%29

This snippet demonstrates how to use the GSAP v3 duration method to both retrieve the current duration of an animation and set a new duration. It is a common pattern for controlling animation timing.

```javascript
var currentDuration = myAnimation.duration(); //gets current duration
myAnimation.duration(2); //sets duration
```

--------------------------------

### Create a GSAP Timeline for sequencing animations

Source: https://gsap.com/docs/v3/GSAP

Illustrates the creation and usage of a GSAP Timeline, which acts as a container for multiple Tweens. Timelines are essential for sequencing animations, allowing for complex choreography and control over playback.

```javascript
var tl = gsap.timeline();
tl.to(".box", { duration: 2, x: 100, opacity: 0.5 });

//sequenced one-after-the-other
tl.to(".box1", { duration: 2, x: 100 }) //notice that there's no semicolon!
  .to(".box2", { duration: 1, y: 200 })
  .to(".box3", { duration: 3, rotation: 360 });

```

--------------------------------

### GSAP: Animate elements to new values

Source: https://gsap.com/docs/v3/GSAP/gsap

Animates properties of elements matching a selector to specified destination values over a given duration. GSAP automatically detects current values as starting points. This is useful for rotating and moving elements.

```javascript
// rotate and move elements with a class of "box"
// ("x" is a shortcut for a translateX() transform) over the course of 1 second.
gsap.to(".box", { rotation: 27, x: 100, duration: 1 });
```

--------------------------------

### y Property Details

Source: https://gsap.com/docs/v3/Plugins/Observer/y

Explains the 'y' property, which represents the clientY from the most recent touch/pointer event, and its update conditions.

```APIDOC
## y Property

### Description
The `y` property represents the `clientY` from the most recent touch/pointer event. This value indicates the vertical distance from the top edge of the viewport.

### Details
This property is only updated if the `type` configuration includes either "touch" or "pointer" (or both).

### Property Type
Number
```

--------------------------------

### Basic MorphSVG Configuration with Shape and Smooth

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Demonstrates the basic configuration for MorphSVG, specifying the target shape and enabling smooth morphing with redraw capabilities. This is useful for creating fluid transitions between SVG shapes.

```javascript
gsap.to("#diamond", {
	duration: 1,
	ease: "power2.inOut",
	morphSVG: {
		shape: "#lightning",
		smooth: { points: 80, redraw: true }
	}
});
```

--------------------------------

### Apply ScrollSmoother Effects with JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/effects%28%29

Demonstrates how to apply parallax and lag effects to elements using the ScrollSmoother.effects() method in JavaScript. It shows examples of using selector text, specifying config objects with speed and lag, and removing effects by resetting values.

```javascript
let smoother = ScrollSmoother.create(...);

// use the data-speed and data-lag attributes found on each .box element
smoother.effects(".box");

// or specify values:
smoother.effects(".circle", {speed: 0.9, lag: 0.3});

// remove effects by setting back to defaults
smoother.effects(".box", { speed: 1, lag: 0 });
```

--------------------------------

### Use String Format for Wiggle Ease

Source: https://gsap.com/docs/v3/Eases/CustomWiggle

Illustrates using GSAP's string ease format to apply a simple wiggle with 15 oscillations or a more advanced wiggle with specified type and oscillations.

```javascript
ease: "wiggle(15)" // <-- easy!

ease: "wiggle({type:anticipate, wiggles:8})" // advanced
```

--------------------------------

### Calculate Animation End Time with GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Timeline/endTime%28%29

Demonstrates how to use the endTime() method in GSAP v3 to get the finish time of a tween. It shows how the end time is affected by the tween's duration, its position on a timeline, and its timeScale.

```javascript
var tl = gsap.timeline();

//create a 1-second tween
var tween = gsap.to(e, { duration: 1, x: 100 });

//insert the tween at 0.5 seconds into the timeline
tl.add(tween, 0.5);

console.log(tween.endTime()); // Output: 1.5

//double the speed of the tween, thus it'll finish in half the normal time
tween.timeScale(2);

console.log(tween.endTime()); // Output: 1
```

--------------------------------

### GSAP Timeline Initialization with Defaults and Repeat Refresh (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Shows how to set default properties for child animations within a GSAP v3 timeline and enable `repeatRefresh`. The `repeatRefresh` option is particularly useful for dynamic or random values in animations that repeat.

```javascript
const myTimeline = gsap.timeline({
  defaults: {
    ease: "power1.inOut",
    duration: 1
  },
  repeatRefresh: true
});
```

--------------------------------

### Customizing Word Delimiters with RegExp

Source: https://gsap.com/docs/v3/Plugins/SplitText

Demonstrates how to use a RegExp with the `wordDelimiter` property to split words based on custom patterns and replace them with specific text. This offers advanced control over word segmentation.

```javascript
const split = new SplitText("#myElement", {
  type: "words",
  wordDelimiter: {
    delimiter: /[,.!?;:]/,
    replaceWith: " "
  }
});
```

--------------------------------

### Access ScrollSmoother's ScrollTrigger Instance and Velocity (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/scrollTrigger

This snippet demonstrates how to create a ScrollSmoother instance and then access its internal ScrollTrigger to get the native scroll velocity. It requires the GSAP ScrollSmoother plugin to be included.

```javascript
let smoother = ScrollSmoother.create({
  // configuration options...
});

let nativeScrollVelocity = smoother.scrollTrigger.getVelocity();
```

--------------------------------

### Create Anticipate Type Wiggle Ease

Source: https://gsap.com/docs/v3/Eases/CustomWiggle

Shows how to create a custom wiggle ease with 10 oscillations and the 'anticipate' type, then applies it to a GSAP tween.

```javascript
//Create a 10-wiggle anticipation ease:
CustomWiggle.create("funWiggle", {wiggles: 10, type: "anticipate"});
gsap.to(".class", {duration: 2, rotation: 30, ease: "funWiggle"});
```

--------------------------------

### Create Reusable Interpolation Function (Two Values)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/interpolate%28%29

Creates a reusable interpolation function that interpolates between a startValue and an endValue. The returned function accepts a progress value (0-1) to calculate the interpolated result. This is efficient for repeated interpolations with the same start and end points.

```javascript
var interp = gsap.utils.interpolate(0, 100);

console.log(interp(0.5)); // 50
console.log(interp(0.25)); // 25
console.log(interp(1)); // 100

var interp = gsap.utils.interpolate(
  { a: 0, b: 10, c: "red" },
  { a: 100, b: 20, c: "blue" }
);

interp(0.5); // {a: 50, b: 15, c: "rgba(128,0,128,1)"}
```

--------------------------------

### MotionPathPlugin.getRelativePosition

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Gets the x and y distances between two elements regardless of nested transforms! Feed two elements to this method and it'll return the gap between them as a point {x, y} according to the coordinate system of the fromElement's parent.

```APIDOC
## MotionPathPlugin.getRelativePosition

### Description
Gets the x and y distances between two elements regardless of nested transforms! Feed two elements to this method and it'll return the gap between them as a point {x, y} according to the coordinate system of the fromElement's parent.

### Method
STATIC

### Endpoint
MotionPathPlugin.getRelativePosition(fromElement:Element | window, toElement:Element | window, fromOrigin:Array | Object, toOrigin:Array | Object | String)

### Parameters
#### Path Parameters
- **fromElement** (Element | window) - Required - The starting element.
- **toElement** (Element | window) - Required - The ending element.
- **fromOrigin** (Array | Object) - Required - The origin point of the fromElement.
- **toOrigin** (Array | Object | String) - Required - The origin point of the toElement.

### Response
#### Success Response (200)
- **Object** - An object with x and y properties representing the distance between the elements.
```

--------------------------------

### Sequence Multiple Morphs with GSAP MorphSVG

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Demonstrates sequencing multiple morphs using GSAP's MorphSVGPlugin. It shows how to morph an element (e.g., a diamond) into various other shapes and back to its original form sequentially.

```javascript
tl.to("#diamond", { duration: 1, morphSVG: "#shape2" }, "+=1")
  .to("#diamond", { duration: 1, morphSVG: "#shape3" }, "+=1")
  .to("#diamond", { duration: 1, morphSVG: "#shape4" }, "+=1")
  .to("#diamond", { duration: 1, morphSVG: "#diamond" }, "+=1"); // back to the original
```

--------------------------------

### GSAP Flip Plugin: onLeave Callback Example

Source: https://gsap.com/docs/v3/Plugins/Flip/static

Illustrates the `onLeave` callback for GSAP's Flip plugin. This callback is triggered when a target element is present in the initial state but not in the end state, or is not in the document flow in the end state. It provides an array of leaving elements for custom animations, such as fading them out. Returned animations are added to the flip timeline.

```javascript
onLeave: elements => gsap.fromTo(elements, {opacity: 1}, {opacity: 0})
```

--------------------------------

### GSAP Function-Based Values Example

Source: https://gsap.com/docs/v3/GSAP/gsap

Demonstrates how to use function-based values for animation properties in GSAP. The function is called once for each target, allowing for dynamic and conditional animation values. The function receives the target's index, the target element itself, and the array of all targets.

```javascript
gsap.to(".class", {
  x: 100, //normal value
  y: function(index, target, targets) { //function-based value
    return index * 50;
  },
  duration: 1
});
```

--------------------------------

### MotionPathPlugin.getRawPath

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Gets the RawPath (Array) for the provided element or raw SVG <path> data. A RawPath is essentially an Array containing one Array for each contiguous segment with alternating x, y, x, y cubic bezier data.

```APIDOC
## MotionPathPlugin.getRawPath

### Description
Gets the RawPath (Array) for the provided element or raw SVG <path> data. A RawPath is essentially an Array containing one Array for each contiguous segment with alternating x, y, x, y cubic bezier data.

### Method
STATIC

### Endpoint
MotionPathPlugin.getRawPath(value:String | Element)

### Parameters
#### Path Parameters
- **value** (String | Element) - Required - The element or raw SVG <path> data.

### Response
#### Success Response (200)
- **RawPath** (Array) - An array representing the path data.
```

--------------------------------

### HTML Structure for ScrollSmoother Content

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

This HTML structure demonstrates the recommended setup for ScrollSmoother, featuring a wrapper and a content element. The 'smooth-content' div is essential as it's the element that ScrollSmoother manipulates for smooth scrolling. Elements with 'position: fixed' can be placed outside this structure.

```html
<div id="smooth-wrapper">
  <div id="smooth-content">
    <!--- ALL YOUR CONTENT HERE --->
  </div>
</div>
<!-- position: fixed elements can go outside -->
```

--------------------------------

### Initialize ScrollSmoother and Log Progress

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/progress

This snippet demonstrates how to initialize ScrollSmoother with a smooth scrolling factor and log the scroll progress to the console during updates. It utilizes the onUpdate callback to access the progress value.

```javascript
ScrollSmoother.create({
  smooth: 1,
  onUpdate: (self) => console.log("progress", self.progress),
});
```

--------------------------------

### Combine clamp with other utilities using pipe()

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/clamp%28%29

Demonstrates chaining multiple GSAP utility functions, including `clamp()`, `mapRange()`, and `snap()`, using `gsap.utils.pipe()`. This allows for complex data transformations on a single input value, creating a powerful reusable 'transformer' function.

```javascript
var transformer = gsap.utils.pipe(
  gsap.utils.clamp(0, 100),
  gsap.utils.mapRange(0, 100, 0, window.innerWidth),
  gsap.utils.snap(20)
);

transformer(25.874);
```

--------------------------------

### timeScale Method

Source: https://gsap.com/docs/v3/GSAP/Tween/timeScale%28%29

The timeScale method allows you to get or set the playback speed of a GSAP animation. A value of 1 is normal speed, 0.5 is half speed, and 2 is double speed. Negative values can be used for reverse playback.

```APIDOC
## GET/SET timeScale

### Description
Controls the playback speed of the animation. Use as a getter to retrieve the current timeScale, or as a setter to define a new speed. A `timeScale` of 1 is normal speed, 0.5 is half speed, 2 is double speed, and negative values play the animation in reverse.

### Method
GET / SET

### Endpoint
`animationInstance.timeScale( [value:Number] )`

### Parameters
#### Query Parameters
- **value** (Number) - Optional - The new time scale value. If omitted, the current time scale is returned.

### Request Example
```javascript
// Get current time scale
var currentSpeed = animation.timeScale();

// Set time scale to half speed
animation.timeScale(0.5);

// Set time scale to double speed and return instance for chaining
animation.timeScale(2).play();
```

### Response
#### Success Response (200)
- **Number** - The current time scale value (if used as a getter).
- **Object** - The animation instance itself (if used as a setter), allowing for chaining.

#### Response Example
```json
// Getter response example
1

// Setter response example (returns the instance)
{
  "_gsTweenType": " animasi "
}
```
```

--------------------------------

### Get and Set Timeline Duration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/duration%28%29

Demonstrates how to retrieve the current duration of a GSAP timeline and how to set a new duration by adjusting the timeline's timeScale to fit its contents within the specified time. This method is useful for controlling playback speed and fitting animations into specific time constraints.

```javascript
//gets current duration
var currentDuration = tl.duration();

//adjusts the timeScale of myAnimation so that it fits into exactly 10 seconds on its parent timeline
tl.duration(10);
```

--------------------------------

### GSAP Utility Methods

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

This section details various utility methods provided by GSAP v3 for common tasks like value manipulation, unit handling, and distribution.

```APIDOC
## Utility Methods

### checkPrefix

#### Description
Prefixes the provided CSS property if necessary.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/checkPrefix`

### clamp

#### Description
Clamps a value to fit within a specific range. Example: `clamp(0, 100, -12)` returns `0`.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/clamp`

### distribute

#### Description
Distributes a value among an array of objects either linearly or according to their position in a grid, optionally with easing applied.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/distribute`

### getUnit

#### Description
Gets the unit of a string. Example: `getUnit("30px")` returns `"px"`.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/getUnit`

### interpolate

#### Description
Interpolates between almost any two values (numbers, colors, strings, arrays, complex strings, or even objects with multiple properties). Example: `interpolate("red", "blue", 0.5)` returns `"rgba(128,0,128,1)"`.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/interpolate`

### mapRange

#### Description
Maps one range to another. Example: `mapRange(-10, 10, 0, 100, 5)` returns `75`.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/mapRange`

### normalize

#### Description
Maps a number within a range to a progress between 0 and 1. Example: `normalize(100, 200, 150)` returns `0.5`.

#### Method
UTILITY

#### Endpoint
`/websites/gsap_v3/UtilityMethods/normalize`
```

--------------------------------

### Get Browser-Prefixed CSS Property Name (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/checkPrefix%28%29

The checkPrefix() utility takes a CSS property name as a string and returns the browser-prefixed version if necessary. If no prefix is required or the property doesn't exist, it returns the original name or undefined, respectively. This is useful for ensuring cross-browser compatibility of CSS properties.

```javascript
var filterProperty = gsap.utils.checkPrefix("filter");
// Example output: "filter", "WebkitFilter", or "MozFilter" depending on the browser.
```

--------------------------------

### GSAP Utility: checkPrefix

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `checkPrefix` utility method prefixes a given CSS property with vendor prefixes if necessary. This ensures cross-browser compatibility for CSS properties. It takes a property name as input and returns the prefixed version.

```javascript
gsap.utils.checkPrefix("transform");
// Example output: "webkitTransform" (depending on browser support)
```

--------------------------------

### Wrap Array Values with Yoyo Effect (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/wrapYoyo%28%29

This snippet demonstrates how to use GSAP's wrapYoyo utility to get values from an array, cycling forwards and backwards. If an index is provided, it returns the corresponding wrapped value. If no index is provided, it returns a function that can be called with an index later.

```javascript
let color = gsap.utils.wrapYoyo(["red", "green", "yellow"], 5); // "red"

let wrap = gsap.utils.wrapYoyo(["red", "green", "yellow"]);
let color = wrap(5); // "green"
```

--------------------------------

### Get and Control Snap Tween with ScrollTrigger.getTween(true) - JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/getTween%28%29

Retrieves the snap tween instance from a ScrollTrigger by passing `true` to getTween(). This is useful when a snap animation is in progress and you need to interrupt or control it, such as forcing it to its end and then killing it.

```javascript
let anim = gsap.to(panels, {
  x: () => (panels.length - 1) * window.innerWidth,
  scrollTrigger: {
    trigger: ".container",
    snap: 1 / (panels.length - 1),
    pin: true,
    end: "+=3000",
  },
});

// Get the snap tween and control it
let snap = anim.scrollTrigger.getTween(true);
if (snap) {
  snap.progress(1).kill(); // Force the snap to its end and kill it
}
```

--------------------------------

### GSAP v3: Reverse Animation Playback with reversed

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

When `reversed` is set to `true`, the animation begins with its playhead oriented towards the start. Since the playhead defaults to time 0, a reversed tween will initially appear paused as it cannot move backward past the beginning.

```javascript
gsap.to("#myElement", {
  x: 100,
  reversed: true
});
```

--------------------------------

### DrawSVG Animation with Timeline

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

Illustrates creating a GSAP timeline to control multiple DrawSVG animations. This allows for sequencing, pausing, playing, reversing, and seeking through the animations.

```javascript
var tl = gsap.timeline();
tl.from(".draw-me", { duration: 2, drawSVG: 0 }, 0.1);

//now we can control it:
tl.pause();
tl.play();
tl.reverse();
tl.seek(0.5);
```

--------------------------------

### Get or Set Timeline Repeat Delay (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/repeatDelay%28%29

This snippet demonstrates how to use the repeatDelay method in GSAP v3. It shows how to retrieve the current repeat delay value and how to set a new delay for a timeline instance. The method is chainable, allowing for fluent animation configuration.

```javascript
var tl = gsap.timeline({ repeat: 2, repeatDelay: 1 });

// Gets current repeat delay value
var currentDelay = tl.repeatDelay();

// Sets repeat delay to 2 seconds
tl.repeatDelay(2);

// Example of chaining other methods
tl.yoyo(true).play();
```

--------------------------------

### Draggable Callbacks and Options

Source: https://gsap.com/docs/v3/Plugins/Draggable

This section covers the event callbacks and configuration options for the Draggable plugin, allowing customization of drag behavior and interactions.

```APIDOC
## Draggable Configuration Options

### Description
Configuration options for the GSAP Draggable plugin, including event callbacks, trigger elements, and drag types.

### Method
N/A (Configuration Object)

### Endpoint
N/A

### Parameters
#### Callbacks
- **onLockAxis** (Function) - Called when movement is locked to a specific axis (horizontal or vertical).
- **onMove** (Function) - Called every time the mouse or touch moves during a drag.
- **onPress** (Function) - Called as soon as the mouse or touch presses down on the element.
- **onPressInit** (Function) - Called before starting values are recorded in `onPress`.
- **onRelease** (Function) - Called as soon as the mouse or touch is released after pressing.

#### Configuration Options
- **onPressParams** (Array) - Optional array of parameters to feed the `onPress` callback.
- **onReleaseParams** (Array) - Optional array of parameters to feed the `onRelease` callback.
- **trigger** (Element | String | Object) - Defines a specific element or selector to trigger dragging.
- **type** (String) - Indicates the type of dragging (e.g., `"x,y"`, `"left,top"`, `"rotation"`, `"x"`, `"y"`). Defaults to `"x,y"`.
- **zIndexBoost** (Boolean) - Whether to boost the z-index of the dragged element. (Note: Description incomplete in source text)

### Request Example
```json
{
  "onPress": function(event) { console.log("Pressed!"); },
  "onMove": function(event) { console.log("Moving..."); },
  "onRelease": function(event) { console.log("Released!"); },
  "trigger": ".handle",
  "type": "x"
}
```

### Response
#### Success Response (200)
N/A (This is a configuration object, not an API endpoint response.)

#### Response Example
N/A
```

--------------------------------

### GSAP Timeline Configuration with Special Properties

Source: https://gsap.com/docs/v3/GSAP/Timeline

Demonstrates how to configure a GSAP timeline with special properties like repeat, repeatDelay, yoyo, and callback functions such as onComplete. These properties allow for advanced control over animation behavior and execution flow.

```javascript
gsap.timeline({
  onComplete: myFunction,
  repeat: 2,
  repeatDelay: 1,
  yoyo: true,
});
```

--------------------------------

### Responsive ScrollTriggers with matchMedia (ScrollTrigger)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Create responsive ScrollTrigger configurations using GSAP's `matchMedia` utility. This allows you to define different animation behaviors or trigger points based on standard CSS media queries, ensuring optimal performance and appearance across various screen sizes.

```javascript
let mm = gsap.matchMedia();

mm.add("(min-width: 1024px)", () => {
  gsap.to("#desktopElement", {
    x: 300,
    scrollTrigger: {
      trigger: "#desktopElement",
      start: "top center"
    }
  });
  return () => {}; // Cleanup function
});

mm.add("(max-width: 1023px)", () => {
  gsap.to("#mobileElement", {
    y: 200,
    scrollTrigger: {
      trigger: "#mobileElement",
      start: "top bottom"
    }
  });
  return () => {}; // Cleanup function
});
```

--------------------------------

### Deleting an Animation Event Callback (GSAP)

Source: https://gsap.com/docs/v3/GSAP/Timeline/eventCallback%28%29

This example shows how to remove an event callback, specifically 'onUpdate', from a GSAP animation instance. By passing 'null' as the callback function, the associated event listener is effectively deleted, preventing the callback from being executed.

```javascript
// deletes the onUpdate
myAnimation.eventCallback("onUpdate", null);
```

--------------------------------

### GSAP Timeline Initialization with Callback Scope (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Demonstrates setting a specific scope for all callbacks within a GSAP v3 timeline. This allows `this` inside the callback functions to refer to the specified object, providing context for the callback execution.

```javascript
const myScope = {
  name: "myAnimationScope"
};
const myTimeline = gsap.timeline({
  callbackScope: myScope,
  onComplete: function() {
    console.log(this.name);
  }
});
```

--------------------------------

### Get CSS Rule for Animation using GSAP CSSRulePlugin

Source: https://gsap.com/docs/v3/Plugins/CSSRulePlugin/methods/static-getRule%28%29

This snippet demonstrates how to use CSSRulePlugin.getRule to retrieve a CSS rule object based on a selector. This object can then be used with GSAP's to() method to animate CSS properties of that rule. Ensure CSSRulePlugin.js is loaded before use. It takes a string selector and returns a stylesheet object.

```javascript
var rule = CSSRulePlugin.getRule(".myClass::before"); //get the rule
gsap.to(rule, {duration: 3, cssRule: {color: "#0000FF"}});
```

```javascript
gsap.to(CSSRulePlugin.getRule(".myClass::before"), {
  duration: 3,
  cssRule: { color: "#0000FF" },
});
```

--------------------------------

### Create and Control a GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline

Demonstrates the minimal usage of GSAP Timelines to sequence multiple tweens. It shows how to create a timeline, add tweens to it, and then control the entire sequence using methods like pause, resume, seek, and reverse.

```javascript
gsap.to(".box", { rotation: 27, x: 100, duration: 1 });

let tl = gsap.timeline();
tl.to("#green", {duration: 1, x: 786})
  .to("#blue", {duration: 2, x: 786})
  .to("#orange", {duration: 1, x: 786});

tl.pause();
tl.resume();
tl.seek(1.5);
tl.reverse();
```

--------------------------------

### ScrollSmoother Callback Functions

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

This JavaScript example illustrates how to implement callback functions for ScrollSmoother events. `onFocusIn` is triggered when an element gains focus, allowing custom behavior or disabling default viewport focusing. `onStop` is called when the smoothed scrolling catches up to the native scroll position. `onUpdate` executes after the content's position is updated.

```javascript
gsap.registerPlugin(ScrollSmoother);

ScrollSmoother.create({
  wrapper: "#smooth-wrapper",
  content: "#smooth-content",
  onFocusIn: function(event) {
    console.log("Focus received by:", event.target);
    // return false; // Uncomment to prevent ScrollSmoother from scrolling to the focused element
  },
  onStop: function() {
    console.log("ScrollSmoother has stopped.");
  },
  onUpdate: function() {
    // console.log("ScrollSmoother updated.");
  }
});
```

--------------------------------

### Storing and Retrieving Custom Data in SplitText .vars

Source: https://gsap.com/docs/v3/Plugins/SplitText/vars

Illustrates how to store arbitrary data, such as a 'group' property, within the `vars` object of a SplitText instance. This custom data can then be used to filter and manage multiple SplitText instances, for example, to kill them collectively.

```javascript
// Helper function to get SplitText instances by group
let getGroup = (group) =>
  SplitText.getAll().filter((t) => t.vars.group === group);

// Example usage: Create a SplitText with a group property
let mySplit = SplitText.create({
  type: "chars",
  group: "my-group"
});

// Kill all SplitText instances belonging to 'my-group'
getGroup("my-group").forEach((t) => t.kill());
```

--------------------------------

### Timeline Configuration Vars

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Explains the configuration object (vars) that can be passed to the GSAP v3 timeline constructor.

```APIDOC
## Timeline Configuration Vars

### Description
The configuration object passed into the original timeline via the constructor, like `gsap.timeline({onComplete: func});`

### Method
N/A (Constructor parameter)

### Endpoint
N/A

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
##### vars (Object) - Required
The configuration object for the timeline. This can include various properties to control timeline behavior, such as callbacks, defaults, and more.

- **onComplete** (Function) - Optional - A function to be called when the timeline completes.
- **onStart** (Function) - Optional - A function to be called when the timeline starts.
- **onUpdate** (Function) - Optional - A function to be called on every frame of the timeline's progress.
- **onRepeat** (Function) - Optional - A function to be called each time the timeline repeats.
- **onReverseComplete** (Function) - Optional - A function to be called when the timeline completes its reverse playback.
- **delay** (Number) - Optional - A delay before the timeline starts playing.
- **repeat** (Number) - Optional - The number of times the timeline should repeat. Use -1 for infinite repeats.
- **repeatDelay** (Number) - Optional - A delay between repeats.
- **yoyo** (Boolean) - Optional - If true, the timeline will play forwards and then backwards on repeat.
- **paused** (Boolean) - Optional - If true, the timeline will start in a paused state.
- **reversed** (Boolean) - Optional - If true, the timeline will start in a reversed state.
- **smoothChildTiming** (Boolean) - Optional - If true, child tweens will be affected by the parent timeline's progress and reversed state.
- **id** (String|Number) - Optional - An identifier for the timeline.

### Request Example
```javascript
gsap.timeline({
  onComplete: myCompleteFunction,
  delay: 1,
  repeat: -1,
  yoyo: true
});
```

### Response
N/A (This is a constructor parameter, not an endpoint response.)

#### Success Response (N/A)
N/A

#### Response Example
N/A
```

--------------------------------

### Track Object Property Velocity with VelocityTracker

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/VelocityTracker

Starts tracking specified numeric properties of an object and allows retrieval of their velocities. Ensure at least 100ms and 2 ticks have elapsed before calling getVelocity() for accurate results. This method is typically accessed via InertiaPlugin.track().

```javascript
var tracker = VelocityTracker.track(obj, "x,y")[0];
var vx = tracker.get("x");
var vy = tracker.get("y");
```

--------------------------------

### Generate SVG Path Data with CustomEase.getSVGData()

Source: https://gsap.com/docs/v3/Eases/CustomEase

This method calculates and returns the SVG `<path>` data string for visualizing a CustomEase or a standard ease graphically. It takes the ease identifier and an object with visualization parameters like width, height, and an SVG path element ID. The `path` property in the vars object populates the `d` attribute of the specified SVG path.

```javascript
CustomEase.create(
  "hop",
  "M0,0 C0,0 0.056,0.445 0.175,0.445 0.294,0.445 0.332,0 0.332,0 0.332,0 0.414,1 0.671,1 0.991,1 1,0 1,0"
);

CustomEase.getSVGData("hop", { width: 500, height: 400, path: "#ease" });
```

--------------------------------

### GSDevTools Configuration Options

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

This snippet outlines the various properties that can be set within the GSDevTools configuration object to customize its behavior and appearance. Options include specifying animations, containers, CSS styles, and control over timeline synchronization, visibility, and state persistence.

```javascript
{
  animation: "myAnimationId", // or a GSAP animation object
  container: "#devTools", // or a DOM element
  css: {
    width: "50%",
    bottom: "30px"
  }, // or a CSS string
  globalSync: true,
  hideGlobalTimeline: false,
  id: "myInstance",
  inTime: 0,
  keyboard: true,
  loop: false,
  minimal: false,
  outTime: 10,
  paused: false,
  persist: true,
  timeScale: 1,
  visibility: "auto"
}
```

--------------------------------

### Accessing the Pinned Element with ScrollTrigger .pin (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/pin

This example demonstrates how to create a ScrollTrigger instance and access the pinned element using the .pin property. The .pin property returns the actual DOM element, not the selector string used during creation. This is useful for direct DOM manipulation or inspection.

```javascript
let st = ScrollTrigger.create({
  trigger: ".trigger",
  pin: ".pin",
  start: "top center",
  end: "+=500",
});

console.log(st.pin); // Outputs the pinned DOM element
```

--------------------------------

### Get Current State with Flip.getState() - JavaScript

Source: https://gsap.com/docs/v3/Plugins/Flip/static

Captures the current position, size, and rotation of target elements. Accepts selector text, an Element, an Array of Elements, or a NodeList. Optionally, it can record additional CSS properties by providing a configuration object with a 'props' key. This function does not alter the elements' state.

```javascript
const state = Flip.getState(".targets");
// To record additional properties:
// const state = Flip.getState(".targets", { props: "backgroundColor,color" });
```

--------------------------------

### Get and Set GSAP Timeline Total Progress (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/totalProgress%28%29

This snippet demonstrates how to retrieve the current total progress of a GSAP timeline and how to set it to a specific value. The total progress is a value between 0 and 1, including repeats and repeatDelays. Suppressing events is optional.

```javascript
// Gets total progress
var progress = tl.totalProgress();

// Sets total progress to one quarter finished
tl.totalProgress(0.25);

// Sets total progress and suppresses events
tl.totalProgress(0.5, true);
```

--------------------------------

### GSAP Tween Creation

Source: https://gsap.com/docs/v3/GSAP/Tween

Demonstrates the minimal usage of GSAP's tweening methods like gsap.to(), gsap.from(), and gsap.fromTo() to animate object properties.

```APIDOC
## GSAP Tween Creation

### Description
GSAP Tweens are the core of GSAP animations, acting as high-performance property setters. They animate specified properties of target objects over a given duration.

### Methods
- `gsap.to(targets, vars)`: Animates properties from their current values to new values.
- `gsap.from(targets, vars)`: Animates properties from new values to their current values.
- `gsap.fromTo(targets, vars)`: Animates properties from a start value to an end value.

### Parameters
#### Targets
- **targets** (string | object | array) - The object(s) or selector text for the properties you want to animate.

#### Vars
- **vars** (object) - An object containing animation properties and special properties.
  - **duration** (number) - The duration of the animation in seconds.
  - **ease** (string) - The easing function for the animation (e.g., "power1.inOut", "elastic.out").
  - **delay** (number) - The delay before the animation starts in seconds.
  - **onComplete** (function) - A callback function to execute when the animation completes.
  - *...any other animatable property*

### Request Example
```javascript
// Animate rotation and x translation of elements with class "box" over 1 second
gsap.to(".box", { rotation: 27, x: 100, duration: 1 });

// Animate opacity from 0 to 1 over 0.5 seconds
gsap.from("p", { opacity: 0, duration: 0.5 });

// Animate x position from 50 to 0 over 2 seconds with an elastic ease
gsap.fromTo("#element", { x: 50 }, { x: 0, duration: 2, ease: "elastic.out(1, 0.3)" });
```

### Response
Returns a Tween instance that can be controlled programmatically.

#### Success Response (Tween Instance)
- **Tween Instance** (object) - A GSAP Tween object with methods like `play()`, `pause()`, `seek()`, `progress()`, etc.

#### Response Example
```javascript
let tween = gsap.to(".my-element", { x: 200, duration: 1 });

// Control the tween later
tween.pause();
tween.seek(0.5);
tween.play();
```
```

--------------------------------

### Get or Set Animation Delay (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/delay%28%29

This snippet demonstrates how to use the delay() method in GSAP v3. It shows how to retrieve the current delay of an animation by calling delay() without arguments and how to set a new delay by passing a numeric value. The setter returns the animation instance, enabling method chaining.

```javascript
var currentDelay = myAnimation.delay(); // Gets current delay
myAnimation.delay(2); // Sets delay to 2 seconds
```

--------------------------------

### Get Next Timeline Label (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/nextLabel%28%29

Retrieves the name of the next label on a GSAP timeline from a specified time. If no time is provided, the current playhead time is used. Labels exactly at the specified time are ignored. This method is useful for programmatic timeline navigation.

```javascript
tl.nextLabel();
tl.nextLabel(1.5);
// Example usage with tweenTo:
tl.tweenTo(tl.nextLabel());
```

--------------------------------

### Callback Data

Source: https://gsap.com/docs/v3/Plugins/Observer

Explains the data passed to callbacks within the Observer instance, including velocity, delta, target element, and last event.

```APIDOC
## Callback Data

### Description
Each callback is passed the Observer instance itself as the only parameter. This allows access to properties like `self.velocityX`, `self.velocityY`, `self.deltaX`, `self.deltaY`, `self.x`, `self.y`, and others.

### Method
N/A (Callback function)

### Endpoint
N/A (Callback function)

### Parameters
#### Observer Instance (`self`)
- **velocityX** (Number) - The current velocity along the X-axis.
- **velocityY** (Number) - The current velocity along the Y-axis.
- **deltaX** (Number) - The change in X position since the last event.
- **deltaY** (Number) - The change in Y position since the last event.
- **x** (Number) - The current X position.
- **y** (Number) - The current Y position.
- **target** (Element) - The DOM element being observed.
- **event** (Event) - The last DOM event that triggered the callback.

### Request Example
```javascript
Observer.create({
  // ... other Observer options
  onChange: (self) => {
    console.log("velocity:", self.velocityX, self.velocityY, "delta:", self.deltaX, self.deltaY, "target element:", self.target, "last event:", self.event);
  }
});
```

### Response
#### Success Response (N/A)
N/A

#### Response Example
N/A
```

--------------------------------

### reversed() Method

Source: https://gsap.com/docs/v3/GSAP/Tween/reversed%28%29

This method allows you to get or set the reversed state of a GSAP animation. When used as a getter, it returns a boolean indicating if the animation is reversed. When used as a setter, it accepts a boolean value to set the reversed state and returns the animation instance for chaining.

```APIDOC
## reversed( value: Boolean )

### Description
Gets or sets the animation's reversed state, indicating whether or not the animation should be played backwards. This value is not affected by `yoyo` repeats and does not take into account the reversed state of ancestor timelines.

### Method
GET or SET

### Endpoint
N/A (This is a method of a GSAP animation object)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters (Setter)
#### value (Boolean)
- **value** (Boolean) - Optional - `true` to play the animation backwards, `false` to play it forwards. Defaults to `false`.

### Request Example
```javascript
// Gets current reversed state
var isReversed = myAnimation.reversed();

// Sets the animation to be reversed
myAnimation.reversed(true);

// Toggles the reversed state
myAnimation.reversed(!myAnimation.reversed());
```

### Response
#### Success Response (Getter)
- **reversed state** (Boolean) - Returns `true` if the animation is currently reversed, `false` otherwise.

#### Success Response (Setter)
- **self** (Object) - Returns the animation instance itself for chaining.

#### Response Example (Getter)
```json
{
  "reversed state": true
}
```

#### Response Example (Setter)
```json
{
  "self": "[Animation Instance]"
}
```
```

--------------------------------

### Chaining Functions with GSAP pipe()

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/pipe%28%29

Demonstrates how to use GSAP's pipe() utility to chain multiple functions sequentially, improving code readability compared to manual chaining or nested function calls. It takes an input value and passes it through a series of provided functions.

```javascript
// without pipe()
var value1 = func1(input);
var value2 = func2(value1);
var output = func3(value2);

// or multi-level wrapping (awkward)
var output = func1(func2(func3(input)));

// cleaner with pipe()
var transfrom = gsap.utils.pipe(func1, func2, func3);
var output = transform(input);
```

--------------------------------

### Control ScrollSmoother Scrolling with .paused() (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/paused%28%29

Demonstrates how to use the .paused() method to set the paused state to true, effectively stopping scrolling, and how to get the current paused state to conditionally execute code. This method is crucial for managing user interaction and animation flow.

```javascript
const smoother = ScrollSmoother.create({
  content:"#content",
  smooth: 1
});

// Setter: Pause scrolling
smoother.paused(true);

// Getter: Check if scrolling is paused
if (!smoother.paused()) {
  console.log("Scrolling is not paused.");
}

// Example of toggling pause state on a button click
document.querySelector("#toggle").addEventListener("click", () => {
  smoother.paused(!smoother.paused());
  console.log("ScrollSmoother paused state toggled.");
});
```

--------------------------------

### Get Scrub Tween with ScrollTrigger.getTween() - JavaScript

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/getTween%28%29

Retrieves the default scrub tween instance from a ScrollTrigger. This tween is responsible for gradually synchronizing the animation with the scrollbar position. It's useful for directly controlling the animation's progress, such as forcing it to its end.

```javascript
let st = ScrollTrigger.create({
  animation: myTween,
  scrub: 1,
  trigger: ".panel-1",
});

// Force the scrub tween to its end
st.getTween().progress(1);
```

--------------------------------

### Log Scroll Direction with ScrollTrigger

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/direction

This example demonstrates how to use the .direction property within the onUpdate callback of a ScrollTrigger instance. It logs the current scrolling direction (1 for forward, -1 for backward) to the console whenever the scroll position updates. This requires the GSAP ScrollTrigger plugin.

```javascript
ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
  onUpdate: (self) => console.log("direction:", self.direction)
});
```

--------------------------------

### Create GSDevTools Linked to a Timeline

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Creates a GSDevTools instance and links it to a specific GSAP timeline instance. This allows GSDevTools to focus on controlling and debugging that particular animation, rather than all global animations.

```javascript
var tl = gsap.timeline();
tl.to(...);

GSDevTools.create({animation: tl});
```

--------------------------------

### Kill Specific Property Tweens of Elements by Class

Source: https://gsap.com/docs/v3/GSAP/Timeline/killTweensOf%28%29

This example shows how to use GSAP's killTweensOf method to stop tweens for specific properties (e.g., 'x', 'y') on elements identified by a CSS selector. This provides more granular control over which animations are terminated.

```javascript
tl.killTweensOf(".box", "x,y");
```

--------------------------------

### Flip.getState

Source: https://gsap.com/docs/v3/Plugins/Flip

Captures information about the current state of targets for later use with Flip animations.

```APIDOC
## POST /websites/gsap_v3/plugins/flip/getstate

### Description
Captures information about the current state of the `targets` so that they can be Flipped later. By default, this information includes the dimensions, rotation, skew, opacity, and the position of the targets in the viewport. Other properties can be captured by configuring the `vars` parameter.

### Method
POST

### Endpoint
/websites/gsap_v3/plugins/flip/getstate

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **targets** (String | Element | Array) - Required - The targets to capture the state of.
- **vars** (Object) - Optional - An object to configure which properties to capture.

### Request Example
```json
{
  "targets": "#myElement",
  "vars": {
    "x": true,
    "y": true
  }
}
```

### Response
#### Success Response (200)
- **Object** (Object) - An object containing the captured state information.

#### Response Example
```json
{
  "x": 100,
  "y": 50,
  "width": 200,
  "height": 150
}
```
```

--------------------------------

### GSAP v3: Invert Tween Values with runBackwards

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

Setting `runBackwards: true` inverts the starting and ending values of a tween, similar to how a `gsap.from()` tween functions internally. Note that the ease of the animation is not flipped. This allows a `to()` tween to behave like a `from()` tween.

```javascript
gsap.to("#myElement", {
  x: 100,
  runBackwards: true
});
```

--------------------------------

### Configure Inertia Plugin with Snap Object for Top and Left

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet demonstrates using an object with snap functions for 'top' and 'left' properties within the InertiaPlugin. This provides granular control over snapping behavior for vertical and horizontal movement.

```javascript
Draggable.create(element, {
  type: "top,left",
  inertia: true,
  snap: {
    top: function(endValue) { return Math.round(endValue / 50) * 50; },
    left: function(endValue) { return Math.round(endValue / 100) * 100; }
  }
});
```

--------------------------------

### GSAP 3: Play Animation from Specific Time Without Suppressing Events

Source: https://gsap.com/docs/v3/GSAP/Tween/play%28%29

Starts playing a GSAP animation from a specified time while also triggering any events or callbacks that occur between the original and new playhead positions. This is achieved by setting the suppressEvents parameter to false.

```javascript
myAnimation.play(2, false);
```

--------------------------------

### ScrollTrigger .scroll() Method

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/scroll%28%29

This method allows you to get or set the scroll position of the scroller associated with a ScrollTrigger instance. When used as a getter, it returns the current scroll position. When used as a setter, it takes a numeric value representing the desired scroll position.

```APIDOC
## .scroll()

### Description
Gets or sets the scroll position of the associated scroller.

### Method
`scroll(position?: Number): Number | null`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Get the current scroll position
let currentPosition = scrollTriggerInstance.scroll();

// Set the scroll position to 100 pixels
scrollTriggerInstance.scroll(100);
```

### Response
#### Success Response (Getter)
- **scrollPosition** (Number) - The current scroll position in pixels.

#### Success Response (Setter)
- **undefined** - The method returns undefined when used as a setter.

#### Response Example (Getter)
```json
{
  "scrollPosition": 150
}
```
```

--------------------------------

### Get Tweens of Target with getTweensOf (GSAP v3)

Source: https://gsap.com/docs/v3/GSAP/Timeline/getTweensOf%28%29

Retrieves tweens associated with a specific target within a GSAP timeline. The 'nested' parameter controls inclusion of tweens from nested timelines. Accepts object, selector text, or an array of targets.

```javascript
tl.getTweensOf(".myClass");
tl.getTweensOf(myElem, true);
```

--------------------------------

### Get Random Element, Not Previous (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/pluckRandomFrom

This function selects a random element from an array, ensuring that the element selected is not the same as the one previously chosen. It modifies the array to store the index of the last selected element. No external dependencies.

```javascript
function getRandomFrom(array) {
  var selected = array.selected;
  while (
    selected === (array.selected = Math.floor(Math.random() * array.length))
  ) {}
  return array[array.selected];
}
```

--------------------------------

### Flexible Scroll Position Definition (ScrollTrigger)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Define precise start and end points for ScrollTrigger animations using a flexible syntax. This includes keywords like 'top', 'center', 'bottom', percentages, pixel values, and relative offsets (e.g., `+=300px`), allowing for intuitive control over animation triggers.

```javascript
gsap.to(".animate", {
  scale: 1.5,
  scrollTrigger: {
    trigger: ".animate",
    start: "top center", // Start when top of trigger hits center of viewport
    end: "bottom top+=100px", // End when bottom of trigger hits 100px above viewport top
    markers: true // Show visual markers during development
  }
});
```

--------------------------------

### Manually Refresh a Single ScrollTrigger Instance

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/refresh%28%29

This code snippet demonstrates how to manually trigger a recalculation of the start and end values for a specific ScrollTrigger instance associated with a GSAP timeline. This is useful after adding animations to a timeline to ensure its scroll behavior is correctly calculated.

```javascript
const tl = gsap.timeline({
  scrollTrigger: {
    // trigger: "#someElement",
    // start: "top top",
    // end: "bottom bottom",
    // markers: true,
    // pin: true
  }
});

// After adding all animations to the timeline, refresh its ScrollTrigger instance
tl.scrollTrigger.refresh();
```

--------------------------------

### Animating PixiJS Properties (Old vs. New Way)

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

Compares the traditional method of animating nested PixiJS properties (like scale, skew, rotation) with the simplified approach offered by PixiPlugin. The new way uses degrees for rotation and directly animates properties like scaleX and skewX.

```javascript
//old way (without plugin):
gsap.to(pixiObject.scale, { x: 2, y: 1.5, duration: 1 });
gsap.to(pixiObject.skew, { x: (30 * Math.PI) / 180, duration: 1 });
gsap.to(pixiObject, { rotation: (60 * Math.PI) / 180, duration: 1 });

//new way (with plugin):
gsap.to(pixiObject, {
  pixi: { scaleX: 2, scaleY: 1.5, skewX: 30, rotation: 60 },
  duration: 1,
});
```

--------------------------------

### Complex Relative Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Utilize prefixes like '+=' and '-=' with numbers or percentages for advanced relative positioning. This allows for gaps, overlaps, and precise offsets from labels or previous animations.

```javascript
// 1 second past the end of the timeline
tl.from(".class", { x: 100 }, "+=1");

// 1 second before the end of the timeline (overlaps)
tl.from(".class", { x: 100 }, "-=1");

// 2 seconds past the label "myLabel"
tl.from(".class", { x: 100 }, "myLabel+=2");

// 3 seconds past the start of the previous animation
tl.from(".class", { x: 100 }, "<+=3");

// 0.5 seconds before the end of the previous animation
tl.from(".class", { x: 100 }, ">-0.5");

// Overlap by 25% of the inserting animation's duration
tl.from(".class", { x: 100 }, "-=25%");

// Gap of 50% of the inserting animation's duration
tl.from(".class", { x: 100 }, "+=50%");

// 25% into the previous animation (from its start)
tl.from(".class", { x: 100 }, "<25%");

// 30% past the label "myLabel" based on inserting animation's duration
tl.from(".class", { x: 100 }, "myLabel+=30%");
```

--------------------------------

### GSAP Interpolate Function Usage

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/interpolate%28%29

Demonstrates how to create and use the GSAP interpolate utility function. This function generates a reusable interpolator for numbers or colors, which can then be called with a progress value to get an interpolated result. It's useful for creating smooth transitions or color blends.

```javascript
// get a function that will interpolate the Array
var interp = gsap.utils.interpolate([100, 50, 500]); //notice we didn't provide a progress value

// now we can reuse the function to interpolate any values:
console.log(interp(0.5)); // 50
console.log(interp(0.75)); // 275

// even works for colors!
var interp = gsap.utils.interpolate(["red", "green", "blue"]);

interp(0.25); // "rgba(128,64,0,1)"
```

--------------------------------

### ScrollTrigger Instance - .next()

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/next%28%29

Retrieves the next ScrollTrigger instance in the refresh order.

```APIDOC
## .next()

### Description
Returns the next ScrollTrigger in the refresh order.

### Method
GET

### Endpoint
N/A (This is an instance method, not a REST endpoint)

### Parameters
None

### Request Example
N/A

### Response
#### Success Response (200)
- **ScrollTrigger instance** (object) - The next ScrollTrigger instance in the refresh order.

#### Response Example
```json
{
  "instance": "ScrollTrigger instance object"
}
```
```

--------------------------------

### Customizing ScrollSmoother Effects Prefix

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

This JavaScript snippet demonstrates how to use the `effectsPrefix` option to specify custom data attribute prefixes for ScrollSmoother effects. This is useful if `data-speed` or `data-lag` are already in use for other purposes. The example sets the prefix to 'scroll-', meaning ScrollSmoother will look for `data-scroll-speed` and `data-scroll-lag` attributes.

```javascript
gsap.registerPlugin(ScrollSmoother);

ScrollSmoother.create({
  wrapper: "#smooth-wrapper",
  content: "#smooth-content",
  effects: true,
  effectsPrefix: "scroll-" // Looks for data-scroll-speed and data-scroll-lag
});

// Example elements with custom prefix:
// <div data-scroll-speed="0.7">...</div>
```

--------------------------------

### Get Animation End Time (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/endTime%28%29

Calculates the end time of a GSAP animation. By default, it includes repeats in the calculation. You can pass `false` to the `includeRepeats` parameter to exclude them. The method returns a Number representing the local time on the parent timeline.

```javascript
var tl = gsap.timeline();

//create a 1-second tween
var tween = gsap.to(e, { duration: 1, x: 100 });

//insert the tween at 0.5 seconds into the timeline
tl.add(tween, 0.5);

console.log(tween.endTime()); //1.5

//double the speed of the tween, thus it'll finish in half the normal time
tween.timeScale(2);

console.log(tween.endTime()); //1
```

--------------------------------

### GSAP v3: Callback Functions and Parameters

Source: https://gsap.com/docs/v3/GSAP/Tween

GSAP v3 allows you to define callback functions (onStart, onUpdate, onComplete, onRepeat, onReverseComplete) to execute at specific points in the animation lifecycle. You can also provide parameters for these callbacks using on*Params arrays.

```javascript
function handleComplete() {
  console.log("Animation complete!");
}

function handleUpdate(progress) {
  console.log("Animation progress: " + progress);
}

gsap.to(".myElement", {
  x: 100,
  duration: 1,
  onComplete: handleComplete,
  onCompleteParams: ["finished"],
  onUpdate: handleUpdate,
  onUpdateParams: [gsap.ticker.frame] // Example: passing current frame number
});
```

--------------------------------

### Include GSDevTools via CDN

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Includes the GSDevTools plugin from a CDN. This method is suitable for quick integration without a build process. Ensure the script tag is placed before your GSAP initialization code.

```html
<script src="https://cdn.jsdelivr.net/npm/gsap@3.14.1/dist/GSDevTools.min.js"></script>
```

--------------------------------

### Get Random Element from Array or Reusable Function (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/random%28%29

Selects a random element from a given array or returns a reusable function that picks a random element from the array each time it's called. This is useful for scenarios like randomly choosing colors or values.

```javascript
gsap.utils.random(["red", "blue", "green"]);

var random = gsap.utils.random([0, 100, 200], true);
console.log(random());
console.log(random());
```

--------------------------------

### Applying ScrollSmoother Effects with Data Attributes

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

This example shows how to use the `effects` property in ScrollSmoother to apply scroll-dependent animations. Elements with `data-speed` or `data-lag` attributes will automatically have effects applied. `data-speed` controls the scroll multiplier, while `data-lag` determines the delay for the element to catch up to the scroll position.

```javascript
gsap.registerPlugin(ScrollSmoother);

ScrollSmoother.create({
  wrapper: "#smooth-wrapper",
  content: "#smooth-content",
  effects: true, // Enables effects for elements with data-speed and data-lag
  smooth: 1 // Adjust the smoothing factor
});

// Example elements with effects:
// <div data-speed="0.5">...</div>
// <div data-lag="0.8">...</div>
```

--------------------------------

### Add Event Listener to Draggable Instance (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/Draggable/addEventListener%28%29

Registers a function to be called when a specific event occurs on a Draggable instance. Inside the listener, `this` refers to the Draggable's target element. This example demonstrates adding a 'press' event listener to animate the background color.

```javascript
var myDraggable = Draggable.create("#box1", {  bounds: "#container"})[0];
myDraggable.addEventListener("press", onPress);

function onPress() {
  console.log("myDraggable was pressed");
  gsap.to(this, {duration: 0.2, backgroundColor: "red"}); // animate the backgroundColor of the target of the Draggable that was pressed
}
```

--------------------------------

### restart()

Source: https://gsap.com/docs/v3/GSAP/Tween

Restarts and begins playing the tween forward from the beginning. This is useful for replaying an animation.

```APIDOC
## POST /docs/v3/GSAP/Tween/restart().md

### Description
Restarts and begins playing forward from the beginning.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/restart().md

### Parameters
#### Path Parameters
- **includeDelay** (Boolean) - Optional - Whether to include the delay.
- **suppressEvents** (Boolean) - Optional - Whether to suppress events.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **self** (self) - Returns self.

#### Response Example
N/A
```

--------------------------------

### Precompile SVG Morphs with GSAP MorphSVGPlugin

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Demonstrates how to use the 'precompile' option in MorphSVGPlugin to log and apply precompiled shape data for performance. This optimizes complex morphs by skipping initial calculations during the tween. Ensure the 'precompile' value is an array of strings representing the transformed shapes.

```javascript
gsap.to("#id", {
  duration: 1,
  morphSVG: { shape: "#otherID", precompile: "log" },
});

// now you can grab the value from the console and drop it in...
gsap.to("#id", {
  duration: 1,
  morphSVG: {
    shape: "#otherID",
    precompile: [
      "M0,0 C100,200 120,500 300,145 34,245 560,46",
      "M0,0 C200,300 100,400 230,400 100,456 400,300",
    ],
  },
});
```

--------------------------------

### Manually Refresh All ScrollTrigger Instances

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/refresh%28%29

This code snippet shows how to use the static ScrollTrigger.refresh() method to force all ScrollTrigger instances on the page to recalculate their start and end values. This is the most common approach to ensure all scroll-based animations are up-to-date, especially after layout changes or dynamic content loading.

```javascript
// Cause ALL ScrollTrigger instances to refresh using the static method:
ScrollTrigger.refresh();
```

--------------------------------

### Timeline Methods

Source: https://gsap.com/docs/v3/GSAP/Timeline

This section details various methods for interacting with GSAP Timelines, such as retrieving previous labels, managing timeline progress, accessing recent tweens, removing elements, and controlling repeat behavior.

```APIDOC
## GET /websites/gsap_v3/Timeline/previousLabel

### Description
Returns the previous label in the timeline from the provided `time`. If no `time` is provided, the timeline's current playhead time will be used.

### Method
GET

### Endpoint
/websites/gsap_v3/Timeline/previousLabel

### Parameters
#### Query Parameters
- **time** (Number) - Optional - The time from which to find the previous label.

### Response
#### Success Response (200)
- **label** (String) - The name of the previous label.

## GET /websites/gsap_v3/Timeline/progress

### Description
Gets or sets the timeline's progress, which is a value between 0 and 1 indicating the position of the virtual playhead (excluding repeats) where 0 is at the beginning, 0.5 is halfway complete, and 1 is complete.

### Method
GET/PUT

### Endpoint
/websites/gsap_v3/Timeline/progress

### Parameters
#### Query Parameters
- **value** (Number) - Optional - The progress value to set (between 0 and 1).
- **suppressEvents** (Boolean) - Optional - If true, events will not be dispatched.

### Response
#### Success Response (200)
- **progress** (Number) - The current progress of the timeline (if GET) or self (if PUT).

## GET /websites/gsap_v3/Timeline/recent

### Description
Returns the most recently added child tween/timeline/callback regardless of its position in the timeline.

### Method
GET

### Endpoint
/websites/gsap_v3/Timeline/recent

### Response
#### Success Response (200)
- **recentChild** (Tween | Timeline | Callback) - The most recently added child.

## DELETE /websites/gsap_v3/Timeline/remove

### Description
Removes a tween, timeline, callback, or label (or array of them) from the timeline.

### Method
DELETE

### Endpoint
/websites/gsap_v3/Timeline/remove

### Parameters
#### Request Body
- **value** (Tween | Timeline | Callback | Label | Array<Tween | Timeline | Callback | Label>) - Required - The tween, timeline, callback, or label to remove.

### Response
#### Success Response (200)
- **self** (self) - The timeline instance.

## DELETE /websites/gsap_v3/Timeline/removeLabel

### Description
Removes a label from the timeline and returns the time of that label.

### Method
DELETE

### Endpoint
/websites/gsap_v3/Timeline/removeLabel

### Parameters
#### Query Parameters
- **label** (String) - Required - The name of the label to remove.

### Response
#### Success Response (200)
- **time** (Number) - The time of the removed label.

## DELETE /websites/gsap_v3/Timeline/removePause

### Description
Removes pauses that were added to a timeline via its `.addPause()` method.

### Method
DELETE

### Endpoint
/websites/gsap_v3/Timeline/removePause

### Parameters
#### Query Parameters
- **position** (Number | Label) - Required - The position or label of the pause to remove.

### Response
#### Success Response (200)
- **self** (self) - The timeline instance.

## GET/PUT /websites/gsap_v3/Timeline/repeat

### Description
Gets or sets the number of times that the timeline should repeat after its first iteration.

### Method
GET/PUT

### Endpoint
/websites/gsap_v3/Timeline/repeat

### Parameters
#### Query Parameters
- **value** (Number) - Optional - The number of repeats.

### Response
#### Success Response (200)
- **repeatCount** (Number) - The number of repeats (if GET) or self (if PUT).

## GET/PUT /websites/gsap_v3/Timeline/repeatDelay

### Description
Gets or sets the amount of time in seconds between repeats.

### Method
GET/PUT

### Endpoint
/websites/gsap_v3/Timeline/repeatDelay

### Parameters
#### Query Parameters
- **value** (Number) - Optional - The delay in seconds.

### Response
#### Success Response (200)
- **delay** (Number) - The repeat delay in seconds (if GET) or self (if PUT).

## POST /websites/gsap_v3/Timeline/restart

### Description
Restarts and begins playing forward from the beginning.

### Method
POST

### Endpoint
/websites/gsap_v3/Timeline/restart

### Parameters
#### Query Parameters
- **includeDelay** (Boolean) - Optional - If true, any repeat delays will be included.
- **suppressEvents** (Boolean) - Optional - If true, events will not be dispatched.

### Response
#### Success Response (200)
- **self** (self) - The timeline instance.

```

--------------------------------

### Initialize ScrollSmoother with Minimal Configuration

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

Creates a ScrollSmoother instance with basic settings for smooth scrolling. The `smooth` property controls the duration of the catch-up effect, and `effects` enables parallax based on data attributes.

```javascript
ScrollSmoother.create({
	smooth: 1,
	effects: true
});
```

--------------------------------

### Animating ColorMatrixFilter Properties with GSAP

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

Illustrates how PixiPlugin simplifies animating properties like saturation, brightness, contrast, hue, and colorize, which are powered by PixiJS's ColorMatrixFilter. It also shows how to animate a custom ColorMatrixFilter instance.

```javascript
var image = new PIXI.Sprite.from(
  "http://pixijs.github.io/examples/required/assets/panda.png"
);
app.stage.addChild(image);

var tl = gsap.timeline({ defaults: { duration: 2 } });
//colorize fully red. Change colorAmount to 0.5 to make it only halfway colorized, for example:
tl.to(image, { pixi: { colorize: "red", colorizeAmount: 1 } })
  //change the hue 180 degrees (opposite)
  .to(image, { pixi: { hue: 180 } })
  //completely desaturate
  .to(image, { pixi: { saturation: 0 } })
  //blow out the brightness to double the normal amount
  .to(image, { pixi: { brightness: 2 } })
  //increase the contrast
  .to(image, { pixi: { contrast: 1.5 } });


var filter = new PIXI.filters.ColorMatrixFilter();
filter.sepia();
gsap.to(image, { pixi: { colorMatrixFilter: filter }, duration: 2 });
```

--------------------------------

### Get and Set Tween Total Duration (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/totalDuration%28%29

This snippet demonstrates how to use the totalDuration method in GSAP v3 to either retrieve the current total duration of a tween or set a new total duration. The method returns the tween instance for chaining when used as a setter.

```javascript
//gets total duration
var total = myTween.totalDuration();

//sets the total duration
myTween.totalDuration(10);
```

--------------------------------

### InertiaPlugin Configuration Options

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

Defines the various properties available within the InertiaPlugin's configuration object. These properties control the behavior of inertia-based tweens, such as initial velocity, boundary limits, snapping points, and resistance.

```javascript
{
  velocity: "auto" | Number, // Initial velocity in units per second
  min: Number,                 // Minimum end value
  max: Number,                 // Maximum end value
  end: Number | Array | Function, // Exact end value, snap-to values, or custom logic
  linkedProps: String,         // Comma-delimited list of properties to link for end function
  resistance: Number           // Resistance per second (friction)
}
```

--------------------------------

### ScrollTrigger Callbacks: onEnter

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

The `onEnter` callback function is executed when the scroll position moves forward past the ScrollTrigger's start point, typically when the trigger element scrolls into view. It receives the ScrollTrigger instance as an argument, providing access to properties like progress, direction, and isActive.

```javascript
ScrollTrigger.create({
  // ... other ScrollTrigger properties
  onEnter: ({ progress, direction, isActive }) => {
    console.log(progress, direction, isActive);
  }
});
```

--------------------------------

### Apply Clamped Speed Effects with data-speed="clamp()"

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

Using `data-speed="clamp(value)"` ensures that speed effects start from the element's native position if it's 'above the fold'. This prevents initial offset when elements are placed near the top of the page. It leverages ScrollTrigger's clamp() feature.

```html
<div data-speed="clamp(0.5)"></div>
<!-- clamped half-speed -->
```

--------------------------------

### GSAP Basic Tween with BackgroundSizePlugin Demo

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/bgSize

A CodePen embed showcasing a basic GSAP tween utilizing the `BackgroundSizePlugin`. This demo illustrates how the plugin enables animating `backgroundSize` to values like 'cover' or 'contain' responsively.

```html
<iframe src="https://codepen.io/GreenSock/embed/rNYxENg?default-tab=result&theme-id=41164" style="width:100%; height: 300px; border: none;"></iframe>
```

--------------------------------

### Set/Get Scroll Smoothing Duration with ScrollSmoother.smooth()

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/smooth%28%29

The .smooth() method allows you to get or set the duration (in seconds) for the scroll smoothing effect. When used as a setter, it accepts a Number representing the desired duration and returns the ScrollSmoother instance for chaining. When used as a getter, it returns the current duration.

```javascript
let smoother = ScrollSmoother.create({
  // ... other options
});

// Setter: Set the smoothing duration to 1.5 seconds
smoother.smooth(1.5);

// Getter: Get the current smoothing duration
let currentDuration = smoother.smooth();
console.log(currentDuration); // Outputs the current duration in seconds
```

--------------------------------

### Initialize ScrollSmoother with Detailed Configuration

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

Initializes ScrollSmoother with comprehensive settings, including smooth scrolling duration, enabling effects, and specifying a shorter smoothing time for touch devices. This configuration aims for a responsive and enhanced scrolling experience.

```javascript
// create the scrollSmoother before your scrollTriggers
ScrollSmoother.create({
	smooth: 1, // how long (in seconds) it takes to "catch up" to the native scroll position
	effects: true, // looks for data-speed and data-lag attributes on elements
	smoothTouch: 0.1 // much shorter smoothing time on touch devices (default is NO smoothing on touch devices)
});
```

--------------------------------

### ScrollTrigger Callbacks: onLeaveBack

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

The `onLeaveBack` callback function is executed when the scroll position moves backward past the ScrollTrigger's start point, typically when the trigger element scrolls out of view while scrolling up. It receives the ScrollTrigger instance as an argument, providing access to properties like progress, direction, and isActive.

```javascript
ScrollTrigger.create({
  // ... other ScrollTrigger properties
  onLeaveBack: ({ progress, direction, isActive }) => {
    console.log(progress, direction, isActive);
  }
});
```

--------------------------------

### Create MotionPathHelper from a GSAP Tween

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

This code demonstrates how to create an interactive MotionPathHelper instance by passing an existing GSAP tween that has a motionPath defined. The helper will then allow editing of that specific motion path.

```javascript
const tween = gsap.to("#id", {
  motionPath: {
    path: "#path",
    align: "#path",
    alignOrigin: [0.5, 0.5],
  },
});

// pass the tween instance in here...
MotionPathHelper.create(tween);
```

--------------------------------

### GSAP Utility: distribute

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `distribute` utility method distributes values among an array of objects, either linearly or based on a grid layout, with optional easing. It's useful for staggering animations or positioning elements evenly. It takes an array of objects and configuration options.

```javascript
const elements = [{}, {}, {}];
gsap.utils.distribute({
  base: 0,
  amount: 100,
  ease: "power1.inOut"
})(elements);
// This would return an array of values to be applied to each element.
```

--------------------------------

### Label Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Place an animation at a named label within the timeline. If the label does not exist, it will be added to the end of the timeline.

```javascript
tl.from(".class", { x: 100 }, "someLabel");
```

--------------------------------

### Resume Playback with GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Timeline/resume%28%29

The resume() method restarts playback of a GSAP Timeline or Tween without altering its current playback direction (forward or reversed). It returns the instance itself for method chaining. Note that if the timeScale is 0, it will be reset to 1 to allow playback.

```javascript
gsap.timeline().resume();

// Example handling timeScale of 0
let tl = gsap.timeline({
  paused: true
});
tl.to("#element", { x: 100 });
tl.timeScale(0);
tl.resume(); // timeScale becomes 1

// Alternative for timeScale 0
tl.timeScale(tl.timeScale() || 0.001).resume();
```

--------------------------------

### Convert Local Time to Global Time with GSAP globalTime()

Source: https://gsap.com/docs/v3/GSAP/Timeline/globalTime%28%29

The globalTime(localTime) method converts a local time value to its equivalent on the GSAP global timeline. It accounts for all nesting, time scales, and other factors. By default, it uses the animation's totalTime if no localTime is provided. This is useful for understanding where a nested timeline's start time (0) would appear on the global timeline.

```javascript
gsap.globalTimeline.globalTime(localTime);
// Example: Convert the start time (0) of a nested timeline to global time
const nestedTimeline = gsap.timeline({
  paused: true
});
const animation = gsap.to(myElement, { duration: 1, x: 100 });
nestedTimeline.add(animation);

const globalStartTime = nestedTimeline.globalTime(0);
console.log("Local start time 0 corresponds to global time:", globalStartTime);

// Example: Get the global time equivalent of the nested timeline's total duration
const globalTotalTime = nestedTimeline.globalTime(); // Equivalent to nestedTimeline.globalTime(nestedTimeline.totalDuration())
console.log("Local total duration corresponds to global time:", globalTotalTime);
```

--------------------------------

### Revert Animation and Remove Inline Styles with GSAP revert()

Source: https://gsap.com/docs/v3/GSAP/Timeline/revert%28%29

The revert() method on GSAP Timelines and Tweens removes inline styles that were added during the animation. This ensures elements return to their original state, respecting CSS rules like media queries, unlike progress(0) which only resets to the animation's starting values.

```javascript
let tl = gsap.timeline();
tl.to(".box", { opacity: 0 });

// To revert and remove inline styles:
tl.revert();
```

--------------------------------

### GSAP v3 Utility Methods

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

This section covers the utility methods provided by GSAP v3, which offer helpful functions for common tasks in animation and general JavaScript development.

```APIDOC
## pipe()

### Description
Sequences a number of function calls, passing the result of each into the next.

### Method
Utility Function

### Endpoint
`gsap.utils.pipe(...functions)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Sequence clamp and snap functions
const clampedAndSnapped = gsap.utils.pipe(gsap.utils.clamp(0, 100), gsap.utils.snap(5));
const result = clampedAndSnapped(8);
console.log(result); // Output: 10
```

### Response
#### Success Response (200)
Returns a function that executes the piped functions in order.

#### Response Example
```json
{
  "example": "Function that returns the final result after all piped functions are executed."
}
```

## random()

### Description
Generates a random number within a specified range or randomly picks an element from an array.

### Method
Utility Function

### Endpoint
`gsap.utils.random(min, max, [increment])` or `gsap.utils.random(array)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Random number between 0 and 100, with increments of 5
const randomNumber = gsap.utils.random(0, 100, 5);
console.log(randomNumber); // Output: e.g., 65

// Example: Randomly pick an element from an array
const randomColor = gsap.utils.random(['red', 'green', 'blue']);
console.log(randomColor); // Output: e.g., "red"
```

### Response
#### Success Response (200)
Returns a random number or a randomly selected element from the array.

#### Response Example
```json
{
  "example": "A random number or a string/element from the input array."
}
```

## selector()

### Description
Returns a selector function that is scoped to a particular Element.

### Method
Utility Function

### Endpoint
`gsap.utils.selector(element)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Get a selector function scoped to a specific element
const myElement = document.getElementById('myContainer');
const scopedSelector = gsap.utils.selector(myElement);

// Now use the scoped selector to find elements within myElement
const buttonsInside = scopedSelector('button');
console.log(buttonsInside);
```

### Response
#### Success Response (200)
Returns a function that can be used to select elements within the specified scope.

#### Response Example
```json
{
  "example": "Function that takes a CSS selector string and returns matching elements within the scoped element."
}
```

## shuffle()

### Description
Shuffles the contents of an array in-place.

### Method
Utility Function

### Endpoint
`gsap.utils.shuffle(array)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Shuffle an array of numbers
const numbers = [1, 2, 3, 4, 5];
gsap.utils.shuffle(numbers);
console.log(numbers); // Output: e.g., [4, 2, 1, 5, 3]
```

### Response
#### Success Response (200)
Modifies the input array in-place with shuffled elements.

#### Response Example
```json
{
  "example": "The original array, now with its elements shuffled."
}
```

## snap()

### Description
Snaps a value to either an increment or to the closest value in an array.

### Method
Utility Function

### Endpoint
`gsap.utils.snap(increment | array, value)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Snap to an increment of 5
const snappedToIncrement = gsap.utils.snap(5, 13);
console.log(snappedToIncrement); // Output: 15

// Example: Snap to the closest value in an array
const snappedToArray = gsap.utils.snap([0, 5, 10], 7);
console.log(snappedToArray); // Output: 5
```

### Response
#### Success Response (200)
Returns the value snapped to the specified increment or array.

#### Response Example
```json
{
  "example": "The snapped numerical value."
}
```

## splitColor()

### Description
Splits any color into its red, green, blue (and optionally alpha) components, or hue, saturation, and brightness.

### Method
Utility Function

### Endpoint
`gsap.utils.splitColor(color, [rgb], [unpack])`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Split a color into RGB components
const rgbComponents = gsap.utils.splitColor('red');
console.log(rgbComponents); // Output: [255, 0, 0]

// Example: Split a color into HSB components
const hsbComponents = gsap.utils.splitColor('#00ff00', false, true);
console.log(hsbComponents); // Output: e.g., [120, 100, 100]
```

### Response
#### Success Response (200)
Returns an array containing the color components (RGB or HSB).

#### Response Example
```json
{
  "example": "An array of numbers representing color components."
}
```

## toArray()

### Description
Converts almost any array-like object to an array, including selector text.

### Method
Utility Function

### Endpoint
`gsap.utils.toArray(targets)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Convert a CSS selector to an array of elements
const elements = gsap.utils.toArray('.my-class');
console.log(elements); // Output: [element1, element2]

// Example: Convert an existing array (no change)
const existingArray = [1, 2, 3];
const arrayResult = gsap.utils.toArray(existingArray);
console.log(arrayResult); // Output: [1, 2, 3]
```

### Response
#### Success Response (200)
Returns an array containing the target elements or values.

#### Response Example
```json
{
  "example": "An array of DOM elements or other values."
}
```

## unitize()

### Description
Wraps around another utility function, allowing it to accept values with units, stripping the unit before processing and adding it back to the result.

### Method
Utility Function

### Endpoint
`gsap.utils.unitize(callback, unit)`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Unitize a wrap function to handle pixel values
const wrapAround = gsap.utils.wrap(0, 100);
const unitizedWrap = gsap.utils.unitize(wrapAround);

const resultPx = unitizedWrap('150px');
console.log(resultPx); // Output: "50px"

// Example: Force a specific unit
const mapRange = gsap.utils.mapRange(-10, 10, 0, 100);
const unitizedMap = gsap.utils.unitize(mapRange, '%');

const resultPercent = unitizedMap(5);
console.log(resultPercent); // Output: "75%"
```

### Response
#### Success Response (200)
Returns a function that handles unitized values.

#### Response Example
```json
{
  "example": "A function that accepts values with units, processes them, and returns a result with the specified unit."
}
```

## wrap()

### Description
Returns the next item in an array or number in a range after the given index. Can also return a function that performs this wrapping.

### Method
Utility Function

### Endpoint
`gsap.utils.wrap(min, max, [index])` or `gsap.utils.wrap(array, [index])`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Wrap a number within a range
const wrappedNumber = gsap.utils.wrap(0, 10, 12);
console.log(wrappedNumber); // Output: 2

// Example: Wrap an element from an array
const colors = ['red', 'green', 'blue'];
const wrappedColor = gsap.utils.wrap(colors, 4);
console.log(wrappedColor); // Output: "red"

// Example: Get a reusable wrapping function
const wrapInRange = gsap.utils.wrap(0, 5);
const nextValue = wrapInRange(3);
console.log(nextValue); // Output: 4
```

### Response
#### Success Response (200)
Returns the wrapped value or a wrapping function.

#### Response Example
```json
{
  "example": "A number within the specified range or an element from the array, or a function that performs wrapping."
}
```

## wrapYoyo()

### Description
Returns an element from an array or a number in a range, going backwards once the last index is reached (yoyo-ing). Can also return a reusable function.

### Method
Utility Function

### Endpoint
`gsap.utils.wrapYoyo(min, max, [index])` or `gsap.utils.wrapYoyo(array, [index])`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Example: Yoyo wrap a number within a range
const yoyoWrappedNumber = gsap.utils.wrapYoyo(0, 5, 7);
console.log(yoyoWrappedNumber); // Output: 3

// Example: Yoyo wrap an element from an array
const letters = ['a', 'b', 'c'];
const yoyoWrappedLetter = gsap.utils.wrapYoyo(letters, 4);
console.log(yoyoWrappedLetter); // Output: "b"

// Example: Get a reusable yoyo wrapping function
const yoyoWrap = gsap.utils.wrapYoyo(0, 3);
const nextYoyoValue = yoyoWrap(2);
console.log(nextYoyoValue); // Output: 1
```

### Response
#### Success Response (200)
Returns the yoyo-wrapped value or a yoyo-wrapping function.

#### Response Example
```json
{
  "example": "A number within the specified range or an element from the array, with yoyo behavior, or a function that performs yoyo wrapping."
}
```
```

--------------------------------

### Add Label to GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/addLabel%28%29

Adds a named label to a GSAP timeline at a specified position. This allows for easy referencing of points in the timeline for seeking, adding tweens, or reversing animations. The position parameter is flexible, accepting numbers, strings (other labels), '<' (start of previous animation), '>' (end of previous animation), or complex relative strings with '+=' and '-=' prefixes.

```javascript
tl.addLabel("myLabel", 3);
// or
tl.addLabel("myLabel", "someLabel");
// or
tl.addLabel("myLabel", "<");
// or
tl.addLabel("myLabel", ">");
// or
tl.addLabel("myLabel", "+=1");
// or
tl.addLabel("myLabel", "myLabel+=2");
// or
tl.addLabel("myLabel", "<25%");
```

--------------------------------

### InertiaPlugin Options

Source: https://gsap.com/docs/v3/Plugins/Draggable

Configuration options for the InertiaPlugin to control momentum-based motion after release.

```APIDOC
## InertiaPlugin Options

### Description
These options control the behavior of inertia-based motion when using the InertiaPlugin with Draggable.

### Method
N/A (Configuration options)

### Endpoint
N/A (Configuration options)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
* **throwResistance** (Number) - Optional - A number (1000 by default) that controls how much resistance or friction there is when the mouse/touch is released and momentum-based motion is enabled. Larger values increase resistance and deceleration.
* **maxDuration** (Number) - Optional - The maximum duration (in seconds) that the kinetic-based inertia tween can last. Defaults to 10 seconds.
* **minDuration** (Number) - Optional - The minimum duration (in seconds) that the kinetic-based inertia tween should last. Defaults to 0.2 seconds.
* **overshootTolerance** (Number) - Optional - Affects how much overshooting is allowed before smoothly returning to the resting position. Defaults to 1. Set to 0 to disallow overshooting.

### Request Example
```json
{
  "throwResistance": 1500,
  "maxDuration": 5,
  "minDuration": 0.5,
  "overshootTolerance": 0.5
}
```

### Response
#### Success Response (200)
N/A (Configuration options)

#### Response Example
N/A (Configuration options)
```

--------------------------------

### Get SVG Stroke Position with DrawSVGPlugin.getPosition

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin/static

This JavaScript function retrieves the current position of an SVG element's stroke using GSAP's DrawSVGPlugin. It takes an SVG element or its selector text as input and returns the stroke's position. This is useful for animations and progress tracking.

```javascript
function getPercentage(element) {
  return Math.floor(
    DrawSVGPlugin.getPosition(element)[1] /
      (DrawSVGPlugin.getLength(element) / 100)
  );
}
```

--------------------------------

### GSAP Draggable: Implementing Auto-Scrolling Near Edges

Source: https://gsap.com/docs/v3/Plugins/Draggable

Enables automatic scrolling of a container when the draggable element is near its edges. The `autoScroll` property accepts a number to control the scroll speed (e.g., 1 for normal, 2 for double). The scrolling speed increases as the draggable gets closer to the edge.

```javascript
Draggable.create("#myElement", {
  autoScroll: 1
});
```

--------------------------------

### GSAP MorphSVG Tween with updateTarget disabled (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

This example shows how to configure a GSAP MorphSVG tween to disable updating the original SVG target element. This is useful when the animation is solely for rendering to a different context, like canvas, and modifying the original SVG is unnecessary. The 'updateTarget: false' option within the morphSVG configuration achieves this.

```javascript
gsap.to("#diamond", {
  duration: 2,
  morphSVG: {
    shape: "#lightning",
    render: draw,
    updateTarget: false,
  },
});
```

--------------------------------

### Get Element Position in Viewport with ScrollTrigger (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Calculates and returns a normalized value representing an element's position within the viewport. This is useful for triggering animations based on scroll position. It takes an element or its selector and an optional reference point (e.g., 'top', 'center', 'bottom') or numeric value. The output is a number between 0 and 1.

```javascript
ScrollTrigger.positionInViewport(element, "top");
```

--------------------------------

### Kill Specific Properties for Multiple Targets - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/kill%28%29

This code shows how to kill a specific property ('opacity') for multiple target objects ('myObject1' and 'myObject2') using the kill() method. Selector text can also be used.

```javascript
// kill only the "opacity" properties of animations of the targets "myObject1" and "myObject2":
animation.kill([myObject1, myObject2], "opacity"); //you could use selector text instead, like ".class1, .class2"
```

--------------------------------

### Convert Timeline Label to Scroll Position with GSAP

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/labelToScroll%28%29

This JavaScript code snippet demonstrates how to use the .labelToScroll() method to get the scroll position of a timeline label. It's typically used within an event listener, like a button click, to smoothly scroll the window to that specific label's position on the page. This requires GSAP and its ScrollTrigger plugin to be included.

```javascript
btn.addEventListener("click", () => {
  gsap.to(window, { scrollTo: tl.scrollTrigger.labelToScroll("myLabel") });
});
```

--------------------------------

### Animate to Current State with Flip.from()

Source: https://gsap.com/docs/v3/Plugins/Flip

Animates the transition from a previously captured state to the element's current state. It immediately repositions elements to their old state and then animates the removal of those offsets. Accepts standard tween properties and returns a timeline.

```javascript
Flip.from(state, {
  duration: 1,
  ease: "power1.inOut",
  absolute: true,
  onComplete: myFunc,
});
```

--------------------------------

### Set Default zIndex in GSAP v3

Source: https://gsap.com/docs/v3/Plugins/Draggable/zIndex

This code snippet demonstrates how to set the static zIndex property for GSAP's Draggable plugin. This value determines the starting z-index for elements that become draggable, ensuring they stack correctly when interacted with. It's a global setting that affects all subsequent Draggable instances unless overridden.

```javascript
Draggable.zIndex = 500;
```

--------------------------------

### Animate All Pseudo-elements of a Type with CSSRulePlugin

Source: https://gsap.com/docs/v3/Plugins/CSSRulePlugin

Illustrates how to use `CSSRulePlugin.getRule()` to select all instances of a pseudo-element (e.g., all `::before` pseudo-elements on the page) and animate a common property across them. The animation targets are wrapped in a `cssRule` object.

```javascript
gsap.to( CSSRulePlugin.getRule("::before"), {duration: 3, cssRule: {color: "blue"}});>
```

--------------------------------

### Configure Inertia Plugin with Custom Live Snap Function

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet illustrates using a custom function within 'liveSnap.points' to implement advanced snapping logic. The function receives a point and can return a modified point based on custom rules.

```javascript
Draggable.create(element, {
  inertia: true,
  liveSnap: {
    points: function(point) {
      // Custom snapping logic here
      return newPoint;
    }
  }
});
```

--------------------------------

### Convert to Array using gsap.utils.toArray

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/toArray%28%29

Demonstrates how to use gsap.utils.toArray to convert different types of inputs (selector text, elements, arrays of selectors) into a flat Array. The method supports an optional scope parameter to limit selector text searches to descendants of a specific element.

```javascript
let targets = gsap.utils.toArray(".class");
```

```javascript
let targets = gsap.utils.toArray(myElement);
```

```javascript
let targets = gsap.utils.toArray([".class1", ".class2"]);
```

```javascript
let targets = gsap.utils.toArray(".class", myElement);
```

--------------------------------

### Configure Inertia Plugin with Snap Array

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet shows how to use an array of values to define snapping points for the InertiaPlugin. The plugin will automatically select the closest value from the provided array as the element's final resting position.

```javascript
Draggable.create(element, {
  inertia: true,
  snap: [10, 50, 200, 450]
});
```

--------------------------------

### Find Nested Label Time in GSAP Timeline (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/getNestedLabelTime

This JavaScript function iterates through child timelines to find a specified label within a nested structure. It then calculates the absolute time of that label on the parent timeline, accounting for start times and time scales of intermediate timelines. This is useful for seeking to specific points in complex, nested animation structures.

```javascript
function getNestedLabelTime(timeline, label) {
  let children = timeline.getChildren(true, false, true),
    i = children.length,
    tl,
    time;
  while (i--) {
    if (label in children[i].labels) {
      tl = children[i];
      time = tl.labels[label];
      break;
    }
  }
  if (tl) {
    while (tl !== timeline) {
      time = tl.startTime() + time / tl.timeScale();
      tl = tl.parent;
    }
  }
  return time;
}
```

--------------------------------

### GSAP Tween Control with Variables

Source: https://gsap.com/docs/v3/GSAP/Tween

Shows how to create a tween and assign it to a variable for later control. This allows pausing, seeking, setting progress, and playing the animation. It requires the GSAP library.

```javascript
let tween = gsap.to(".class", { rotation: 360, duration: 5, ease: "elastic" });

tween.pause();
tween.seek(2);
tween.progress(0.5);
tween.play();
```

--------------------------------

### GSAP v3 Default Easing Configuration

Source: https://gsap.com/docs/v3/Eases

Demonstrates how to set default easing and duration for all GSAP tweens using gsap.defaults(). It also shows how to set defaults for specific timelines.

```javascript
gsap.defaults({
  ease: "power2.in",
  duration: 1,
});

gsap.timeline({defaults: {ease: "power2.in"}})

```

--------------------------------

### MorphSVG Configuration with Precision

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Demonstrates how to set the 'precision' property in MorphSVG to control the number of decimal places for the resulting path data. This can be used to balance performance and visual accuracy.

```javascript
gsap.to("#id", { morphSVG: { shape: "#other-id", precision: 5 } });
```

--------------------------------

### resume() Method

Source: https://gsap.com/docs/v3/GSAP/Tween/resume%28%29

The resume() method in GSAP v3 allows you to resume playing an animation that has been paused, without altering its current direction (forward or reversed).

```APIDOC
## resume()

### Description
Resumes playing an animation without altering its direction (forward or reversed).

### Method
`resume()`

### Parameters
This method does not accept any parameters.

### Returns
`self` - Returns the animation instance itself, enabling easier chaining of methods.

### Details
When `resume()` is called, the animation will continue from its current state. If the animation's `timeScale` is 0 when `resume()` is invoked, it will be automatically set to 1 to ensure playback. To avoid an abrupt jump from 0 to 1, you can set a very small `timeScale` before calling `resume()`, for example: `myAnimation.timeScale(myAnimation.timeScale() || 0.001).resume()`.

### Request Example
```javascript
// Assuming 'myAnimation' is a GSAP tween or timeline
myAnimation.pause(); // Pause the animation
// ... later ...
myAnimation.resume(); // Resume the animation

// Example to handle timeScale of 0:
myAnimation.timeScale(0).pause();
// ... later ...
myAnimation.timeScale(myAnimation.timeScale() || 0.001).resume();
```

### Response
#### Success Response
- `self` (object) - The animation instance for chaining.
```

--------------------------------

### resume()

Source: https://gsap.com/docs/v3/GSAP/Tween

Resumes playing the tween without altering its direction (forward or reversed). This allows for pausing and resuming animations.

```APIDOC
## POST /docs/v3/GSAP/Tween/resume().md

### Description
Resumes playing without altering direction.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/resume().md

### Parameters
N/A

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **self** (self) - Returns self.

#### Response Example
N/A
```

--------------------------------

### Customized RoughEase Animation

Source: https://gsap.com/docs/v3/Eases/RoughEase

Illustrates how to customize the RoughEase effect by providing specific configuration properties. This allows for fine-tuning the roughness, points, randomization, taper, and template ease.

```javascript
//or customize the configuration
gsap.to(element, {duration: 2, y: 300, ease: "rough({strength: 3, points: 50, template: strong.inOut, taper: both, randomize: false})" });
```

--------------------------------

### shiftChildren Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/shiftChildren%28%29

Shifts the startTime of the timeline's children by a certain amount and optionally adjusts labels too. This can be useful when you want to prepend children or splice them into a certain spot, moving existing ones back to make room for the new ones.

```APIDOC
## shiftChildren

### Description
Shifts the startTime of the timeline's children by a certain amount and optionally adjusts labels too. This can be useful when you want to prepend children or splice them into a certain spot, moving existing ones back to make room for the new ones.

### Method
`shiftChildren`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
timeline.shiftChildren(1.0, true, 0.5);
```

### Response
#### Success Response (200)
Returns `self` for chaining.

#### Response Example
```javascript
// Returns the timeline instance for chaining
```

### Parameters Details
* **amount** (Number) - Required - Number of seconds (or frames for frames-based timelines) to move each child.
* **adjustLabels** (Boolean) - Optional - If `true`, the timing of all labels will be adjusted as well. (default = `false`)
* **ignoreBeforeTime** (Number) - Optional - All children that begin at or after the `startAtTime` will be affected by the shift (the default is 0, causing all children to be affected). This provides an easy way to splice children into a certain spot on the timeline, pushing only the children after that point back to make room. (default = `0`)
```

--------------------------------

### Observer Configuration: Event Capture Phase

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Enables the use of the capture phase for touch and pointer event listeners. Setting `capture: true` is equivalent to using `addEventListener(type, func, {capture: true})`.

```javascript
Observer.create({
  capture: true
});
```

--------------------------------

### Create a tween to scrub timeline between labels

Source: https://gsap.com/docs/v3/GSAP/Timeline/tweenFromTo%28%29

This snippet demonstrates how to use tweenFromTo to scrub a GSAP timeline between two named labels. It's ideal for sequencing animations where the duration is determined immediately.

```javascript
var master = gsap.timeline();
master.add(tl.tweenFromTo("myLabel1", "myLabel2"));
master.add(tl.tweenFromTo("myLabel2", 0));
```

--------------------------------

### Draggable enable()

Source: https://gsap.com/docs/v3/Plugins/Draggable/enable%28%29

Enables a Draggable instance, allowing it to be dragged. Returns the Draggable instance for chaining.

```APIDOC
## enable()

### Description
Enables the Draggable instance, making it draggable.

### Method
`enable()`

### Endpoint
N/A (This is a method call on a Draggable instance)

### Parameters
None

### Request Example
```javascript
const draggables = Draggable.create(".box", {
  type: "x,y"
});

draggables[0].enable(); // Enables the first Draggable instance
```

### Response
#### Success Response
Returns the Draggable instance itself, enabling method chaining.

#### Response Example
```javascript
// Assuming draggables[0] is a Draggable instance
const enabledDraggable = draggables[0].enable();
console.log(enabledDraggable === draggables[0]); // true
```
```

--------------------------------

### Register GSAP Observer Plugin

Source: https://gsap.com/docs/v3/Plugins/Observer

This code snippet shows how to register the Observer plugin with GSAP, making its functionality available for use in your project. This is typically the first step before creating an Observer instance.

```javascript
gsap.registerPlugin(Observer)
```

--------------------------------

### Handle Units with Unitize() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The unitize() method wraps around another utility function, allowing it to accept values with units (like "20px" or "50%"). It strips the unit before passing the value to the wrapped function and adds it back to the result. It can also force a specific unit. This method is part of GSAP's utility methods.

```javascript
const wrap = gsap.utils.unitize(gsap.utils.wrap(0, 100));
wrap("150px"); // Output: "50px"

const mapRange = gsap.utils.mapRange(-10, 10, 0, 100);
const unitizedMap = gsap.utils.unitize(mapRange, "%");
unitizedMap(5); // Output: "75%"
```

--------------------------------

### GSAP Shorthand Transforms and Properties

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/CSS

Demonstrates common GSAP v3 shorthand properties for transforms and other animation-related settings, mapping them to their CSS equivalents. This provides a quick lookup for developers.

```javascript
gsap.to(element, {
  x: 100, // transform: translateX(100px)
  y: 100, // transform: translateY(100px)
  xPercent: 50, // transform: translateX(50%)
  yPercent: 50, // transform: translateY(50%)
  scale: 2, // transform: scale(2)
  scaleX: 2, // transform: scaleX(2)
  scaleY: 2, // transform: scaleY(2)
  rotation: 90, // transform: rotate(90deg)
  rotation: "1.25rad", // transform: rotate(1.25rad)
  skew: 30, // transform: skew(30deg)
  skewX: 30, // transform: skewX(30deg)
  skewY: "1.23rad", // transform: skewY(1.23rad)
  transformOrigin: "center 40%", // transform-origin: center 40%
  opacity: 0, // adjust the element's opacity
  autoAlpha: 0, // shorthand for opacity & visibility
  duration: 1, // animation-duration: 1s
  repeat: -1, // animation-iteration-count: infinite
  repeat: 2, // animation-iteration-count: 3
  delay: 2, // animation-delay: 2s
  yoyo: true // animation-direction: alternate
});
```

--------------------------------

### Restart Animation (GSAP v3)

Source: https://gsap.com/docs/v3/GSAP/Timeline/restart%28%29

Restarts an animation from the beginning. The 'includeDelay' parameter controls whether to honor the initial delay, and 'suppressEvents' prevents callbacks during the restart. Returns the animation instance for chaining.

```javascript
tl.restart();
tl.restart(true, false);
```

--------------------------------

### Enable and Offset Auto Rotation

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This snippet demonstrates enabling `autoRotate` to make the element follow the path's angle. It also shows how to offset the rotation by a specific degree value (e.g., 90 degrees).

```javascript
autoRotate: true
// or with an offset:
autoRotate: 90
```

--------------------------------

### GSAP Observer: Accessing Callback Data

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Demonstrates how to access observer instance properties within the onChange callback function. This allows you to log velocity, delta, target element, and the last event.

```javascript
Observer.create({
  ...
  onChange: (self) =>  {
    console.log("velocity:", self.velocityX, self.velocityY, "delta:", self.deltaX, self.deltaY, "target element:", self.target, "last event:", self.event);
  }
});
```

--------------------------------

### Accessing SplitText Configuration with .vars

Source: https://gsap.com/docs/v3/Plugins/SplitText/vars

Demonstrates how to access the configuration object (`vars`) of a SplitText instance after its creation. This object contains the initial settings like `type` and `wordsClass` and can be logged to the console.

```javascript
let splitText = SplitText.create({
  type: "chars,words",
  wordsClass: "word++",
});

console.log(splitText.vars);
```

--------------------------------

### GSAP Timeline Control Methods

Source: https://gsap.com/docs/v3/GSAP

Demonstrates common control methods for GSAP Timeline instances. These methods allow for pausing, playing, seeking, and manipulating the playback progress and speed of animations within a timeline.

```javascript
var tween = gsap.to(...);
var tl = gsap.timeline(); //"tl" short for timeline
tl.to(...).to(...); //add animations.

//now we can control them...
tween.pause();
tween.timeScale(2); //double speed
tl.seek(3); //jump to 3 seconds in
tl.progress(0.5); //halfway through
...
```

--------------------------------

### Integrating Animations with onSplit Callback

Source: https://gsap.com/docs/v3/Plugins/SplitText

Shows how to return a GSAP animation from the `onSplit` callback. The animation's total time and revert functionality are automatically managed by SplitText, ensuring seamless transitions.

```javascript
const split = new SplitText("#myElement", {
  onSplit: function() {
    const tl = gsap.timeline();
    tl.from(split.chars, { opacity: 0, duration: 0.5 });
    return tl; // Return the timeline to be managed by SplitText
  }
});
```

--------------------------------

### Animate Transforms with GSAP Aliases

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/CSS

Illustrates animating transform properties using GSAP's built-in aliases for better performance and cross-browser compatibility. It contrasts this with animating the 'transform' string directly.

```javascript
gsap.to(element, {
  // writing out the transform string 🔥
  // transform: "translate(-50%,-50%)"
  xPercent: -50,
  yPercent: -50,
});
```

--------------------------------

### GSAP v3: Random Values for Animation Properties (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/gsap

Demonstrates how to use GSAP's random value feature to animate properties with random values for each target. This includes random numbers within a range (optionally rounded to an increment) and random selection from an array. It simplifies creating randomized visual effects.

```javascript
gsap.to(".class", {
  // chooses a random number between -100 and 100
  // for each target, rounding to the closest 5!
  x: "random(-100, 100, 5)"
});

gsap.to(".class", {
  x: "random([0, 100, 200, 500])" // randomly selects one of the values (0, 100, 200, or 500)
});
```

--------------------------------

### MotionPathPlugin.getAlignMatrix

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Retrieves a Matrix2D for aligning elements between coordinate spaces, considering all transforms.

```APIDOC
## MotionPathPlugin.getAlignMatrix

### Description
Gets a Matrix2D for translating between coordinate spaces, typically so that you can move the `fromElement` to align it with the `toElement` while factoring in all transforms (even nested ones). The matrix allows you to convert any point/coordinate using its apply() method.

### Method
STATIC

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
*   **fromElement** (Element | window) - The source element.
*   **toElement** (Element | window) - The target element.
*   **fromOrigin** (Array) - The origin point in the `fromElement`'s coordinate space (e.g., `[x, y]`).
*   **toOrigin** (Array | String) - The origin point in the `toElement`'s coordinate space (e.g., `[x, y]`) or a string like "50% 50%".

### Request Example
```json
{
  "fromElement": document.getElementById('elementA'),
  "toElement": document.getElementById('elementB'),
  "fromOrigin": [0, 0],
  "toOrigin": ["50%", "50%"]
}
```

### Response
#### Success Response (200)
*   **Matrix2D** (Object) - A Matrix2D object with an `apply()` method for coordinate conversion.

#### Response Example
```json
{
  "a": 1, "b": 0, "c": 0, "d": 1, "e": 10, "f": 20,
  "apply": function(point) { /* ... */ }
}
```
```

--------------------------------

### Create a reusable clamp function

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/clamp%28%29

This method returns a reusable function that remembers the minimum and maximum values. This is efficient for repeatedly clamping values within the same range without redefining the boundaries each time. The returned function accepts a single number to clamp.

```javascript
var clamper = gsap.utils.clamp(0, 100);

console.log(clamper(105)); // 100
console.log(clamper(-50)); // 0
console.log(clamper(20)); // 20
```

--------------------------------

### Complex Data Transformations using GSAP pipe()

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/pipe%28%29

Illustrates a powerful use case of pipe() by combining several reusable GSAP utility functions (clamp, mapRange, snap) to perform a series of data transformations on a single input value. This creates a reusable 'transformer' function for complex operations.

```javascript
// get a clamping function that will always clamp to a range between 0 and 100
var transformer = gsap.utils.pipe(
  // clamp between 0 and 100
  gsap.utils.clamp(0, 100),

  // then map to the corresponding position on the width of the screen
  gsap.utils.mapRange(0, 100, 0, window.innerWidth),

  // then snap to the closest increment of 20
  gsap.utils.snap(20)
);

// now we feed one value in and it gets run through ALL those transformations!:
transformer(25.874);
```

--------------------------------

### Inertia Plugin Configuration for Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

Configures inertia-based motion after a drag release. Requires InertiaPlugin and setting `inertia: true`. Options control resistance, maximum and minimum tween durations, and overshoot tolerance.

```javascript
Draggable.create(element, {
  inertia: true,
  throwResistance: 1000, // Default value, controls friction on release
  maxDuration: 10,     // Default value, caps the inertia tween duration
  minDuration: 0.2,    // Default value, ensures a minimum inertia tween duration
  overshootTolerance: 1 // Default value, allows temporary overshoot of bounds
});
```

--------------------------------

### Use Tracked Properties in throwProps Tween (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/VelocityTracker/.track

Demonstrates how to utilize properties automatically tracked by InertiaPlugin.track() within a GSAP throwProps tween. By setting the target property to "auto", the tween will use the internally calculated velocity to glide the property to a stop. This eliminates the need for manual velocity calculation, simplifying motion tweens.

```javascript
// Track 'x' and 'y' properties first:
InertiaPlugin.track(obj, "x,y");

// Then, after at least 100ms, smoothly tween to EXACTLY x:200, y:300
gsap.to(obj, {
  duration: 2,
  throwProps: {
    x: { end: 200 },
    y: { end: 300 }
  },
  ease: "Strong.easeOut"
});

// To have obj.x and obj.y glide to a stop based on velocity:
gsap.to(obj, {
  duration: 2,
  throwProps: {
    x: "auto",
    y: "auto"
  },
  ease: "Strong.easeOut"
});
```

--------------------------------

### String Format for Custom Bounce Ease (JavaScript)

Source: https://gsap.com/docs/v3/Eases/CustomBounce

Illustrates how to use GSAP's condensed string formatting to define custom bounce eases directly within tween properties. This allows for inline definition of basic and advanced bounce parameters.

```javascript
ease: "bounce(0.5)"; //easy!
ease: "bounce({strength:0.5, endAtStart:true})"; //advanced
```

--------------------------------

### Complex Relative Positioning with Offsets in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Uses '+' and '-' prefixes with numbers or percentages to define positions relative to the end of the timeline, a label, or the start/end of the previous animation. This allows for precise overlaps or gaps.

```javascript
// 1 second past the end of the timeline
tl.fromTo(".class", { x: 100 }, { x: 200 }, "+=1");

// 1 second before the end of the timeline (overlaps)
tl.fromTo(".class", { x: 100 }, { x: 200 }, "-=1");

// 2 seconds past the label "myLabel"
tl.fromTo(".class", { x: 100 }, { x: 200 }, "myLabel+=2");

// 3 seconds past the start of the previous animation
tl.fromTo(".class", { x: 100 }, { x: 200 }, "<+=3");

// 0.5 seconds before the end of the previous animation
tl.fromTo(".class", { x: 100 }, { x: 200 }, ">-0.5");

// Overlap by 25% of the inserting animation's duration
tl.fromTo(".class", { x: 100 }, { x: 200 }, "-=25%");

// 25% into the previous animation (from its start)
tl.fromTo(".class", { x: 100 }, { x: 200 }, "<25%");

// 30% of the inserting animation's duration past the label "myLabel"
tl.fromTo(".class", { x: 100 }, { x: 200 }, "myLabel+=30%");
```

--------------------------------

### Observer Plugin Properties

Source: https://gsap.com/docs/v3/Plugins/Observer

This section details the properties available on the GSAP v3 Observer plugin instance.

```APIDOC
## Observer Plugin Properties

### Description

Details the properties accessible on an Observer instance, providing information about the observed element, configuration, and motion.

### Method

N/A (Properties of an object instance)

### Endpoint

N/A (Properties of an object instance)

### Parameters

#### Path Parameters

N/A

#### Query Parameters

N/A

#### Request Body

N/A

### Request Example

N/A

### Response

#### Success Response (200)

- **target** (Element) - The target Element that the Observer is observing.
- **vars** (Object) - The configuration object that was originally passed in to the Observer.create().
- **velocityX** (Number) - The horizontal velocity (in pixels per second) of the observed movement.
- **velocityY** (Number) - The vertical velocity (in pixels per second) of the observed movement.
- **x** (Number) - The `clientX` from the most recent touch/pointer event, referring to the horizontal distance from the left edge of the viewport. This is updated if the `type` includes "touch" and/or "pointer".
- **y** (Number) - The `clientY` from the most recent touch/pointer event, referring to the vertical distance from the top edge of the viewport. This is updated if the `type` includes "touch" and/or "pointer".

#### Response Example

```json
{
  "target": "<div id=\"myElement\"></div>",
  "vars": {
    "type": "scroll,pointer",
    "speed": 1
  },
  "velocityX": 150.5,
  "velocityY": 0,
  "x": 300,
  "y": 150
}
```
```

--------------------------------

### Position Animations in GSAP Timeline (Labels)

Source: https://gsap.com/docs/v3/GSAP/Timeline

Explains how to use labels to mark specific points in a GSAP Timeline and position animations relative to these labels.

```javascript
tl.to(".class", { x: 100 }, "someLabel");
tl.to(".class", { x: 100 }, "someLabel+=2");
```

--------------------------------

### nextLabel Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/nextLabel%28%29

Retrieves the name of the next label in a GSAP timeline from a given time. If no time is specified, it uses the current playhead position.

```APIDOC
## nextLabel

### Description
Returns the name of the label that occurs after the specified time in the timeline. If no time is provided, the timeline's current playhead time is used. Labels at the exact same time are ignored.

### Method
`nextLabel( time:Number )`

### Parameters
#### Path Parameters
* None

#### Query Parameters
* None

#### Request Body
* None

### Request Example
```javascript
tl.nextLabel(1.5);
```

### Response
#### Success Response (String)
- **labelName** (String) - The name of the next label.

#### Response Example
```json
{
  "labelName": "myLabel"
}
```

### Details
The `nextLabel()` method is useful for navigating timelines. For example, you can use it with `tweenTo()` to jump to the next label:

```javascript
tl.tweenTo(tl.nextLabel());
```
```

--------------------------------

### Snap values, increments, and points with GSAP v3

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/snap%28%29

Demonstrates the `gsap.utils.snap()` function for snapping numbers to an array of values or to increments, with an optional radius. It also shows how to snap 2D points (objects with x and y properties) to an array of points.

```javascript
// snapping only occurs when the provided value is within a radius of 20 from one of the values in the array
gsap.utils.snap({ values: [0, 100, 300], radius: 20 }, 30.5); // 30.5 (because it's not within 20 of any values)

// this will snap because it's within the radius:
gsap.utils.snap({ values: [0, 100, 300], radius: 20 }, 85); // 100

// also works with points (objects with "x" and "y" properties):
var point = { x: 8, y: 8 };
gsap.utils.snap(
  {
    values: [
      { x: 0, y: 0 },
      { x: 10, y: 10 },
      { x: 20, y: 20 },
    ],
    radius: 5,
  },
  point
); // {x:10, y:10}

// snapping only occurs when the provided value is within a radius of 150 from any increment of 500
gsap.utils.snap({ increment: 500, radius: 150 }, 975); // 1000 (because it's within 150 of an increment of 500)
```

--------------------------------

### targets()

Source: https://gsap.com/docs/v3/GSAP/Tween

Returns the targets of the tween.

```APIDOC
## GET /docs/v3/GSAP/Tween/targets().md

### Description
Returns the targets of the tween.

### Method
GET

### Endpoint
/docs/v3/GSAP/Tween/targets().md

### Parameters
N/A

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Array** (Array) - Returns the targets.

#### Response Example
N/A
```

--------------------------------

### Animate CSS Properties with GSAP

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/CSS

Demonstrates how to animate various CSS properties using GSAP. It shows the conversion of hyphenated names to camelCase and how GSAP handles complex string values and properties like 'height: auto'.

```javascript
gsap.to(element, {
  backgroundColor: "red", // background-color
  fontSize: 12, // font-size
  boxShadow: "0px 0px 20px 20px red", // animate complex strings
  borderRadius: "50% 50%",
  height: "auto", // animate between auto and a px value 🪄
});
```

--------------------------------

### Relative End Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Place an animation at the end of the previously inserted animation using the '>' character. This allows for animations to follow each other immediately.

```javascript
tl.from(".class", { x: 100 }, ">");
```

--------------------------------

### Configure Draggable Click Event Handling

Source: https://gsap.com/docs/v3/Plugins/Draggable

Defines functions and parameters to be executed when an element is clicked (dragged less than 3 pixels). It allows access to Draggable instance properties and event details.

```javascript
Draggable.create(element, {
  onClick: function(event) {
    console.log("Clicked!");
    console.log("PageX: " + event.pageX);
  },
  onClickParams: ["customParam1", 123]
});
```

--------------------------------

### GSAP v3: Add Callback to Timeline with call()

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

Demonstrates how to use the `call()` method to add a callback function to a GSAP timeline. This method is a shortcut for `timeline.add(gsap.delayedCall(...))` and allows for specifying parameters and insertion points within the timeline.

```javascript
function myFunction(param1, param2) {
  // ...
}

// Using add with delayedCall
tl.add(gsap.delayedCall(0, myFunction, ["param1", "param2"]));

// Using call (equivalent)
tl.call(myFunction, ["param1", "param2"]);
```

```javascript
//create a timeline that calls myFunction() when it completes
var tl = gsap.timeline({ onComplete: myFunction });

//now we'll use chaining, but break each step onto a different line for readability...

//tween element's x to 100
tl.to(element, { duration: 1, x: 100 })

  //then call myCallback()
  .call(myCallback)

  //then set element.opacity to 0.5 immediately
  .set(element, { opacity: 0 })

  //then call otherFunction("param1", "param2")
  .call(otherFunction, ["param1", "param2"])

  //finally tween the rotation of element1, element2, and element3 to 45 and stagger the start times by 0.25 seconds
  .to([element1, element2, element3], {
    duration: 1.5,
    rotation: 45,
    stagger: 0.25,
  });
```

--------------------------------

### SplitText.split()

Source: https://gsap.com/docs/v3/Plugins/SplitText/split%28%29

The static split() method allows you to split text content within target elements based on configuration properties. It's typically called automatically by the constructor but can be used manually to re-split text.

```APIDOC
## SplitText.split()

### Description
Splits the text in the target element(s) according to the provided config properties. This method is usually called automatically in the constructor, but can be used to change the text splitting configuration after the SplitText instance has been created.

### Method
`static`

### Endpoint
N/A (This is a static utility method, not an HTTP endpoint)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Parameters
#### **vars**: Object
(default = `null`) - A configuration object that can include the following properties:
- `type`: Specifies the type of splitting (e.g., 'chars', 'words', 'lines').
- `charsClass`: CSS class to apply to individual characters.
- `wordsClass`: CSS class to apply to words.
- `linesClass`: CSS class to apply to lines.
- `position`: Controls the position of the split elements.

### Request Example
```javascript
// Example of calling split with configuration
SplitText.split("#myElement", {
  type: "chars",
  charsClass: "my-char-class"
});
```

### Response
#### Success Response (200)
This method does not return a value directly but modifies the target element(s) by splitting the text and applying configurations. The SplitText instance itself holds the references to the split elements.
```

--------------------------------

### ScrollTrigger Configuration Options

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This section details various configuration options available for ScrollTrigger instances, including refreshPriority, scroller, scrub, and snap.

```APIDOC
## ScrollTrigger Configuration Options

### Description
This section details various configuration options available for ScrollTrigger instances, including refreshPriority, scroller, scrub, and snap.

### Method
N/A (Configuration options applied during ScrollTrigger instantiation)

### Endpoint
N/A

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
N/A

#### Response Example
N/A

## Configuration Details:

* #### refreshPriority

  `Number` - It's unlikely you'd need to define a `refreshPriority` unless ScrollTriggers are created out of order. Use `refreshPriority` to influence the order in which ScrollTriggers get refreshed. A higher number means it gets refreshed earlier. Default is `0`.

* #### scroller

  `String | Element` - By default, the `scroller` is the viewport. This option allows you to specify a different scrollable element (e.g., a `<div>`) using selector text or the element itself.

* #### scrub

  `Boolean | Number` - Links the animation's progress directly to the scrollbar. 
  - `true`: Directly links animation progress to ScrollTrigger progress.
  - `Number`: Specifies the time (in seconds) for the animation's playhead to catch up to the scrollbar's position, enabling smoothing.

* #### snap

  `Number | Array | Function | Object | "labels" | "labelsDirectional"` - Allows snapping to specific progress values after scrolling stops.
  - **Number**: Snaps in increments (e.g., `0.1` for 10% increments).
  - **Array**: Snaps to the closest value in the provided array (e.g., `[0, 0.1, 0.5, 0.8, 1]`).
  - **Function**: Custom logic to determine the snap point based on the scroll value.
  - **"labels"**: Snaps to the closest label in a GSAP Timeline.
  - **"labelsDirectional"**: Snaps to the closest label in the direction of the last scroll.
  - **Object**: Provides detailed customization with properties like `snapTo`, `duration`, `delay`, `ease`, `directional`, `inertia`, and callbacks (`onStart`).
    - `snapTo`: Determines the snapping logic (Number, Array, Function, "labels").
    - `duration`: Duration of the snapping animation (Number or Object with `min`/`max`).
    - `delay`: Delay before snapping starts.
    - `ease`: Easing function for the snapping animation.
    - `directional`: (Boolean) Enables/disables directional snapping (default is true).
    - `inertia`: (Boolean) Disables inertia factoring in snapping.
    - `onStart`: (Function) Callback when snapping begins.

### Error Handling
N/A
```

--------------------------------

### Define Motion Path using Array of Property Objects

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Explains how to define a motion path by providing an array of objects, where each object specifies values for different properties (e.g., scale, rotation). This method smoothly animates the target through these property values.

```javascript
motionPath: [
  { scale: 0.5, rotation: 10 },
  { scale: 1, rotation: -10 },
  { scale: 0.8, rotation: 3 },
];
```

--------------------------------

### Wrap Values with wrap() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The wrap() method returns the next item in an array or a number in a range after the given index. If no index is provided, it returns a function that performs this wrapping when fed a value. This is useful for creating looping or cyclical behaviors. This method is part of GSAP's utility methods.

```javascript
const arr = [1, 2, 3];
gsap.utils.wrap(0, arr.length, 2)(arr) // Output: 3

const wrapInRange = gsap.utils.wrap(0, 100);
wrapInRange(110) // Output: 10
```

--------------------------------

### Chaining eventCallback Calls (GSAP)

Source: https://gsap.com/docs/v3/GSAP/Timeline/eventCallback%28%29

This snippet illustrates the chaining capability of the eventCallback method in GSAP. After setting an 'onComplete' callback, another 'onUpdate' callback with parameters is set on the same animation instance, followed by calling the 'play' method. This demonstrates how the setter returns the animation instance for fluid method chaining.

```javascript
myAnimation.eventCallback("onComplete", completeHandler)
    .eventCallback("onUpdate", updateHandler, ["param1"]).play(1);
```

--------------------------------

### Minimal SplitText Usage with GSAP Animation

Source: https://gsap.com/docs/v3/Plugins/SplitText

Demonstrates the basic usage of SplitText to split elements with the class 'split' into words and characters, followed by a GSAP animation applied to the split characters. It utilizes GSAP's stagger feature for staggered animation effects.

```javascript
// split elements with the class "split" into words and characters
let split = SplitText.create(".split", { type: "words, chars" });

// now animate the characters in a staggered fashion
gsap.from(split.chars, {
  duration: 1,
  y: 100,       // animate from 100px below
  autoAlpha: 0, // fade in from opacity: 0 and visibility: hidden
  stagger: 0.05 // 0.05 seconds between each
});
```

--------------------------------

### Configure Live Snapping with Functions for Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

Enables custom snapping logic for Draggable elements while dragging. This can be achieved by providing a function for 'points' to apply combined x/y logic or separate functions for 'x' and 'y' properties for individual axis snapping.

```javascript
Draggable.create('#id', {
	type: 'x,y',
	liveSnap: {
		points: function (point) {
			var dx = point.x - 500;
			var dy = point.y - 250;
			if (Math.sqrt(dx * dx + dy * dy) < 100) {
				return { x: 500, y: 250 };
			}
			return point;
		}
	}
});
```

```javascript
Draggable.create('#id', {
	type: 'x,y',
	liveSnap: {
		x: function (value) {
			return Math.round(value / 50) * 50;
		},
		y: function (value) {
			return Math.round(value / 25) * 25;
		}
	}
});
```

```javascript
Draggable.create('#id', {
	type: 'rotation',
	liveSnap: {
		rotation: function (value) {
			return Math.round(value / 10) * 10;
		}
	}
});
```

--------------------------------

### GSAP v3 then() Method

Source: https://gsap.com/docs/v3/GSAP/Tween/then%28%29

The then() method in GSAP v3 allows you to chain actions after an animation completes by returning a Promise.

```APIDOC
## GSAP v3 then() Method

### Description
Returns a promise so that you can use promises to track when a tween or timeline is complete. This is an alternative to using the `onComplete` callback.

### Method
`then()`

### Endpoint
N/A (This is a method of a GSAP tween or timeline object)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
gsap.to(".class", {duration: 1, x: 100}).then(yourFunction).then(...);
```

### Response
#### Success Response (200)
This method returns a `Promise` that resolves when the animation completes.

#### Response Example
```json
{
  "promise": "A JavaScript Promise object"
}
```
```

--------------------------------

### Flip.from

Source: https://gsap.com/docs/v3/Plugins/Flip

Immediately moves/resizes targets to match a provided state, then animates backwards to end at the current state. Returns a timeline animation.

```APIDOC
## POST /websites/gsap_v3/plugins/flip/from

### Description
Immediately moves/resizes the targets to match the provided `state` object, and then animates backwards to remove those offsets to end up at the current state. By default, `width` and `height` properties are used for the resizing, but you can set `scale: true` to scale instead (transform). It returns a timeline animation, so you can control it or add() other animations.

### Method
POST

### Endpoint
/websites/gsap_v3/plugins/flip/from

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **state** (FlipState) - Required - The state object to animate from.
- **vars** (Object) - Optional - An object containing additional properties like `scale`.
  - **scale** (Boolean) - Optional - If true, uses scaleX and scaleY instead of width and height.

### Request Example
```json
{
  "state": {
    "x": 100,
    "y": 50,
    "width": 200,
    "height": 150
  },
  "vars": {
    "scale": true
  }
}
```

### Response
#### Success Response (200)
- **Timeline** (Object) - A GSAP timeline animation object.

#### Response Example
```json
{
  "message": "Animation created successfully."
}
```
```

--------------------------------

### GSDevTools Keyboard Controls

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

This snippet lists the default keyboard shortcuts available for controlling GSDevTools and the associated GSAP animations. These shortcuts allow for quick manipulation of playback, timeline markers, and UI visibility without needing to use the mouse.

```plaintext
SPACEBAR: play/pause
UP/DOWN ARROWS: increase/decrease timeScale
LEFT ARROW: rewind
RIGHT ARROW: jump to end
L: toggle loop
I: set in point
O: set out point
H: hide/show toggle
```

--------------------------------

### Tweening ColorFilter Properties with GSAP

Source: https://gsap.com/docs/v3/Plugins/EaselPlugin

Illustrates how to directly tween individual properties of an EaselJS ColorFilter using GSAP's EaselPlugin. This allows for fine-grained control over color transformations.

```javascript
gsap.to(circle, {
  duration: 3,
  easel: {
    colorFilter: { redMultiplier: 0.5, blueMultiplier: 0.8, greenOffset: 100 },
  },
});
```

--------------------------------

### Import GSDevTools from GSAP Package

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Imports the GSDevTools plugin from the GSAP npm package. This is the standard approach for projects using a module bundler like Webpack or Rollup.

```javascript
import { GSDevTools } from "gsap/GSDevTools";
```

--------------------------------

### Minimal Inertia Animation

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

Demonstrates the most basic usage of InertiaPlugin. It animates the 'x' and 'y' properties of an object to a stop, based on the provided initial velocities. The plugin automatically calculates a natural duration for the deceleration.

```javascript
gsap.to(obj, { inertia: { x: 500, y: -300 } });
```

--------------------------------

### ScrollTrigger Configuration Options

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This section details various configuration options available for ScrollTrigger, including parameters related to pinning, element handling, and animation overlaps.

```APIDOC
## ScrollTrigger Configuration Options

This page details various configuration options available for ScrollTrigger, including parameters related to pinning, element handling, and animation overlaps.

### Element

*   **`pinnedContainer`** (Element | String) - If your ScrollTrigger's `trigger`/`endTrigger` element is **INSIDE** an element that gets pinned by *another* ScrollTrigger (pretty uncommon), that would cause the start/end positions to be thrown off by however long that pin lasts, so you can set the `pinnedContainer` to that parent/container element to have ScrollTrigger calculate those offsets accordingly. Again, this is very rarely needed. **Important**: nested pinning is not supported, so this feature is only for non-pinning ScrollTriggers. (added in 3.7.0)

### Pin Reparenting

*   **`pinReparent`** (Boolean) - If `true`, the pinned element will be reparented to the `<body>` while it is actively pinned so that it can escape any ancestor containing blocks. If you notice odd behavior while pinning (like the pinned element suddenly shifting and then moving with the scroll), you probably have a `transform` or `will-change` on an ancestor element which breaks `position: fixed` behavior. It's best to set up your project to avoid those because reparenting can be expensive, but `pinReparent: true` can bail you out if you can't avoid them. Only use this feature if you must. **Warning:** if you have CSS rules that rely on specific nesting that'd be affected by the reparenting, they'll break.

### Pin Spacer

*   **`pinSpacer`** (Element | String) - Normally ScrollTrigger creates a `<div>` internally to wrap around pinned elements but in the *extremely* rare scenario where you're loading an iframe into the pinned element, it can cause the iframe to refresh when ScrollTrigger refreshes (like on window resize), so this feature allows you to specify an element that should be used as the spacer instead of the internally-created one. That way, ScrollTrigger won't remove/add it during its refresh, keeping iframe content intact.

### Pin Spacing

*   **`pinSpacing`** (Boolean | String) - By default, padding will be added to the bottom (or right for `horizontal: true`) to push other elements down so that when the pinned element gets unpinned, the following content catches up perfectly. Otherwise, things may scroll UNDER the pinned element. You can tell ScrollTrigger not to add any padding by setting `pinSpacing: false`. If you'd rather it use margin instead of padding, you can set `pinSpacing: "margin"`. **Note:** `pinSpacing` works in most cases, but it really depends on the way you set up your DOM and CSS. For example, if you pin something in a parent that has `display: flex` or `position: absolute`, the extra padding won't push other elements down/right so you may need to manually space things out. `pinSpacing` is just a convenience that works in most situations. **Important**: if the container is `display: flex`, `pinSpacing` is set to `false` by default because that's typically what is desired since padding works differently in that context.

### Pin Type

*   **`pinType`** ("fixed" | "transform") - By default, `position: fixed` is used for pinning only if the scroller is the `<body>`, otherwise transforms are used (because `position: fixed` won't work in various nested scenarios), but you can **force** ScrollTrigger to use `position: fixed` by setting `pinType: "fixed"`. Typically this isn't necessary or helpful. Beware that if you set the CSS property `will-change: transform`, browsers treat it just like having a transform applied, breaking `position: fixed` elements (this is unrelated to ScrollTrigger/GSAP).

### Prevent Overlaps

*   **`preventOverlaps`** (Boolean | String) - This feature activates as a ScrollTrigger is about to trigger an animation; it finds preceding scrollTrigger-based animations and forces those previous animations to their end state – avoiding unsightly overlaps. If `true`, it will affect all preceding ScrollTriggers. You can use an arbitrary string to limit their effect to only others with a matching string. So `preventOverlaps: "group1"` would only affect other ScrollTriggers with `preventOverlaps: "group1"`. See a [demo here](https://codepen.io/GreenSock/pen/7d22c763b9edd0c0c48150ecd1c921c9).

### Refresh Priority

*   **`refreshPriority`** (Number) - Determines the order in which ScrollTriggers are refreshed. Higher numbers are refreshed first. Defaults to 0.
```

--------------------------------

### Create reusable snap functions with GSAP v3

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/snap%28%29

Shows how to create reusable snapping functions using `gsap.utils.snap()` by omitting the value to snap. These functions can then be used to snap multiple values efficiently, including numbers and 2D points.

```javascript
// get a reusable function that will snap only when the provided value is within a radius of 20 from one of the values in the array
var snap = gsap.utils.snap({ values: [0, 100, 300], radius: 20 }); // notice we didn't provide a valueToSnap

// now we can reuse the function to snap any values:
console.log(snap(50)); // 50 (not within radius)
console.log(snap(86)); // 100 (within radius)
console.log(snap(315)); // 300 (within radius)

// also works with points (objects with "x" and "y" properties):
var snap = gsap.utils.snap({
  values: [
    { x: 0, y: 0 },
    { x: 10, y: 10 },
    { x: 20, y: 20 },
  ],
  radius: 5,
});

// now we can reuse the function to snap points:
console.log(snap({ x: 8, y: 8 })); // {x:10, y:10} (within radius)
console.log(snap({ x: 40, y: 40 })); // {x:40, y:40} (outside radius)
console.log(snap({ x: -5, y: -10 })); // {x:-5, y:-10} (outside radius)

// or a simple increment:
var snap = gsap.utils.snap({ increment: 500, radius: 150 }); // notice we didn't provide a valueToSnap

// now we can reuse the function to snap any values:
console.log(snap(310)); // 310 (not within radius)
console.log(snap(480)); // 500 (within radius)
console.log(snap(610)); // 500 (within radius)
```

--------------------------------

### Timeline yoyo() Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/yoyo%28%29

This section details the yoyo() method for GSAP timelines, explaining its getter and setter functionality for controlling the alternating repeat behavior.

```APIDOC
## GET/SET yoyo()

### Description
Gets or sets the timeline's yoyo state. When true, the timeline repeats by alternating backward and forward on each repeat.

### Method
GET / SET

### Endpoint
`timeline.yoyo()`

### Parameters
#### Query Parameters
- **value** (Boolean) - Optional - If provided, sets the yoyo state to true or false. If omitted, returns the current yoyo state.

### Request Example
```javascript
// Getter: Get the current yoyo state
var currentYoyoState = myTimeline.yoyo();

// Setter: Set yoyo to true
myTimeline.yoyo(true);

// Chaining setters
myTimeline.yoyo(true).repeat(3).timeScale(2).play(0.5);
```

### Response
#### Success Response (Getter)
- **yoyoState** (Boolean) - The current yoyo state of the timeline.

#### Success Response (Setter)
- **instance** (Object) - Returns the timeline instance itself for chaining.

#### Response Example (Getter)
```json
{
  "yoyoState": true
}
```

#### Response Example (Setter)
```json
{
  "message": "Timeline instance returned for chaining"
}
```

### Details
The `yoyo()` method controls whether a repeating timeline alternates its playback direction on each repeat. For `yoyo` to have an effect, the `repeat` property must be set to a value greater than zero. `yoyo` does not affect the `reversed` property of the timeline. The method acts as both a getter (when no argument is provided) and a setter (when a boolean argument is provided).
```

--------------------------------

### CSS Styling for MotionPath Animation

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

Provides basic CSS for the HTML document, setting up full viewport height and hiding overflow. It also styles the SVG path, setting stroke width and color, and hides the astronaut element by default.

```css
body, html {
  padding: 0;
  margin: 0
}
body {
  height: 100vh;
  overflow: hidden;
}
#motionPath {
  overflow: visible;
  height: 100%;
  max-width: 100%;
}

#motionPath path {
  stroke-width: 2;
  stroke: gray;
}

#motionPath .astronaut {
  visibility: hidden;
}
```

--------------------------------

### Timeline fromTo Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Adds a `.fromTo()` tween to the end of the timeline. This is a convenience method that accomplishes the same thing as `add(gsap.fromTo(...))` but with less code.

```APIDOC
## POST /websites/gsap_v3/fromTo

### Description
Adds a `.fromTo()` tween to the end of the timeline. This is a convenience method that accomplishes the same thing as `add(gsap.fromTo(...))` but with less code.

### Method
POST

### Endpoint
/websites/gsap_v3/fromTo

### Parameters
#### Path Parameters
- **target** (Object | Array | String) - Required - Target object (or array of objects) whose properties should be affected. This can also be CSS selector text like "#feature" or "h2.author".
- **fromVars** (Object) - Required - An object defining the starting values for each property that should be animated. Do **NOT** put special properties like duration, ease, delay, etc. here - those go in the **toVars** parameter.
- **toVars** (Object) - Required - An object defining the end values for each property that should be animated as well as any special properties like `duration`, `onComplete`, `ease`, etc.
- **position** (Number | String) - Optional - (default = `"+=0"`) - Controls the insertion point in the timeline. See the [Position Parameter article](/resources/position-parameter.md) for more details.

### Request Example
```json
{
  "target": "#myElement",
  "fromVars": {
    "x": -100
  },
  "toVars": {
    "duration": 1,
    "x": 100,
    "ease": "power2.inOut"
  },
  "position": "+=1"
}
```

### Response
#### Success Response (200)
- **self** (Object) - The GSAP timeline instance, allowing for chaining.

#### Response Example
```json
{
  "self": "[GSAP Timeline Instance]"
}
```
```

--------------------------------

### Wrap with Yoyo Behavior using wrapYoyo() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The wrapYoyo() method returns an element from an array or a number in a range, going backwards once the last index is reached (yoyo-ing). If no value is provided, it returns a reusable function that performs this wrapping. This is useful for creating back-and-forth animations. This method is part of GSAP's utility methods.

```javascript
const arr = ["a", "b", "c"];
gsap.utils.wrapYoyo(0, arr.length, 2)(arr) // Output: "a"
gsap.utils.wrapYoyo(0, arr.length, 4)(arr) // Output: "b"

const wrapYoyoInRange = gsap.utils.wrapYoyo(0, 100);
wrapYoyoInRange(110) // Output: 90
```

--------------------------------

### Define shapeIndex in Advance for MorphSVG Performance

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Provides a performance tip for MorphSVGPlugin by suggesting the pre-definition of the shapeIndex. It explains how setting a numeric shapeIndex or using the 'log' value to capture the auto-calculated index can skip runtime calculations and improve performance.

```javascript
// logs a value like "shapeIndex:[3]"
gsap.to("#id", {
  duration: 1,
  morphSVG: { shape: "#otherID", shapeIndex: "log" },
});
// now you can grab the value from the console and drop it in...
gsap.to("#id", {
  duration: 1,
  morphSVG: { shape: "#otherID", shapeIndex: [3] },
});
```

--------------------------------

### MorphSVGPlugin.stringToRawPath

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Takes a string of path data and converts it into a RawPath array, parsing it into cubic beziers.

```APIDOC
## MorphSVGPlugin.stringToRawPath

### Description
Takes a string of path data (like `"M0,0 C100,20 300,50 400,0..."`, what's typically found in the `d` attribute of a `<path>`), parses it, converts it into cubic beziers, and returns it as a RawPath which is just an array containing an array for each segment (each `M` command starts a new segment).

### Method
Static method

### Endpoint
N/A (JavaScript method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
*   **data** (String) - Required - The SVG path data string.

### Request Example
```javascript
const pathString = "M10,10 L90,10 L90,90 L10,90 Z";
const rawPath = MorphSVGPlugin.stringToRawPath(pathString);
console.log(rawPath); // Output: [[{x:10,y:10},{x:90,y:10},{x:90,y:90},{x:10,y:90}]]
```

### Response
#### Success Response (200)
*   **RawPath** (Array) - An array representing the parsed path data, where each inner array is a segment.
```

--------------------------------

### Percentage-Based Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Allows positioning based on percentages of either the inserting animation's duration or the previous animation's duration. This feature was introduced in GSAP 3.7.0.

```javascript
// Overlap by 25% of the inserting animation's duration
tl.to(".class", { x: 100 }, "-=25%");

// Gap of 50% of the inserting animation's duration beyond the timeline end
tl.to(".class", { x: 100 }, "+=50%");

// 25% into the previous animation (based on previous animation's duration)
tl.to(".class", { x: 100 }, "<25%");

// 30% past the "myLabel" label (based on inserting animation's duration)
tl.to(".class", { x: 100 }, "myLabel+=30%");

// 0.5 seconds before the end of the previous animation
tl.to(".class", { x: 100 }, ">-0.5");
```

--------------------------------

### Register GSAP CustomEase Plugin

Source: https://gsap.com/docs/v3/Eases/CustomEase

This code snippet shows how to register the CustomEase plugin with GSAP, which is necessary before using any CustomEase functionalities. It requires the GSAP core library to be loaded.

```javascript
gsap.registerPlugin(CustomEase)
```

--------------------------------

### Create and Use Custom Bounce Ease (JavaScript)

Source: https://gsap.com/docs/v3/Eases/CustomBounce

This snippet demonstrates how to create a custom bounce ease with specified strength and squash, and then apply it to a GSAP tween for the 'y' property. It also shows how to create a corresponding squash ease for synchronized scale animations.

```javascript
//Create a custom bounce ease:
CustomBounce.create("myBounce", {
  strength: 0.6,
  squash: 3,
  squashID: "myBounce-squash",
});

//do the bounce by affecting the "y" property.
gsap.from(".class", { duration: 2, y: -200, ease: "myBounce" });

//and do the squash/stretch at the same time:
gsap.to(".class", {
  duration: 2,
  scaleX: 1.4,
  scaleY: 0.6,
  ease: "myBounce-squash",
  transformOrigin: "center bottom",
});
```

--------------------------------

### Label-Based Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/fromTo%28%29

Positions an animation at a named label within the timeline. If the label does not exist, it is automatically created at the end of the timeline.

```javascript
tl.fromTo(".class", { x: 100 }, { x: 200 }, "someLabel");
```

--------------------------------

### deltaX Property

Source: https://gsap.com/docs/v3/Plugins/Draggable/deltaX

Explains the deltaX property, its type, and its purpose in tracking changes during drag events.

```APIDOC
## deltaX Property

### Description

The `deltaX` property represents the change in the x-related value since the last drag event. This is particularly useful for tracking horizontal movement during interactive drag operations.

### Method

N/A (This is a property, not an endpoint)

### Endpoint

N/A (This is a property, not an endpoint)

### Parameters

#### Path Parameters

N/A

#### Query Parameters

N/A

#### Request Body

N/A

### Request Example

N/A

### Response

#### Success Response (200)

- **deltaX** (Number) - The change in the x-related value since the last drag event. The x-related value is typically `x` (`translateX`) or `left`, but if type is "rotation" it applies to the change in rotation.

#### Response Example

```json
{
  "deltaX": 15.5
}
```
```

--------------------------------

### Animating BlurFilter Properties with GSAP

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

Demonstrates the ease of applying blur effects to PixiJS objects using PixiPlugin's `blur`, `blurX`, and `blurY` properties. This avoids the need to manually create and manage BlurFilter instances.

```javascript
//blur on both the x and y axis to a blur amount of 15
gsap.to(image, { pixi: { blurX: 15, blurY: 15 }, duration: 2 });
```

--------------------------------

### FLIP Animation Special Properties

Source: https://gsap.com/docs/v3/Plugins/Flip/static

This section details the special properties that can be used within the options object of the `Flip.from()` method in GSAP v3, in addition to standard tween properties.

```APIDOC
## Special Properties for Flip.from()

### Description
These are optional properties that can be included in the second parameter (options object) of the `Flip.from()` method. They work alongside standard tween properties like `duration`, `ease`, and `onComplete`.

### Method
`Flip.from(targets, options)

### Endpoint
N/A (This is a method within a JavaScript library)

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
(This refers to the `options` object passed to `Flip.from()`)

- **absolute** (Boolean | String | Array | NodeList | Element) - Optional - Specifies which targets should have `position: absolute` applied during the FLIP animation. If `true`, all targets are affected. You can also provide selector text, an array/NodeList of Elements, or a single Element to affect a subset. This is useful for flex and grid layouts. Setting `absolute: true` can sometimes solve layout issues, but be aware that `position: absolute` removes elements from the document flow, potentially causing collapse. In such cases, define a subset that excludes the container to maintain layout.
- **absoluteOnLeave** (Boolean) - Optional - If `true`, any "leaving" Elements (passed to `onLeave()`) will be set to `position: absolute` during the flip animation. This is useful when hiding elements with `display: none` in the final state but wanting to animate them out. It ensures they don't affect layout while remaining visible during the animation.

### Request Example
```javascript
Flip.from(
  targets,
  {
    absolute: ".my-class",
    absoluteOnLeave: true,
    duration: 1,
    ease: "power1.inOut",
    onComplete: () => console.log("Flip complete!")
  }
);
```

### Response
#### Success Response (200)
N/A (This is a method call, not an HTTP request/response)

#### Response Example
N/A
```

--------------------------------

### Perform State Changes for FLIP Animation

Source: https://gsap.com/docs/v3/Plugins/Flip

This step involves making the necessary DOM or style modifications to transition elements to their desired final state. This can include toggling classes, updating styles, or any other DOM manipulation.

```javascript
element.classList.toggle("full-screen");
```

--------------------------------

### MotionPathPlugin.pointsToSegment

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin/methods/static-pointsToSegment

Plots a curved cubic Bezier path through the provided x,y point coordinates, returning a segment Array that's typically dropped into a RawPath Array.

```APIDOC
## MotionPathPlugin.pointsToSegment

### Description
Plots a curved cubic Bezier path through the provided x,y point coordinates, returning a segment Array that's typically dropped into a RawPath Array.

### Method
N/A (This is a utility function, not an HTTP endpoint)

### Endpoint
N/A

### Parameters
#### Path Parameters
N/A

#### Query Parameters
N/A

#### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (N/A)
N/A

#### Response Example
N/A

### Parameters
#### **points** (Array)
An Array of alternating x, y, x, y point coordinates like [x, y, x, y, x, y...]

#### **curviness** (Number)
[Optional] This determines how "curvy" the resulting path is. So 0 would make straight lines (hard corners), 1 (the default) creates a nicely curved path, and 2 would make it much more curvy. Think of it like pulling the control points further and further outward from the anchors as the number goes higher.

### Returns
Array - Cubic Bezier data in alternating x, y, x, y format (ordered like: anchor, two control points, anchor, two control points, anchor, etc.)
```

--------------------------------

### Configure Draggable with onThrowUpdate Callback

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet demonstrates setting an 'onThrowUpdate' callback function for the InertiaPlugin. This function is executed on each tick of the inertia tween after the user releases the element, allowing for real-time updates during the momentum-based motion.

```javascript
Draggable.create(element, {
  inertia: true,
  onThrowUpdate: function() {
    console.log('Inertia tween updating...');
  }
});
```

--------------------------------

### Animating CSS Variables with GSAP

Source: https://gsap.com/docs/v3/Plugins/CSSRulePlugin

Demonstrates how to animate CSS variables directly using GSAP's native support. This is the recommended approach, replacing the deprecated CSSRulePlugin. It takes a selector and an object with CSS variable properties to tween.

```javascript
gsap.to("html", { "--my-variable": 100, duration: 2 });
```

--------------------------------

### Draggable Enabled State

Source: https://gsap.com/docs/v3/Plugins/Draggable/enabled%28%29

This section details the `enabled()` method for GSAP's Draggable plugin. It explains how to retrieve the current enabled state and how to set a new state, which controls whether the Draggable instance responds to events and can be dragged.

```APIDOC
## GET/SET enabled

### Description
Gets or sets the enabled state of the Draggable instance. When enabled, the instance responds to mouse events, fires callbacks, and can be dragged. Omitting the `value` parameter acts as a getter, while providing a boolean value acts as a setter.

### Method
GET / SET (via JavaScript method call)

### Endpoint
N/A (This is a JavaScript method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```javascript
// Getter: Get the current enabled state
let isEnabled = draggableInstance.enabled(); 

// Setter: Enable the Draggable instance
draggableInstance.enabled(true);

// Setter: Disable the Draggable instance
draggableInstance.enabled(false);
```

### Response
#### Success Response (Getter)
- **enabledState** (Boolean) - The current enabled state of the Draggable instance.

#### Success Response (Setter)
- **instance** (Draggable) - Returns the Draggable instance itself for chaining.

#### Response Example
```json
// Getter response example
true

// Setter response example (returns the instance for chaining)
// [Draggable Instance Object]
```

### Details
The `enabled()` method provides a straightforward way to control the interactivity of a Draggable instance. Setting `value` to `true` activates dragging and associated events, while `false` deactivates them. This is useful for temporarily disabling dragging, for example, during animations or when the UI is in a state where dragging is not desired.
```

--------------------------------

### Register GSAP MotionPathHelper Plugin

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

This snippet shows how to register the MotionPathHelper plugin with GSAP, which is necessary before using its features. It requires the GSAP library to be loaded.

```javascript
gsap.registerPlugin(MotionPathHelper)
```

--------------------------------

### then()

Source: https://gsap.com/docs/v3/GSAP/Tween

Returns a promise so that you can uses promises to track when a tween or timeline is complete. This allows for asynchronous operations after the tween completes.

```APIDOC
## POST /docs/v3/GSAP/Tween/then().md

### Description
Returns a promise to track when a tween is complete.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/then().md

### Parameters
#### Path Parameters
- **callback** (Function) - Required - The callback function.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **Promise** (Promise) - Returns a promise.

#### Response Example
N/A
```

--------------------------------

### SplitText with onSplit() Syntax (v3.13.0+)

Source: https://gsap.com/docs/v3/Plugins/SplitText

Shows the newer `onSplit()` syntax available from GSAP v3.13.0 onwards. This allows for splitting into lines and words and then immediately animating the words using a callback function. It includes options for masking and automatic splitting.

```javascript
SplitText.create(".split", {
  type: "lines, words",
  mask: "lines",
  autoSplit: true,
  onSplit(self) {
    return gsap.from(self.words, {
      duration: 1,
      y: 100,
      autoAlpha: 0,
      stagger: 0.05
    });
  }
});
```

--------------------------------

### Use findShapeIndex() Utility for MorphSVG Development

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Introduces the findShapeIndex() utility function provided by MorphSVGPlugin. This function helps in determining the correct shapeIndex values for morphing, especially for complex or multi-segment paths, by providing an interactive UI.

```javascript
findShapeIndex("#square", "#star");
```

```javascript
findShapeIndex(
  "#square",
  "M10 315 L 110 215 A 30 50 0 0 1 162.55 162.45 L 172.55 152.45 A 30 50 -45 0 1 215.1 109.9 L 315 10"
);
```

--------------------------------

### Timeline from() Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/from%28%29

Adds a `.from()` tween to the end of the timeline or at a specified position. This is a convenience method equivalent to `timeline.add(gsap.from(...))`.

```APIDOC
## POST /websites/gsap_v3/from

### Description
Adds a `.from()` tween to the end of the timeline (or elsewhere using the `position` parameter). This is a convenience method that accomplishes exactly the same thing as `add(gsap.from(...))` but with less code.

### Method
POST

### Endpoint
/websites/gsap_v3/from

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **target** (Object | Array | String) - Required - Target object (or array of objects) whose properties should be affected. Can also be CSS selector text.
- **vars** (Object) - Required - An object defining the starting values for each property that should be tweened as well as any special properties like `onComplete`, `ease`, etc.
- **position** (Number | String) - Optional - Controls the insertion point in the timeline. Defaults to `"+=0"`.

### Request Example
```json
{
  "target": "#myElement",
  "vars": {
    "duration": 1,
    "x": 100,
    "opacity": 0.5
  },
  "position": "+=1"
}
```

### Response
#### Success Response (200)
- **self** (Object) - Returns the timeline instance for easier chaining.

#### Response Example
```json
{
  "message": "Tween added successfully to the timeline."
}
```

### Details
This method is a shortcut for adding a `gsap.from()` tween to a timeline. Refer to the [gsap.from() documentation](/docs/v3/GSAP/gsap.from().md) for a comprehensive list of available properties and options within the `vars` object. You can chain multiple timeline methods like `to()`, `set()`, and `call()` after `from()` to create complex sequences.
```

--------------------------------

### Accessing Observer Callback Data in JavaScript

Source: https://gsap.com/docs/v3/Plugins/Observer

This snippet demonstrates how to access and log various properties passed to the `onChange` callback of a GSAP Observer instance. It shows how to retrieve velocity, delta, target element, and event details.

```javascript
Observer.create({
  ... 
  onChange: (self) =>  {
    console.log("velocity:", self.velocityX, self.velocityY, "delta:", self.deltaX, self.deltaY, "target element:", self.target, "last event:", self.event);
  }
});
```

--------------------------------

### Complex Relative Positioning with Offsets in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Uses prefixes like '+=' and '-=' to define positions relative to the end of the timeline or a specific label. These offsets can be in seconds or percentages of the inserting animation's duration.

```javascript
// 1 second past the end of the timeline
tl.to(".class", { x: 100 }, "+=1");

// 1 second before the end of the timeline (overlaps)
tl.to(".class", { x: 100 }, "-=1");

// 2 seconds past the "myLabel" label
tl.to(".class", { x: 100 }, "myLabel+=2");

// 3 seconds past the start of the previous animation
tl.to(".class", { x: 100 }, "<+=3");

// 0.5 seconds before the end of the previous animation
tl.to(".class", { x: 100 }, ">")
```

--------------------------------

### Live Recalculation for DrawSVG

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

Explains how to use the 'live' keyword with `drawSVG` to ensure the SVG element's length is recalculated during the animation. This is useful for responsive SVGs where dimensions might change.

```javascript
drawSVG: "20% 70% live"
```

--------------------------------

### Animating PixiJS Colors with GSAP

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

Shows how PixiPlugin allows animating color properties in PixiJS using familiar CSS color formats (names, hex, rgb, hsl) instead of the default `0xFF0000` format. It also demonstrates animating relative HSL values.

```javascript
//named colors
gsap.to(graphics, { duration: 2, pixi: { lineColor: "purple" } });

//relative hsl() color that reduces brightness but leaves the hue and saturation the same:
gsap.to(graphics, {
  duration: 2,
  pixi: { fillColor: "hsl(+=0, +=0%, -=30%)" },
});
```

--------------------------------

### ScrollTrigger.observe

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Provides a flexible way to sense pointer events across different devices.

```APIDOC
## ScrollTrigger.observe

### Description
Super-flexible, unified way to sense meaningful events across all (touch/mouse/pointer) devices without wrestling with all the implementation details. Trigger simple callbacks like onUp, onDown, onLeft, onRight, onChange, onHover, onDrag, etc. Functionally identical to [Observer.create()](/docs/v3/Plugins/Observer/static.create().md).

### Method
`static`

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **config** (Object) - An object containing event listeners and configurations for the observer.

### Request Example
```javascript
const myObserver = ScrollTrigger.observe({
  target: '#myElement',
  onHover: () => console.log('Hovered!'),
  onChange: (self) => console.log('Changed:', self.deltaX, self.deltaY)
});
```

### Response
#### Success Response (Observer)
- **return value** (Observer) - An Observer instance that can be used to manage the observation.

#### Response Example
```json
{
  "_isObserver": true
}
```
```

--------------------------------

### GSAP v3 Timeline Sequencing (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween

Creates and manages sequences of animations using the GSAP Timeline. It allows for precise control over the timing and order of multiple tweens, enabling complex animations and overlaps.

```javascript
let tl = gsap.timeline(); //create the timeline
tl.to(".class1", {x: 100}) //start sequencing
.to(".class2", {y: 100, ease: "elastic"})
.to(".class3", {rotation: 180});
```

--------------------------------

### Configure Live Snapping with Arrays for Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

Defines how a Draggable element snaps to specific points or values while being dragged. It supports snapping to an array of points (x, y) with a radius, or separate arrays for x and y coordinates.

```javascript
Draggable.create('#id', {
	type: 'x,y',
	liveSnap: {
		points: [
			{ x: 0, y: 0 },
			{ x: 100, y: 0 },
			{ x: 200, y: 50 }
		],
		radius: 15
	}
});
```

```javascript
Draggable.create('#id', {
	type: 'x,y',
	liveSnap: {
		x: [0, 100, 200, 300],
		y: [0, 50, 100, 150]
	}
});
```

--------------------------------

### Register GSAP MotionPathPlugin via CDN

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This snippet shows how to register the MotionPathPlugin using a CDN link, which is necessary before using its functionalities. It requires the GSAP library to be loaded first.

```javascript
gsap.registerPlugin(MotionPathPlugin)
```

--------------------------------

### Track Object Properties for Velocity (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/VelocityTracker/.track

Initiates velocity tracking for specified properties of a target object. This method is crucial for InertiaPlugin's throwProps tweens to automatically determine and apply velocity. It accepts the target object and a comma-delimited string of properties to track. Ensure properties are numeric or function-based getters/setters. Untrack when finished to optimize performance.

```javascript
InertiaPlugin.track(obj, "x,y");
```

--------------------------------

### GSAP Physics2D Tween with Acceleration

Source: https://gsap.com/docs/v3/Plugins/Physics2DPlugin

Demonstrates using both acceleration and accelerationAngle to control the directional force applied to the object during the tween, in addition to initial velocity and angle.

```javascript
gsap.to(element, {
  duration: 2,
  physics2D: {
    velocity: 300,
    angle: -60,
    acceleration: 50,
    accelerationAngle: 180,
  },
});
```

--------------------------------

### ScrollSmoother Plugin Methods

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother

This section details the various methods available for the GSAP ScrollSmoother plugin, allowing control over scrolling behavior, parallax effects, and instance management.

```APIDOC
## ScrollSmoother Plugin Methods

### Description
Provides methods to interact with and control the ScrollSmoother instance, including managing content, effects, scroll position, and the plugin's state.

### Methods

#### `.content(element: String | Element): Element | self`
Gets or sets the content element for ScrollSmoother.

#### `.effects(targets: String | Element | Array, config: Object | null): Array`
Adds parallax elements that are managed by ScrollSmoother.

#### `.getVelocity(): Number`
Returns the current velocity of the smoothed scroll in pixels per second.

#### `.kill(): void`
Kills the entire ScrollSmoother instance and any applied effects.

#### `.offset(target: String | Element, position: String): Number`
Calculates the numeric offset (scroll position in pixels) for a given element and position.

#### `.paused(pause: Boolean): Boolean | self`
Gets or sets the paused state of the ScrollSmoother instance.

#### `.scrollTo(target: Number | String | Element, smooth: Boolean, position: String): void`
Scrolls to a specific position or element, with optional smoothing.

#### `.scrollTop(position: Number): Number | void`
Immediately gets or sets the scroll position in pixels.

#### `.smooth(duration: Number): Number | self`
Gets or sets the duration (in seconds) for smoothing the scroll catch-up.

### Static Methods

#### `ScrollSmoother.create(): ScrollSmoother`
Creates a new ScrollSmoother instance.

#### `ScrollSmoother.get(): ScrollSmoother`
Returns the existing ScrollSmoother instance. Only one instance can exist at a time.
```

--------------------------------

### Create a Number Formatter with Custom Increment and Padding (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/formatNumber

Generates a flexible number formatter function based on a specified increment and padding option. The formatter can snap values to the increment and control decimal place padding. It's ideal for creating custom number display logic for animations.

```javascript
function getFormatter(increment, pad) {
  let snap = gsap.utils.snap(increment),
      exp = /\B(?=(\d{3})+(?!\d))/g,
      snapWithCommas = value => (snap(+value) + "").replace(exp, ","),
      whole = increment % 1 === 0,
      decimals = whole ? 0 : ((increment + "").split(".")[1] || "0").length;
  return !pad || whole ? snapWithCommas : value => {
    let s = snapWithCommas(value),
        i = s.indexOf(".");
    ~i || (i = s.length);
    return s.substr(0, i) + "." + (s.substr(i + 1, s.length - i - 1) + "00000000").substr(0, decimals);
  };
}
```

--------------------------------

### Enable GSAP Observer Instance

Source: https://gsap.com/docs/v3/Plugins/Observer

Enables a previously disabled Observer instance by re-adding its event listeners and triggering the onEnable callback. It accepts an optional 'event' object.

```javascript
observer.enable(event);
```

--------------------------------

### GSAP v3 Timeline Call Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

The 'call' method is a convenient way to add a function callback to a GSAP timeline at a specific position.

```APIDOC
## POST /timeline/call

### Description
Adds a callback function to the end of the timeline or at a specified position. This is a shortcut for `timeline.add(gsap.delayedCall(...))`.

### Method
POST

### Endpoint
`/timeline/call`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **callback** (Function) - Required - The function to be executed.
- **params** (Array) - Optional - An array of parameters to pass to the callback function. Defaults to `null`.
- **position** (*) - Optional - Controls the insertion point in the timeline. Defaults to `"+=0"` (end of the timeline). Can be a number, label, or a position relative to the current time.

### Request Example
```json
{
  "callback": "myFunction",
  "params": ["param1", "param2"],
  "position": "+=1.5"
}
```

### Response
#### Success Response (200)
- **self** (Object) - Returns the timeline instance, enabling chaining.

#### Response Example
```json
{
  "self": "[Timeline Instance]"
}
```
```

--------------------------------

### Define Motion Path using Array of XY Coordinates (Cubic Bezier)

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Demonstrates defining a motion path using an array of coordinates specified as a cubic Bezier curve. This requires setting the 'type' property to 'cubic'. The array format includes anchor points and control points.

```javascript
motionPath: {
  path: [{x:0, y:0}, {x:20, y:0}, {x:30, y:50}, {x:50, y:50}],
  type: "cubic"
}
```

--------------------------------

### GSAP Horizontal Loop Usage with Click Events

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/seamlessLoop

Demonstrates how to initialize a horizontal loop with GSAP and attach click event listeners to elements within the loop. Clicking an element will smoothly animate it to the first position in the loop.

```javascript
const boxes = gsap.utils.toArray(".box"),
  loop = horizontalLoop(boxes, { paused: true });

// add click listeners so you can click a box to have it move to the first slot
boxes.forEach((box, i) =>
  box.addEventListener("click", () =>
    loop.toIndex(i, { duration: 1, ease: "power1.inOut" })
  )
);

// make the "next" and "previous" buttons call the appropriate methods on the timeline
document
  .querySelector(".next")
  .addEventListener("click", () =>
    loop.next({ duration: 1, ease: "power1.inOut" })
  );
document
  .querySelector(".prev")
  .addEventListener("click", () =>
    loop.previous({ duration: 1, ease: "power1.inOut" })
  );
```

--------------------------------

### Restart Animation with GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Tween/restart%28%29

Restarts an animation, optionally including any defined delay and controlling event suppression. This method is useful for resetting animations to their initial state and replaying them.

```javascript
myAnimation.restart();

// Restarts, including any delay, and doesn't suppress events during the initial move back to time:0
myAnimation.restart(true, false);
```

--------------------------------

### Observer Configuration: Assigning an ID

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Assigns an arbitrary string ID to the Observer instance, allowing retrieval using `Observer.getById()`. This is useful for managing multiple Observer instances.

```javascript
const myObserver = Observer.create({
  id: "myScrollObserver"
});

// Later, to get the observer:
// const retrievedObserver = Observer.getById("myScrollObserver");
```

--------------------------------

### GSAP then() for Promise-based Animation Completion (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Tween/then%28%29

This snippet demonstrates using GSAP's then() method to chain animations or execute a function upon completion. It leverages JavaScript Promises for asynchronous control flow. The input is a GSAP tween or timeline, and the output is a Promise that resolves when the animation finishes.

```javascript
gsap.to(".class", {duration: 1, x: 100}).then(yourFunction).then(...);
```

--------------------------------

### Snap Values to Increments or Arrays with snap() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The snap() method snaps a value to either a specified increment or to the closest value within a provided array. This is useful for aligning elements or values to a grid or a predefined set of points. This method is part of GSAP's utility methods.

```javascript
gsap.utils.snap(5, 13) // Output: 15
gsap.utils.snap([0, 5, 10], 7) // Output: 5
```

--------------------------------

### Tween State and Management Methods

Source: https://gsap.com/docs/v3/GSAP/Tween

Methods for managing the state, iteration, and lifecycle of a GSAP tween.

```APIDOC
## GET /websites/gsap_v3/Tween/isActive

### Description
Indicates whether or not the animation is currently active (meaning the virtual playhead is actively moving across this instance's time span and it is not paused, nor are any of its ancestor timelines).

### Method
GET

### Endpoint
/websites/gsap_v3/Tween/isActive

### Response
#### Success Response (200)
- **isActive** (Boolean) - `true` if the tween is active, `false` otherwise.

## GET /websites/gsap_v3/Tween/iteration

### Description
Gets or sets the iteration (the current repeat) of tweens.

### Method
GET

### Endpoint
/websites/gsap_v3/Tween/iteration

### Parameters
#### Query Parameters
- **iteration** (Number) - Optional - The iteration number to set.

### Response
#### Success Response (200)
- **iteration** (Number) - The current iteration number of the tween.

## POST /websites/gsap_v3/Tween/invalidate

### Description
Flushes any internally-recorded starting/ending values, which can be useful if you want to restart an animation without reverting to any previously recorded starting values.

### Method
POST

### Endpoint
/websites/gsap_v3/Tween/invalidate

### Response
#### Success Response (200)
- **message** (String) - Indicates the tween has been invalidated.

## POST /websites/gsap_v3/Tween/kill

### Description
Kills the animation entirely or in part depending on the parameters. To kill means to immediately stop the animation, remove it from its parent timeline, and release it for garbage collection.

### Method
POST

### Endpoint
/websites/gsap_v3/Tween/kill

### Parameters
#### Request Body
- **target** (Object) - Optional - The target object to kill animations on.
- **propertiesList** (String) - Optional - A comma-separated string of properties to kill.

### Response
#### Success Response (200)
- **message** (String) - Indicates the tween has been killed.
```

--------------------------------

### Progressive Timeline Build Function (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/progressiveBuild

This JavaScript function, `progressiveBuild`, helps create a GSAP timeline by executing a sequence of function calls. It takes functions and optional delay values as arguments, organizing them into a timeline with `onComplete` callbacks to manage the sequencing and delays.

```javascript
function progressiveBuild() {
  let data = Array.from(arguments),
    i = 0,
    tl = gsap.timeline({
      onComplete: function () {
        let isNum = typeof data[i] === "number",
          delay = isNum ? data[i++] : 0,
          func = data[i++];
        typeof func === "function" && tl.add(func(), "+=" + delay);
      },
    });
  tl.vars.onComplete();
  return tl;
}
```

--------------------------------

### Tween Callback and Time Methods

Source: https://gsap.com/docs/v3/GSAP/Tween

Methods for managing event callbacks and time-related properties of a GSAP tween.

```APIDOC
## POST /websites/gsap_v3/Tween/eventCallback

### Description
Gets or sets an event callback like `"onComplete", "onUpdate", "onStart"` or `"onRepeat"` along with any parameters that should be passed to that callback.

### Method
POST

### Endpoint
/websites/gsap_v3/Tween/eventCallback

### Parameters
#### Request Body
- **type** (String) - Required - The type of event callback (e.g., "onComplete").
- **callback** (Function) - Required - The function to execute.
- **params** (Array) - Optional - An array of parameters to pass to the callback.

### Response
#### Success Response (200)
- **callback** (Function) - The registered callback function.

## GET /websites/gsap_v3/Tween/globalTime

### Description
Converts a local time to the corresponding time on the `gsap.globalTimeline`, factoring in all nesting, timeScales, etc.

### Method
GET

### Endpoint
/websites/gsap_v3/Tween/globalTime

### Parameters
#### Query Parameters
- **localTime** (Number) - Required - The local time to convert.

### Response
#### Success Response (200)
- **globalTime** (Number) - The converted global timeline time.

## GET /websites/gsap_v3/Tween/endTime

### Description
Returns the time at which the animation will finish according to the parent timeline's local time.

### Method
GET

### Endpoint
/websites/gsap_v3/Tween/endTime

### Parameters
#### Query Parameters
- **includeRepeats** (Boolean) - Optional - If `true`, includes repeat durations in the end time calculation.

### Response
#### Success Response (200)
- **endTime** (Number) - The calculated end time of the tween.
```

--------------------------------

### GSAP seek() - Jump to Time

Source: https://gsap.com/docs/v3/GSAP/Tween/seek%28%29

Demonstrates how to use the seek() method in GSAP v3 to jump an animation to a specific time. The default behavior suppresses events during the jump.

```javascript
myAnimation.seek(2);

// jumps to exactly 2 seconds
```

--------------------------------

### Setting Animation Event Callback with Parameters (GSAP)

Source: https://gsap.com/docs/v3/GSAP/Timeline/eventCallback%28%29

This code snippet demonstrates how to set an 'onComplete' event callback for a GSAP animation, along with custom parameters. It shows the equivalent syntax using both the constructor's 'vars' object and the eventCallback method. The eventCallback method is beneficial for setting callbacks after animation creation.

```javascript
gsap.to(obj, {
  duration: 1,
  x: 100,
  onComplete: myFunction,
  onCompleteParams: ["param1", "param2"],
});

// Equivalent using eventCallback:
myAnimation.eventCallback("onComplete", myFunction, ["param1", "param2"]);
```

--------------------------------

### Toggle Animation Direction (GSAP 3)

Source: https://gsap.com/docs/v3/GSAP/Timeline/reverse%28%29

Demonstrates how to flip the orientation of an animation (forward to backward, or backward to forward) using the reverse() and play() methods, or more concisely with the reversed() method.

```javascript
if (tl.reversed()) {
  tl.play();
} else {
  tl.reverse();
}
```

```javascript
tl.reversed(!tl.reversed());
```

--------------------------------

### Using then() for GSAP Animation Completion (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/Timeline/then%28%29

The then() method returns a Promise that resolves when a GSAP tween or timeline animation completes. This allows for chaining actions or handling completion events using Promise syntax, offering an alternative to traditional onComplete callbacks.

```javascript
gsap.timeline().to(".class", {duration: 1, x: 100}).then(yourFunction).then(...);
```

--------------------------------

### Register GSDevTools Plugin

Source: https://gsap.com/docs/v3/Plugins/GSDevTools

Registers the GSDevTools plugin with GSAP. This is typically the first step before using any GSDevTools functionality. It ensures GSAP recognizes and can utilize the plugin's features.

```javascript
gsap.registerPlugin(GSDevTools)
```

--------------------------------

### Accessing ScrollTrigger .vars Configuration Object (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger/vars

Demonstrates how to create a ScrollTrigger instance and access its .vars property to retrieve the initial configuration. The vars object holds all properties passed during ScrollTrigger.create().

```javascript
let st = ScrollTrigger.create({
  trigger: ".trigger",
  start: "top center",
  end: "+=500",
});

console.log(st.vars); // {trigger: ".trigger", start: "top center", end: "+=500"}
```

--------------------------------

### Split Colors into Components with splitColor() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The splitColor() method splits any color string into its red, green, blue, and optionally alpha components. It can also split colors into hue, saturation, and brightness. This is useful for color manipulation and analysis. This method is part of GSAP's utility methods.

```javascript
gsap.utils.splitColor("red") // Output: [255, 0, 0]
gsap.utils.splitColor("#00ff00", true) // Output: [0, 255, 0, 1]
```

--------------------------------

### Register CustomBounce Plugin (JavaScript)

Source: https://gsap.com/docs/v3/Eases/CustomBounce

Before using CustomBounce, you need to register it along with CustomEase. This makes the CustomBounce functionality available in your GSAP project.

```javascript
gsap.registerPlugin(CustomEase, CustomBounce);
```

--------------------------------

### Animate Element Along SVG Path (Minimal Usage)

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Demonstrates the basic usage of the MotionPathPlugin to animate an element (identified by '#div') along an SVG path (identified by '#path'). The animation lasts for 5 seconds and centers the transform origin.

```javascript
gsap.to("#div", {
  motionPath: {
    path: "#path",
  },
  transformOrigin: "50% 50%",
  duration: 5,
});
```

--------------------------------

### Flip.fit

Source: https://gsap.com/docs/v3/Plugins/Flip

Repositions/resizes one element so that it appears to fit exactly into the same area as another element. Can use `fitChild` to fit based on a child element.

```APIDOC
## POST /websites/gsap_v3/plugins/flip/fit

### Description
Repositions/resizes one element so that it appears to fit exactly into the same area as another element. Using the `fitChild` special property, you can even scale/reposition an element so that one if its *child* elements is used for the fitting calculations instead! By default it alters the transforms (x, y, rotation, and skewX) as well as the width and height of the element, but if you set `scale: true` it will use scaleX and scaleY instead of width and height.

### Method
POST

### Endpoint
/websites/gsap_v3/plugins/flip/fit

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **targetToResize** (String | Element) - Required - The element to reposition/resize.
- **destinationTargetOrState** (String | Element | FlipState) - Required - The target element or state to fit into.
- **vars** (Object) - Optional - An object containing additional properties like `fitChild` or `scale`.
  - **fitChild** (String | Element) - Optional - Specifies a child element to use for fitting calculations.
  - **scale** (Boolean) - Optional - If true, uses scaleX and scaleY instead of width and height.

### Request Example
```json
{
  "targetToResize": "#myElement",
  "destinationTargetOrState": "#destinationElement",
  "vars": {
    "scale": true
  }
}
```

### Response
#### Success Response (200)
- **Timeline** (Object) - A GSAP timeline animation object.

#### Response Example
```json
{
  "message": "Element fitted successfully."
}
```
```

--------------------------------

### Timeline set() Method

Source: https://gsap.com/docs/v3/GSAP/Timeline/set%28%29

The `set()` method is a convenience method for adding a zero-duration tween to a timeline that immediately sets specific property values on a target object.

```APIDOC
## POST /websites/gsap_v3/set

### Description
Adds a zero-duration tween to the end of the timeline (or elsewhere using the `position` parameter) that sets values immediately when the virtual playhead reaches that position on the timeline. This is a convenience method that accomplishes exactly the same thing as `add(gsap.to(target, {duration: 0, ...}) )` but with less code.

### Method
POST

### Endpoint
`/websites/gsap_v3/set`

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **target** (Object | Array | String) - Required - Target object (or array of objects) whose properties will be set.
- **vars** (Object) - Required - An object defining the value to which each property should be set. For example, to set element's `left` to 100 and element's `top` to 200, do this: `myTimeline.set(element, {left: 100, top: 200});`
- **position** (Number | String) - Optional - Controls the insertion point in the timeline (by default, it's the end of the timeline). See options below, or the [Position Parameter article](/resources/position-parameter.md) which has interactive timeline visualizations and a video. If you define a label that doesn't exist yet, it will **automatically be added to the end of the timeline** (default = `"+=0"`).

### Request Example
```json
{
  "target": "#myElement",
  "vars": {
    "x": 100,
    "opacity": 0.5
  },
  "position": "+=1"
}
```

### Response
#### Success Response (200)
- **self** (Object) - Returns the timeline instance, making chaining easier.

#### Response Example
```json
{
  "message": "Tween added successfully",
  "timeline_instance": "[object Object]" 
}
```

### Details
Adds a [`gsap.set()`](/docs/v3/GSAP/gsap.set().md) to the end of the timeline (or elsewhere using the "position" parameter) - this is a convenience method that accomplishes exactly the same thing as `add(gsap.set(...) )` but with less code. For example:

```javascript
var tl = gsap.timeline();

var setValues = gsap.set(element, { x: 100, opacity: 0.5 });
tl.add(setValues);

//this line produces the same result as the previous two lines (just shorter)
tl.set(element, { x: 100, opacity: 0.5 });
```

**See the [gsap.set() docs](/docs/v3/GSAP/gsap.set().md) for all the details and special properties available for a `set()`**. You can chain these calls together and use other convenience methods like [`to()`](/docs/v3/GSAP/Timeline/to().md), [`call()`](/docs/v3/GSAP/Timeline/call().md), [`from()`](/docs/v3/GSAP/Timeline/from().md), etc. to build out sequences very quickly:

```javascript
//create a timeline that calls myFunction() when it completes
var tl = gsap.timeline({ onComplete: myFunction });

//now we'll use chaining, but break each step onto a different line for readability...

//tween element's x from -100
tl.from(element, { duration: 1, x: -100 })

  //then tween element's y to 50
  .to(element, { duration: 1, y: 50 })

  //then set element's opacity to 0.5 immediately
  .set(element, { opacity: 0 })

  //then call otherFunction()
  .call(otherFunction)

  //finally tween the rotation of all elements with the class "myClass" to 45 and stagger the start times by 0.25 seconds
  .to(".myClass", { duration: 1.5, rotation: 45, stagger: 0.25 });
```
```

--------------------------------

### Configuring trackDirection with Callbacks for a Tween (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/trackDirection

Illustrates how to use trackDirection with configuration options when applied to a tween's onUpdate callback. This allows specifying both 'onToggle' for direction change notifications and 'onUpdate' for general animation updates, including logging to the console.

```javascript
gsap.to(
  ...,
  {
    x: 100,
    onUpdate: trackDirection({
      onToggle: (direction) => console.log("toggled direction to", direction),
      onUpdate: (direction) => console.log("updated animation"),
    }),
  }
);
```

--------------------------------

### MorphSVGPlugin Properties

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

This section details the properties that can be used to configure the morphSVG tween.

```APIDOC
## MorphSVGPlugin Properties

This section details the properties that can be used to configure the morphSVG tween.

### shapeIndex

#### Description
The `shapeIndex` property controls how the points in the start shape are mapped to the ones in the end shape. It acts as an offset for matching points between shapes.

#### Method
`gsap.to(target, { morphSVG: { shape: "#endShape", shapeIndex: value } })`

#### Endpoint
N/A (Plugin Property)

#### Parameters

##### Path Parameters
N/A

##### Query Parameters
N/A

##### Request Body (morphSVG object)
- **shape** (string) - Required - A selector or element for the target shape.
- **shapeIndex** (number) - Optional - The offset value for mapping points. A positive number shifts the start point, a negative number reverses the path.

### Request Example
```json
{
  "duration": 1,
  "morphSVG": {
    "shape": "#star",
    "shapeIndex": 3
  }
}
```

### Response

#### Success Response (200)
N/A (Plugin Property)

#### Response Example
N/A

---

### smooth

#### Description
Adds extra "smoothing" anchor points to the artwork to make the morph look more natural. This can be a number, "auto", or an object for more detailed control.

#### Method
`gsap.to(target, { morphSVG: { shape: "#endShape", smooth: value } })`

#### Endpoint
N/A (Plugin Property)

#### Parameters

##### Path Parameters
N/A

##### Query Parameters
N/A

##### Request Body (morphSVG object)
- **shape** (string) - Required - A selector or element for the target shape.
- **smooth** (number | "auto" | object) - Optional - Controls the amount of smoothing.
  - **points** (number | "auto") - The number of points to use for smoothing.
  - **redraw** (boolean) - If `true`, the path is redrawn with new anchor points (default). If `false`, original anchor points are maintained for perfect fidelity.
  - **persist** (boolean) - If `true`, the smoothed shape persists after the animation (default). If `false`, it reverts to the original shape.

### Request Example
```json
{
  "duration": 1,
  "morphSVG": {
    "shape": "#lightning",
    "smooth": {
      "points": 40,
      "redraw": false,
      "persist": false
    }
  }
}
```

### Response

#### Success Response (200)
N/A (Plugin Property)

#### Response Example
N/A

---

### type

#### Description
Determines the interpolation method for shape morphing. Can be "linear" (default) or "rotational".

#### Method
`gsap.to(target, { morphSVG: { shape: "#endShape", type: "rotational" } })`

#### Endpoint
N/A (Plugin Property)

#### Parameters

##### Path Parameters
N/A

##### Query Parameters
N/A

##### Request Body (morphSVG object)
- **shape** (string) - Required - A selector or element for the target shape.
- **type** (string) - Optional - The interpolation type. Accepts "linear" or "rotational".

### Request Example
```json
{
  "duration": 2,
  "morphSVG": {
    "shape": "#shape2",
    "type": "rotational"
  }
}
```

### Response

#### Success Response (200)
N/A (Plugin Property)

#### Response Example
N/A
```

--------------------------------

### Minimal ScrambleText Animation

Source: https://gsap.com/docs/v3/Plugins/ScrambleTextPlugin

Demonstrates the most basic usage of the ScrambleText plugin. It tweens an element's text to a new string over a specified duration, using default scrambling settings.

```javascript
gsap.to(element, {
  duration: 1,
  scrambleText: "THIS IS NEW TEXT"
});
```

--------------------------------

### GSAP Utility: normalize

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `normalize` utility method maps a number within a given range to a progress value between 0 and 1. It takes the minimum value of the range, the maximum value of the range, and the number to normalize. This is often used to calculate animation progress based on scroll position or other metrics.

```javascript
gsap.utils.normalize(100, 200, 150); // Returns 0.5
gsap.utils.normalize(0, 10, 5);     // Returns 0.5
gsap.utils.normalize(0, 10, 12);    // Returns 1.2
```

--------------------------------

### GSAP Tween Ratio vs. Progress

Source: https://gsap.com/docs/v3/GSAP/Tween/ratio

This snippet demonstrates the difference between a tween's 'progress' and its 'ratio' after applying an ease function. The 'ratio' reflects the eased progress, which can be higher than the raw progress for eases like 'power2.out'.

```javascript
const easeFunc = gsap.parseEase("power2.out");
const tween = gsap.to({ foo: 0 }, { foo: 10, duration: 1, ease: "power2.out" });
tween.pause(0.5); // pause at 0.5 seconds which is halfway in this 1-second tween

console.log(tween.progress()); // 0.5
console.log(tween.ratio); // 0.875
console.log(easeFunc(tween.progress())); // 0.875
```

--------------------------------

### GSAP MotionPathPlugin Animation

Source: https://gsap.com/docs/v3/Plugins/MotionPathHelper

Animates an element with the class 'astronaut' along an SVG path defined by the ID 'path'. It registers the MotionPathPlugin, sets initial properties for the astronaut, and configures the animation using motionPath properties.

```javascript
//register the plugin (just once)
gsap.registerPlugin(MotionPathPlugin);

gsap.set(".astronaut", {scale: 0.5, autoAlpha: 1});

gsap.to(".astronaut", {
  duration: 5,
  ease: "power1.inOut",
  immediateRender: true,
  motionPath: {
    path: "#path",
    align: "#path",
    alignOrigin: [0.5, 0.5],
    autoRotate: 90
  }
});

MotionPathHelper.create(".astronaut");
```

--------------------------------

### GSAP SplitText: Responsive Line Splitting with autoSplit

Source: https://gsap.com/docs/v3/Plugins/SplitText

Enables responsive line splitting using autoSplit, which automatically re-splits text when container width changes and lines are split. Animations are created within the onSplit() callback for seamless updates. Dependencies include GSAP and SplitText.

```javascript
SplitText.create(".split", {
    type: "words,lines",
    autoSplit: true,
    onSplit(self) {
      return gsap.from(self.lines, {
        yPercent: 20,
        opacity: 0,
        stagger: 1,
        duration: 3,
        onComplete: () => self.revert()
      });
    }
  });
```

--------------------------------

### GSAP Timeline Labels

Source: https://gsap.com/docs/v3/GSAP

Shows how to add and use labels within a GSAP timeline. Labels mark specific points in time, allowing for easier navigation and animation placement.

```javascript
//add a label at exactly 3 seconds
tl.addLabel("step2", 3)

//then later, we can seek() to that spot:
tl.seek("step2");
```

--------------------------------

### Register EaselPlugin with GSAP

Source: https://gsap.com/docs/v3/Plugins/EaselPlugin

This code snippet shows how to register the EaselPlugin with GSAP, which is necessary before using its features. Ensure the EaselJS library is loaded.

```javascript
gsap.registerPlugin(EaselPlugin)
```

--------------------------------

### GSAP SplitText autoSplit with onSplit Callback

Source: https://gsap.com/docs/v3/Plugins/SplitText

Demonstrates how to use the `autoSplit: true` option with SplitText to automatically re-split text when conditions change, such as font loading or element width changes. The `onSplit` callback is used to apply animations to the newly split elements, ensuring they are animated correctly after re-splitting. This is crucial for dynamic text layouts.

```javascript
SplitText.create(".split", {
  type: "lines",
  autoSplit: true,
  onSplit: (self) => {
    return gsap.from(self.lines, {
      y: 100,
      opacity: 0,
      stagger: 0.05
    });
  }
});
```

--------------------------------

### GSAP Utility: mapRange

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `mapRange` utility method maps a value from one range to another. It takes the input range (min, max) and the output range (min, max), and then the value to map. It returns the corresponding value in the output range. This is useful for converting values between different scales.

```javascript
gsap.utils.mapRange(-10, 10, 0, 100, 5);  // Returns 75
gsap.utils.mapRange(0, 1, 10, 20, 0.5); // Returns 15
```

--------------------------------

### Create Scoped Selector Function (Vanilla JS)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/selector%28%29

Demonstrates how to create a reusable selector function scoped to a specific DOM element using GSAP's selector utility. This function can then be used to select descendant elements within that scope, returning an Array for easier manipulation.

```javascript
let q = gsap.utils.selector(myElement); // or use selector text like ".class"
let boxes = q(".box"); // finds only elements with the class "box" that are INSIDE myElement
// or plug directly into animations
gsap.to(q(".circle"), { x: 100 });
```

--------------------------------

### Register GSAP Flip Plugin

Source: https://gsap.com/docs/v3/Plugins/Flip

Registers the GSAP Flip plugin, making its functionality available for use in animations. This is typically the first step before utilizing any Flip-related methods.

```javascript
gsap.registerPlugin(Flip)
```

--------------------------------

### Configure Inertia Plugin with Snap Functionality

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet demonstrates how to configure the InertiaPlugin for Draggable to snap an element to specific increments after release. It uses a function to calculate the snapping value, ensuring the element lands on the closest multiple of 50.

```javascript
Draggable.create(element, {
  inertia: true,
  snap: function(endValue) {
    return Math.round(endValue / 50) * 50;
  }
});
```

--------------------------------

### Live Snap Functionality for Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

Defines snapping rules applied during dragging. Can be a function, array of values, object for property-specific rules, or a boolean to use the main 'snap' property.

```javascript
Draggable.create(element, {
  // Example 1: Snap to the closest increment of 50
  liveSnap: function(value) {
    return Math.round(value / 50) * 50;
  }
});

Draggable.create(element, {
  // Example 2: Snap to a predefined array of values
  liveSnap: [10, 50, 200, 450]
});

Draggable.create(element, {
  // Example 3: Object for property-specific snapping (e.g., x and y)
  liveSnap: {
    x: [5, 20, 80, 400],
    y: function(value) {
      return Math.round(value / 100) * 100;
    }
  }
});

Draggable.create(element, {
  // Example 4: Using 'points' for complex snapping
  liveSnap: {
    points: [{x: 0, y: 0}, {x: 100, y: 0}],
    radius: 20
  }
});

Draggable.create(element, {
  // Example 5: Using boolean true to apply main 'snap' rules live
  snap: 50, // Main snap value
  liveSnap: true
});
```

--------------------------------

### Configure Draggable Movement Constraints

Source: https://gsap.com/docs/v3/Plugins/Draggable

Allows setting minimum movement thresholds for drag detection and locking movement to a single axis after initial movement. Useful for differentiating clicks from drags and preventing diagonal movement.

```javascript
Draggable.create(element, {
  type: "x,y",
  lockAxis: true,
  minimumMovement: 5
});
```

--------------------------------

### GSAP Unit Handling and Conversion

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/CSS

Shows how GSAP handles default units and allows specifying custom units for properties like rotation and translation. GSAP automatically converts units if the current and target units differ.

```javascript
gsap.to(HTMLelement, {
  rotation: 360, // default deg
  rotation: "1.25rad", // use radians instead
  x: 24, // using px
  x: "20vw" // use viewport widths instead
});
```

--------------------------------

### startY Property

Source: https://gsap.com/docs/v3/Plugins/Draggable/startY

The startY property provides the initial vertical position of a Draggable instance when a drag operation begins. This value is read-only and reflects the element's vertical transform or CSS 'top' property depending on the Draggable configuration.

```APIDOC
## startY Property

### Description

The `startY` property is a read-only numeric value that indicates the starting vertical (y) position of the Draggable instance when the most recent drag operation commenced. This value is crucial for understanding the initial state of the element before user interaction.

### Method

GET (Implicit - This is a property, not an endpoint)

### Endpoint

N/A (This is a property of a Draggable instance)

### Parameters

This property does not take any parameters.

### Request Example

```javascript
// Assuming 'draggableInstance' is an initialized Draggable instance
const initialY = draggableInstance.startY;
console.log("Starting Y position:", initialY);
```

### Response

#### Success Response (Property Value)

- **startY** (Number) - The initial vertical position (y-coordinate) when the drag started. This value is relative to the element's transform or CSS 'top' property, not a global coordinate.

#### Response Example

```json
{
  "startY": 150
}
```
```

--------------------------------

### GSAP checkPrefix Utility

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/checkPrefix%28%29

The checkPrefix utility takes a CSS property name and returns its browser-prefixed version if necessary. If no prefix is required, it returns the original property name. If the property is not recognized, it returns undefined.

```APIDOC
## GSAP checkPrefix Utility

### Description

This utility function checks a given CSS property name and returns the browser-prefixed version if one is necessary. If the property does not require a prefix, the original name is returned. If the property is not a valid CSS property, `undefined` is returned.

### Method

`gsap.utils.checkPrefix(property)`

### Parameters

#### Path Parameters

None

#### Query Parameters

None

#### Request Body

None

### Parameters

1. **property** (*String*) - Required - The name of the CSS property to check (e.g., "filter").

### Request Example

```javascript
// Example usage:
var prefixedFilter = gsap.utils.checkPrefix("filter");
console.log(prefixedFilter); // Output might be "filter", "WebkitFilter", or "MozFilter" depending on the browser.

var unknownProperty = gsap.utils.checkPrefix("nonExistentProperty");
console.log(unknownProperty); // Output: undefined
```

### Response

#### Success Response (String)

- **prefixedProperty** (*String*) - The browser-prefixed version of the property name, the original name if no prefix is needed, or `undefined` if the property is not recognized.

#### Response Example

```json
{
  "example": "WebkitFilter"
}
```

#### Error Response

- **undefined** - Returned if the provided property name is not a valid CSS property.

#### Error Response Example

```json
{
  "example": "undefined"
}
```
```

--------------------------------

### MotionPathHelper.editPath

Source: https://gsap.com/docs/v3/MotionPathHelper/static

Makes an SVG <path> element editable in the browser, allowing for interactive manipulation of the path's anchors and handles. It accepts the path element (or a selector) and an optional configuration object.

```APIDOC
## MotionPathHelper.editPath

### Description
Makes an SVG `<path>` element editable in the browser. This function allows users to interactively modify the path's shape by adding, deleting, or adjusting anchor points and their handles.

### Method
`MotionPathHelper.editPath(path: Element | String, config?: Object): PathEditor`

### Parameters
#### Path Parameter
* **path** (Element | String) - Required - The SVG `<path>` element to be edited. This can be a direct reference to the element or a CSS selector string.

#### Config Object (Optional)
An optional configuration object that allows customization of the editing experience. It can include properties like `draggable`, `handleSize`, `selected`, callback functions (`onPress`, `onRelease`, `onUpdate`, `onDeleteAnchor`), etc.

### Returns
* **PathEditor** - An object representing the path editor instance, providing methods for further control or information about the edited path.

### Configuration Options
| Property | Description |
|---|---|
| `draggable` | Boolean - Determines if the path should be selected initially. |
| `handleSize` | Number - The radius of the anchor points/handles. |
| `onDeleteAnchor` | Function - A callback function invoked when an anchor point is deleted. |
| `onPress` | Function - A callback function invoked when an anchor or the path is pressed (mousedown/pointerdown/touchstart). |
| `onRelease` | Function - A callback function invoked when the mouse/pointer is released (mouseup/pointerup/touchend/touchcancel). |
| `onUpdate` | Function - A callback function invoked when the path is updated in any way. |
| `selected` | Boolean - Whether or not the path will be selected initially. |

### Examples
#### Simple Example
```javascript
MotionPathHelper.editPath("#my-path");
```

#### Advanced Example
```javascript
MotionPathHelper.editPath("#my-path", {
  handleSize: 7,
  selected: true,
  draggable: true,
  onPress: () => console.log("pressed"),
  onRelease: () => console.log("released"),
  onUpdate: () => console.log("updated"),
  onDeleteAnchor: () => console.log("deleted anchor"),
});
```

### Editing Tips
* **Add point**: ALT-Click somewhere on the path.
* **Toggle smooth/corner anchor**: ALT-Click the anchor.
* **Get handle from corner anchor**: ALT-Drag.
* **Select multiple anchors**: SHIFT-Click (and again to deselect).
* **Delete anchor**: Select it, then press the DELETE key.
* **Undo**: CTRL-Z.
* Click and drag on handles to change how the path curves.
* **Drag entire path**: Click and drag on a part of the path that doesn't have an anchor.
```

--------------------------------

### Timeline smoothChildTiming Property

Source: https://gsap.com/docs/v3/GSAP/Timeline/vars

Controls whether child animations are automatically repositioned to maintain smooth playback when timing properties change.

```APIDOC
## Timeline smoothChildTiming

### Description
Controls whether child animations are automatically repositioned (changing their `startTime`) to maintain smooth playback when timing-related properties are changed on-the-fly. For example, if the timeline’s playhead is on a child tween that is 75% complete, and that tween’s `reverse()` method is called. If `smoothChildTiming` is `false` (the default except for the globalTimeline), the tween would flip in place, keeping its `startTime` consistent. Therefore the playhead of the timeline would now be at the tween’s 25% completion point instead of 75%.

### Method
N/A (This is a property, not an endpoint)

### Endpoint
N/A

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
```json
{
  "smoothChildTiming": true
}
```

### Response
#### Success Response (200)
N/A (This is a property setting)

#### Response Example
N/A
```

--------------------------------

### Normalize a Value Immediately (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/normalize%28%29

This snippet demonstrates how to use GSAP's normalize() method to immediately convert a value from a specified range (minimum, maximum) to a normalized value between 0 and 1. It takes three arguments: the minimum of the range, the maximum of the range, and the value to normalize.

```javascript
gsap.utils.normalize(-10, 10, 0); // Returns 0.5
gsap.utils.normalize(0, 100, 25); // Returns 0.25
```

--------------------------------

### Register GSAP PixiPlugin

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin

This snippet shows how to register the PixiPlugin with GSAP and provide it with a reference to the PIXI object. This is a prerequisite for using the plugin's features.

```javascript
import * as PIXI from "pixi.js";
import { gsap } from "gsap";
import { PixiPlugin } from "gsap/PixiPlugin";

// register the plugin
gsap.registerPlugin(PixiPlugin);

// give the plugin a reference to the PIXI object
PixiPlugin.registerPIXI(PIXI);
```

--------------------------------

### Accessing Inertia Tween

Source: https://gsap.com/docs/v3/Plugins/Draggable/tween

This section details how to access the tween instance created when inertia is enabled. The tween is available via `this.tween` within the `onDragEnd` callback, allowing control over its properties like duration, pause/resume, and timeScale.

```APIDOC
## GET /websites/gsap_v3/tween

### Description
Accesses the read-only tween instance created when inertia is enabled and the user releases the mouse or touch. This allows for manipulation of the tween's properties.

### Method
GET

### Endpoint
/websites/gsap_v3/tween

### Parameters
#### Query Parameters
- **inertia** (boolean) - Required - Set to `true` to enable inertia and generate a tween.

### Request Example
```
GET /websites/gsap_v3/tween?inertia=true
```

### Response
#### Success Response (200)
- **tween** (object) - The Tween instance. Properties include `duration`, `pause()`, `resume()`, `timeScale()`, etc.

#### Response Example
```json
{
  "tween": {
    "duration": 1.5,
    "progress": 0.75,
    "timeScale": 1,
    "paused": false
  }
}
```

### Details
When `inertia` is `true`, a new Tween instance is created upon mouse or touch release. This instance, accessible as `this.tween` within the `onDragEnd` callback, provides control over the animation's progression. For example, you can pause, resume, or adjust the playback speed using methods like `pause()`, `resume()`, and `timeScale()`.
```

--------------------------------

### MotionPathPlugin.stringToRawPath

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Converts a string representation of a path into a RawPath Array.

```APIDOC
## MotionPathPlugin.stringToRawPath

### Description
Converts a string representation of a path into a RawPath Array.

### Method
STATIC

### Endpoint
MotionPathPlugin.stringToRawPath(data:String)

### Parameters
#### Path Parameters
- **data** (String) - Required - The string data of the path.

### Response
#### Success Response (200)
- **RawPath** (Array) - The RawPath Array representation of the string data.
```

--------------------------------

### MotionPathPlugin.rawPathToString

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Converts a RawPath Array into a string format.

```APIDOC
## MotionPathPlugin.rawPathToString

### Description
Converts a RawPath Array into a string format.

### Method
STATIC

### Endpoint
MotionPathPlugin.rawPathToString(rawPath:Array)

### Parameters
#### Path Parameters
- **rawPath** (Array) - Required - The RawPath Array to convert.

### Response
#### Success Response (200)
- **String** - The string representation of the RawPath.
```

--------------------------------

### InertiaPlugin Automatic Duration Control

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin

Shows how InertiaPlugin automatically calculates the tween duration for a natural feel, and how to optionally set a fixed duration or a range for it. This ensures consistent deceleration regardless of initial velocity.

```javascript
// Automatic duration (default behavior)
inertia: {
  // ... other properties
},

// Hard-coded duration
duration: 2,

// Duration range
duration: {
  min: 0.5,
  max: 3
}
```

--------------------------------

### GSAP BackgroundSizePlugin for Responsive Animations

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/bgSize

This unofficial GSAP plugin extends GSAP's capabilities to animate `backgroundSize` directly to 'cover' or 'contain' values, ensuring responsiveness. It also allows for scaling and applies the actual 'cover' or 'contain' value rather than a pixel equivalent after the tween.

```javascript
// This is a conceptual representation. The actual plugin code would be provided separately.
// Example usage:
gsap.to(".my-element", {
  backgroundSize: "cover", // or "contain"
  duration: 1,
  // other plugin-specific properties like scale, etc.
});
```

--------------------------------

### GSAP Pipe Function for Chained Transformations

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/interpolate%28%29

Illustrates the use of GSAP's pipe utility function to chain multiple utility methods together. This allows for a sequence of operations (like clamping, normalizing, and interpolating) to be applied to a single input value, creating powerful and reusable data transformation pipelines.

```javascript
// get a clamping function that will always clamp to a range between 0 and 100
var colorizer = gsap.utils.pipe(
  // clamp between 0 and 100
  gsap.utils.clamp(0, 100),

  // normalize to a value between 0 and 1
  gsap.utils.normalize(0, 100),

  // then interpolate between red and blue
  gsap.utils.interpolate("red", "blue")
);

// now we feed one value in and it gets run through ALL those transformations!:
colorizer(25.874);
```

--------------------------------

### Minimal Draggable Element Creation

Source: https://gsap.com/docs/v3/Plugins/Draggable

Demonstrates the most basic usage of the Draggable plugin to make an element draggable along the x-axis. This requires a DOM element with the ID 'yourID' to exist.

```javascript
Draggable.create('#yourID', {
	type: 'x'
});
```

--------------------------------

### Kill Entire Animation - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/kill%28%29

This code snippet demonstrates how to completely kill an animation using the kill() method without any parameters. It also shows how to set the animation reference to null for garbage collection.

```javascript
animation.kill();

// set to null so the reference is removed
animation = null;
```

--------------------------------

### Animate 3D Properties with GSAP

Source: https://gsap.com/docs/v3/GSAP/CorePlugins/CSS

This snippet demonstrates animating multiple 3D and 2D transform properties simultaneously using GSAP's to() method. It requires the GSAP library. Inputs are the target element and an object containing animation properties like duration, rotationX, scaleX, and z. Outputs are animated element properties.

```javascript
gsap.to(element, {
  duration: 2,
  rotationX: 45,
  scaleX: 0.8,
  z: -300,
});
```

--------------------------------

### Register GSAP Physics2DPlugin via CDN

Source: https://gsap.com/docs/v3/Plugins/Physics2DPlugin

This code snippet demonstrates how to register the Physics2DPlugin for use with GSAP animations. It requires including the GSAP library and the Physics2DPlugin script via CDN links.

```javascript
gsap.registerPlugin(Physics2DPlugin)
```

--------------------------------

### Register PIXI Library with PixiPlugin (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/PixiPlugin/static

Registers the main PIXI library object with PixiPlugin. This is necessary when PIXI is not available in the global scope, common in module bundler or ES module environments. It allows PixiPlugin to access PIXI classes and objects.

```javascript
import { gsap } from "gsap";
import { PixiPlugin } from "gsap/PixiPlugin";
import * as PIXI from "pixi.js";

gsap.registerPlugin(PixiPlugin);
PixiPlugin.registerPIXI(PIXI);
```

```javascript
import { gsap } from "gsap";
import { PixiPlugin } from "gsap/PixiPlugin";

import { Container, Sprite, BlurFilter, ColorMatrixFilter } from "https://cdn.skypack.dev/pixi.js";

PixiPlugin.registerPIXI({
  Container,
  Sprite,
  BlurFilter,
  ColorMatrixFilter
});
```

--------------------------------

### Timeline previousLabel()

Source: https://gsap.com/docs/v3/GSAP/Timeline/previousLabel%28%29

Retrieves the name of the label that occurs before a specified time on the GSAP timeline. If no time is provided, it defaults to the current playhead position.

```APIDOC
## GET /websites/gsap_v3/timeline/previousLabel

### Description
Returns the previous label in the timeline from the provided `time`. If no `time` is provided, the timeline's current playhead time will be used. A label positioned exactly at the same `time` as the time parameter will be ignored.

### Method
GET

### Endpoint
`/websites/gsap_v3/timeline/previousLabel`

### Parameters
#### Query Parameters
- **time** (Number) - Optional - The time to get the previous label from.

### Request Example
```json
{
  "time": 1.5
}
```

### Response
#### Success Response (200)
- **labelName** (String) - The name of the label that occurs before the specified time.

#### Response Example
```json
{
  "labelName": "myLabel"
}
```
```

--------------------------------

### Configure AutoKill Globally

Source: https://gsap.com/docs/v3/Plugins/ScrollToPlugin

Sets the `autoKill` property to `true` globally for all ScrollToPlugin instances using the `ScrollToPlugin.config()` method. This simplifies configuration if you want auto-killing enabled for all scroll animations throughout your project.

```javascript
ScrollToPlugin.config({ autoKill: true })
```

--------------------------------

### GSAP Utility: clamp() - Reusable Function

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/clamp%28%29

Creates a reusable function that remembers the minimum and maximum values, allowing you to clamp multiple values efficiently without re-specifying the range each time.

```APIDOC
## POST /utils/clamp/create

### Description
Creates a reusable function that accepts a value to clamp between a predefined minimum and maximum. This is useful for repeatedly clamping values within the same range.

### Method
POST

### Endpoint
/utils/clamp/create

### Parameters
#### Request Body
- **minimum** (Number) - Required - The minimum value for the reusable function.
- **maximum** (Number) - Required - The maximum value for the reusable function.

### Request Example
```json
{
  "minimum": 0,
  "maximum": 100
}
```

### Response
#### Success Response (200)
- **clamperFunctionId** (String) - An identifier for the created reusable clamping function.

#### Response Example
```json
{
  "clamperFunctionId": "unique_clamper_id_123"
}
```

## POST /utils/clamp/execute

### Description
Executes a previously created reusable clamping function with a given value.

### Method
POST

### Endpoint
/utils/clamp/execute

### Parameters
#### Request Body
- **clamperFunctionId** (String) - Required - The identifier of the reusable clamping function to execute.
- **valueToClamp** (Number) - Required - The value to be clamped.

### Request Example
```json
{
  "clamperFunctionId": "unique_clamper_id_123",
  "valueToClamp": 105
}
```

### Response
#### Success Response (200)
- **clampedValue** (Number) - The result of clamping the value using the specified reusable function.

#### Response Example
```json
{
  "clampedValue": 100
}
```
```

--------------------------------

### Observer Configuration: Debounce Events

Source: https://gsap.com/docs/v3/Plugins/Observer/static

Controls whether Observer debounces events for additive deltas, optimizing performance. Disabling `debounce: false` checks events immediately on every occurrence, affecting delta-related callbacks.

```javascript
Observer.create({
  debounce: false
});
```

--------------------------------

### MotionPathPlugin.getLength

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Calculates and returns the total length of a given path.

```APIDOC
## MotionPathPlugin.getLength

### Description
Returns the length of a path.

### Method
STATIC

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
*   **path** (Element | String | RawPath) - The path element, a selector string, or a RawPath array.

### Request Example
```json
{
  "path": document.getElementById('myPath')
}
```

### Response
#### Success Response (200)
*   **Number** (Number) - The total length of the path.

#### Response Example
```json
500.75
```
```

--------------------------------

### GSAP seek() - Jump to Time with Events

Source: https://gsap.com/docs/v3/GSAP/Tween/seek%28%29

Illustrates using the seek() method in GSAP v3 to jump an animation to a specific time while also triggering events during the jump by setting suppressEvents to false.

```javascript
myAnimation.seek(2, false);

// jumps to exactly 2 seconds but doesn't suppress events during the initial move
```

--------------------------------

### Clamp a number directly

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/clamp%28%29

This method clamps a given number between a specified minimum and maximum value. It's useful for ensuring values stay within a valid range, like percentages or pixel positions. No external dependencies are required beyond GSAP.

```javascript
gsap.utils.clamp(0, 100, 105); // returns 100
gsapsap.utils.clamp(0, 100, -50); // returns 0
gsapsap.utils.clamp(0, 100, 20); // returns 20
```

--------------------------------

### Define Motion Path using SVG Path Data String

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Illustrates how to define the motion path directly using an SVG path data string. This method is useful when you have path data but not an actual SVG element in the DOM.

```javascript
motionPath: "M9,100c0,0,18-41,49-65";
```

--------------------------------

### ScrollSmoother .kill()

Source: https://gsap.com/docs/v3/Plugins/ScrollSmoother/kill%28%29

The .kill() method is used to completely stop and remove the ScrollSmoother instance, including any effects that were applied. This is useful for cleaning up resources when the ScrollSmoother is no longer needed.

```APIDOC
## .kill()

### Description
Kills the entire ScrollSmoother as well as any effects that were applied.

### Method
`JavaScript`

### Endpoint
N/A (This is a method call on an instance)

### Parameters
None

### Request Example
```javascript
ScrollSmoother.get("#myScrollSmoother").kill();
```

### Response
N/A (This method does not return a value, it performs an action.)

#### Success Response (N/A)
N/A

#### Response Example
N/A
```

--------------------------------

### Minimal MorphSVG Usage

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Demonstrates the most basic usage of MorphSVG to animate a shape to another shape. It targets an element with the ID 'circle' and morphs it to the shape defined by the ID 'lightning' over 1 second.

```javascript
gsap.to("#circle", { duration: 1, morphSVG: "#lightning" });
```

--------------------------------

### Configure ScrollToPlugin Global Settings (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/ScrollToPlugin/config%28%29

The ScrollToPlugin.config() method allows you to set global configurations for the ScrollToPlugin. The 'autoKill' property, when set to true, automatically cancels scroll tweens if the scroll position is changed manually.

```javascript
ScrollToPlugin.config({ autoKill: true });
```

--------------------------------

### Align Element to Motion Path using Selector Text

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This snippet illustrates aligning the animated element to a motion path using a CSS selector. The element's top-left corner will be aligned with the specified path element.

```javascript
align: "#path"
```

--------------------------------

### Sequence Function Calls with pipe() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The pipe() method sequences a number of function calls, passing the result of each into the next. It's useful for creating complex data transformations by chaining simpler functions. This method is part of GSAP's utility methods.

```javascript
gsap.utils.pipe(clamp(0, 100), snap(5))(8)
```

--------------------------------

### revert() Method

Source: https://gsap.com/docs/v3/Plugins/SplitText/revert%28%29

The revert() method in GSAP v3 is used to restore the original content of an element, typically after a split animation, and also internally calls the kill() method to stop any ongoing animations.

```APIDOC
## revert()

### Description
Reverts to the original content (the innerHTML before the split) and also calls kill() internally.

### Method
`revert()`

### Endpoint
N/A (This is a method, not an API endpoint)

### Parameters
None

### Request Example
```javascript
// Assuming 'myAnimation' is a GSAP animation object that has been split
myAnimation.revert();
```

### Response
This method does not return a value. It modifies the state of the animation and the target element.
```

--------------------------------

### Configuring trackDirection with Callbacks for an Animation (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/trackDirection

Demonstrates configuring trackDirection with specific callbacks ('onToggle' and 'onUpdate') when assigning it to a GSAP animation object. This provides detailed control over when and how direction change notifications are handled.

```javascript
trackDirection({
  animation: tl,
  onToggle: (direction) => console.log("toggled direction to", direction),
  onUpdate: (direction) => console.log("updated animation"),
});
```

--------------------------------

### GSAP Utility: interpolate

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `interpolate` utility method creates a function that interpolates between two values. It can handle various data types including numbers, colors, strings, arrays, and objects. The returned function takes a progress value (0 to 1) and returns the interpolated value.

```javascript
const colorInterpolate = gsap.utils.interpolate("red", "blue");
colorInterpolate(0.5); // Returns "rgb(128, 0, 128)"

const numInterpolate = gsap.utils.interpolate(0, 100);
numInterpolate(0.25); // Returns 25
```

--------------------------------

### Disable immediate rendering with tweenFromTo

Source: https://gsap.com/docs/v3/GSAP/Timeline/tweenFromTo%28%29

This snippet illustrates how to prevent the timeline from immediately jumping to the 'from' position by setting immediateRender to false. This provides more control over the initial state of the tween.

```javascript
tl.tweenFromTo(1, 5, {immediateRender: false});
```

--------------------------------

### Register GSAP Plugin

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

This code snippet demonstrates how to register a GSAP plugin, such as ScrollTrigger or a custom plugin. Registration is essential to prevent plugins from being removed by tree shaking during production builds and to ensure they are available for use in your animations.

```javascript
gsap.registerPlugin(ScrollTrigger)
```

```javascript
gsap.registerPlugin(undefined)
```

--------------------------------

### Setting Timeline Defaults in GSAP v3

Source: https://gsap.com/docs/v3/GSAP/Timeline

Demonstrates how to set default properties for child tweens within a GSAP timeline using the `defaults` object. This reduces code repetition for common properties like `duration` and `ease`. Child tweens inherit these defaults unless explicitly overridden.

```javascript
// WITHOUT defaults (long)
var tl = gsap.timeline();
tl.to(".class1", { rotation: -270, duration: 1, ease: "elastic" })
  .to(".class2", { rotation: -360, duration: 1, ease: "elastic" })
  .to(".class3", { rotation: -180, duration: 1, ease: "elastic" });

//WITH defaults (shorter)
var tl = gsap.timeline({ defaults: { duration: 1, ease: "elastic" } });
tl.to(".class1", { rotation: -270 }) //child tweens will inherit the duration and from the parent timeline!
  .to(".class2", { rotation: -360 })
  .to(".class3", { rotation: -180 });
```

--------------------------------

### GSAP v3: Sequence Animations with keyframes

Source: https://gsap.com/docs/v3/GSAP/Tween/vars

The `keyframes` property enables sequencing multiple animation states within a single tween. It accepts an array of vars objects, each representing a `to()` tween. Keyframes are played back-to-back, but a `delay` can be used to add spacing or create overlaps. This property is exclusively for `to()` tweens.

```javascript
gsap.to("#myElement", {
  keyframes: [
    {x: 100, duration: 1},
    {y: 100, duration: 0.5, delay: -0.2},
    {opacity: 0, duration: 0.7}
  ]
});
```

--------------------------------

### Add Animation to Timeline (Percentage Offset from Previous Animation)

Source: https://gsap.com/docs/v3/GSAP/Timeline/add%28%29

Adds an animation to a GSAP timeline with a percentage offset relative to the previous animation. Percentages following '<' or '>' are based on the previous animation's duration.

```javascript
tl.add(animation, "<25%");
tl.add(animation, "<+=25%");
```

--------------------------------

### Register SplitText Plugin

Source: https://gsap.com/docs/v3/Plugins/SplitText

Registers the SplitText plugin with GSAP. This is a prerequisite for using any SplitText functionality. It requires the GSAP library to be loaded.

```javascript
gsap.registerPlugin(SplitText)
```

--------------------------------

### Register GSAP DrawSVGPlugin

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

This code snippet shows how to register the DrawSVGPlugin with GSAP. This is a prerequisite for using any of its features. It requires the GSAP library to be loaded.

```javascript
gsap.registerPlugin(DrawSVGPlugin)
```

--------------------------------

### Configure Draggable with Force3D Enabled

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet shows how to enable 'force3D' for a Draggable element. By default, GSAP uses 3D transforms to optimize rendering by forcing the element onto its own GPU layer, which usually improves performance.

```javascript
Draggable.create(element, {
  force3D: true
});
```

--------------------------------

### Generate Random Numbers or Pick Array Elements with random() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The random() method generates a random number within a specified range or randomly picks an element from a supplied array. It's a versatile tool for introducing variability into animations or data. This method is part of GSAP's utility methods.

```javascript
gsap.utils.random(0, 100, 5)
// Example output: 65
gsap.utils.random(["red", "green", "blue"])
// Example output: "red"
```

--------------------------------

### Link Animation to Scrollbar with Scrub

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

The `scrub` property links an animation's progress directly to the scrollbar's position. It can be a boolean for direct linking or a number representing the time (in seconds) for the animation playhead to catch up, providing smoothing.

```javascript
gsap.to("#element", {
  x: 500,
  scrollTrigger: {
    trigger: "#element",
    scrub: true // Directly links animation to scrollbar
  }
});

gsap.to("#element", {
  x: 500,
  scrollTrigger: {
    trigger: "#element",
    scrub: 0.5 // Animation playhead takes 0.5s to catch up
  }
});
```

--------------------------------

### Implement onAutoKill Callback

Source: https://gsap.com/docs/v3/Plugins/ScrollToPlugin

Defines a callback function that executes when the `autoKill` feature of the ScrollToPlugin is triggered. This allows for custom actions, such as displaying a notification or logging an event, when the tween is interrupted by user scrolling.

```javascript
gsap.to(window, {
  duration: 2,
  scrollTo: { y: 300, autoKill: true, onAutoKill: myAutoKillFunction },
});

function myAutoKillFunction() {
  alert("autoKill");
}
```

--------------------------------

### Position Animations in GSAP Timeline (Relative Time)

Source: https://gsap.com/docs/v3/GSAP/Timeline

Demonstrates positioning animations relative to the end of the timeline using `+=` for gaps and `-=` for overlaps.

```javascript
tl.to(".class", { x: 100 }, "+=1");
tl.to(".class", { y: 100 }, "-=1");
```

--------------------------------

### Format Number with Commas and Decimals (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/formatNumber

Formats a number by adding thousand separators and optionally limiting the number of decimal places. It takes a numerical value and the desired number of decimals as input, returning a formatted string. This is useful for displaying animated numbers in a user-friendly format.

```javascript
function formatNumber(value, decimals) {
  let s = (+value).toLocaleString("en-US").split(".");
  return decimals
    ? s[0] + "." + ((s[1] || "") + "00000000").substr(0, decimals)
    : s[0];
}
```

--------------------------------

### Parent Timeline Concept

Source: https://gsap.com/docs/v3/GSAP/Timeline/parent

This section explains the concept of a parent timeline in GSAP v3. Animations not explicitly placed in a created timeline are added to the global timeline by default. Each animation can only have one parent timeline.

```APIDOC
## Parent Timeline Concept

### Description

This section explains the concept of a parent timeline in GSAP v3. Animations not explicitly placed in a created timeline are added to the global timeline by default. Each animation can only have one parent timeline.

### Method

N/A (Conceptual Explanation)

### Endpoint

N/A

### Parameters

N/A

### Request Example

N/A

### Response

N/A

### Related Topics

- [Timeline](/docs/v3/GSAP/Timeline.md)
- [gsap.globalTimeline](/docs/v3/GSAP/gsap.globalTimeline.md)
- [Tween](/docs/v3/GSAP/Tween.md)
- [Timeline.add()](/docs/v3/GSAP/Timeline/add().md)

### Notes

- If an animation is added to a different timeline, its `parent` property will be updated accordingly.
- Understanding the mechanics of timelines is crucial for effective use. Refer to the [Timeline docs for details](/docs/v3/GSAP/Timeline.md#mechanics).
```

--------------------------------

### Clearing GSAP Transform Cache

Source: https://gsap.com/docs/v3/Plugins/Flip

Shows how to use `gsap.set()` with `clearProps: "transform"` to clear GSAP's internal transform cache for an element. This is generally not needed if all transform changes are made via GSAP.

```javascript
const element = document.getElementById("myElement");
gsap.set(element, { clearProps: "transform" });
```

--------------------------------

### ScrollTrigger.matchMedia (Deprecated)

Source: https://gsap.com/docs/v3/Plugins/ScrollTrigger

Allows setting up ScrollTriggers that apply only to specific viewport sizes (using media queries). This method is deprecated.

```APIDOC
## ScrollTrigger.matchMedia (Deprecated)

### Description
[DEPRECATED] Allows you to set up ScrollTriggers that only apply to certain viewport sizes (using media queries).

### Method
`static`

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
- **vars** (Object) - An object containing media query conditions and their associated ScrollTrigger configurations.

### Request Example
```javascript
ScrollTrigger.matchMedia({
  '(min-width: 1024px)': function() {
    // ScrollTrigger configurations for large screens
  },
  '(max-width: 768px)': function() {
    // ScrollTrigger configurations for small screens
  }
});
```

### Response
#### Success Response
This method does not return a value.

#### Response Example
None
```

--------------------------------

### Complex Relative Positioning in GSAP v3 Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

Uses prefixes like '+=' and '-=' for relative positioning, allowing insertions before or after specific points (end of timeline, labels, previous animation start/end) by a fixed duration or percentage.

```javascript
// 1 second past the end of the timeline
tl.call(myFunction, null, "+=1");

// 1 second before the end of the timeline
tl.call(myFunction, null, "-=1");

// 2 seconds past the "myLabel" label
tl.call(myFunction, null, "myLabel+=2");

// 3 seconds past the start of the previous animation
tl.call(myFunction, null, "<+=3");

// 0.5 seconds before the end of the previous animation
tl.call(myFunction, null, ">-0.5");

// Overlap with the end of the timeline by 25% of the inserting animation's duration
tl.call(myFunction, null, "-=25%");

// 25% into the previous animation (from its start)
tl.call(myFunction, null, "<25%");

// 30% of the inserting animation's duration past the label "myLabel"
tl.call(myFunction, null, "myLabel+=30%");
```

--------------------------------

### Kill Specific Properties - JavaScript

Source: https://gsap.com/docs/v3/GSAP/Tween/kill%28%29

This snippet illustrates how to kill only specific animated properties of an animation, leaving other properties and targets unaffected. The properties are provided as a comma-delimited string.

```javascript
// kill only the "x" and "y" properties of the animation (all targets):
animation.kill(null, "x,y");
```

--------------------------------

### Animate from Previous State with Flip.from() - JavaScript

Source: https://gsap.com/docs/v3/Plugins/Flip/static

Animates target elements from a previously captured state (provided by Flip.getState()) to their current visual state. It immediately positions/resizes elements to match the 'state' object and then animates the removal of these offsets. Accepts standard GSAP tween properties like duration, ease, and callbacks. Returns a GSAP Timeline object.

```javascript
Flip.from(state, {
  duration: 1,
  ease: "power1.inOut",
  absolute: true,
  onComplete: myFunc
});
```

--------------------------------

### Label Positioning in GSAP Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/to%28%29

Positions an animation at a named label within the timeline. If the label does not exist, it is automatically added to the end of the timeline.

```javascript
tl.to(".class", { x: 100 }, "someLabel");
```

--------------------------------

### Combine GSAP Utility Functions with pipe()

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/random%28%29

The pipe() method allows chaining multiple GSAP utility functions to process a single value sequentially. This is useful for complex data transformations like clamping, normalizing, and interpolating. It takes reusable functions as arguments and returns a new function that applies them in order.

```javascript
var colorizer = gsap.utils.pipe(
  gsap.utils.clamp(0, 100),
  gsap.utils.normalize(0, 100),
  gsap.utils.interpolate("red", "blue")
);

colorizer(25.874);
```

--------------------------------

### Minimal DrawSVG Animation

Source: https://gsap.com/docs/v3/Plugins/DrawSVGPlugin

Demonstrates the basic usage of DrawSVGPlugin to animate the drawing of SVG elements with the class 'draw-me'. It animates the `drawSVG` property from 0 to its default value over 1 second.

```javascript
//draws all elements with the "draw-me" class applied
gsap.from('.draw-me', { duration: 1, drawSVG: 0 });
```

--------------------------------

### seek()

Source: https://gsap.com/docs/v3/GSAP/Tween

Jumps to a specific time without affecting whether the instance is paused or reversed. This allows for precise control over the animation's playhead.

```APIDOC
## POST /docs/v3/GSAP/Tween/seek().md

### Description
Jumps to a specific time.

### Method
POST

### Endpoint
/docs/v3/GSAP/Tween/seek().md

### Parameters
#### Path Parameters
- **time** (*) - Required - The time to seek to.
- **suppressEvents** (Boolean) - Optional - Whether to suppress events.

### Request Body
N/A

### Request Example
N/A

### Response
#### Success Response (200)
- **self** (self) - Returns self.

#### Response Example
N/A
```

--------------------------------

### MotionPathPlugin.arrayToRawPath

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Converts an array of coordinates into a RawPath Array, optionally interpreting them as cubic bezier points.

```APIDOC
## MotionPathPlugin.arrayToRawPath

### Description
Takes an Array of coordinates and plots a curve through them, returning a corresponding RawPath Array. If `type: "cubic"` is declared in the `vars` parameter object, they will be interpreted as cubic bezier points like anchor, two control points, anchor, two control points, anchor, etc.)

### Method
STATIC

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
*   **values** (Array) - An array of coordinates.
*   **vars** (Object) - An object containing configuration options, such as `type: "cubic"`.

### Request Example
```json
{
  "values": [[0, 0], [100, 100], [200, 0]],
  "vars": {"type": "linear"}
}
```

### Response
#### Success Response (200)
*   **RawPath Array** (Array) - A RawPath Array representing the plotted curve.

#### Response Example
```json
[[0, 0, 0, 0, 100, 100, 100, 100, 200, 0, 200, 0]]
```
```

--------------------------------

### MotionPathPlugin.getGlobalMatrix

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

Retrieves the Matrix2D for converting an element's local coordinates to global viewport coordinates.

```APIDOC
## MotionPathPlugin.getGlobalMatrix

### Description
Gets the Matrix2D that would be used to convert the element's local coordinate space into the global coordinate space. So, for example, if you take a point `{x:0, y:0}` and `apply()` the matrix to it, the resulting point would be the viewport coordinates of that element's top left corner.

### Method
STATIC

### Endpoint
N/A (Static method)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
*   **element** (Element) - The element for which to get the global matrix.
*   **inverse** (Boolean) - If true, returns the inverse matrix.
*   **adjustGOffset** (Boolean) - If true, adjusts for the "graphics offset" (typically for SVG).

### Request Example
```json
{
  "element": document.getElementById('myElement'),
  "inverse": false,
  "adjustGOffset": true
}
```

### Response
#### Success Response (200)
*   **Matrix2D** (Object) - A Matrix2D object with an `apply()` method for coordinate conversion.

#### Response Example
```json
{
  "a": 1, "b": 0, "c": 0, "d": 1, "e": 5, "f": 15,
  "apply": function(point) { /* ... */ }
}
```
```

--------------------------------

### Import GSAP v3 in JavaScript

Source: https://gsap.com/docs/v3/GSAP

Imports the GSAP core functionality into your JavaScript project. This allows you to use GSAP's animation methods.

```javascript
import { gsap } from "gsap"

```

--------------------------------

### minRotation Property

Source: https://gsap.com/docs/v3/Plugins/Draggable/minRotation

Details on the minRotation property for GSAP v3 rotation tweens.

```APIDOC
## minRotation Property

### Description

When bounds are applied to a rotation tween, `minRotation` defines the minimum "legal" rotation value. This property is useful for implementing custom logic within `snap`, `liveSnap`, or callback functions.

### Method

N/A (This is a configuration property, not an endpoint)

### Endpoint

N/A

### Parameters

#### Path Parameters

N/A

#### Query Parameters

N/A

#### Request Body

- **minRotation** (Number) - Required - Specifies the minimum rotation value when bounds are active. Only applies to tweens of `type: "rotation"`.

### Request Example

```json
{
  "minRotation": -90
}
```

### Response

#### Success Response (200)

N/A (This is a configuration property)

#### Response Example

N/A
```

--------------------------------

### Observer disable()

Source: https://gsap.com/docs/v3/Plugins/Observer/disable%28%29

Disables the Observer, removing event listeners and firing the onDisable callback. Use kill() for permanent disabling.

```APIDOC
## disable()

### Description
Disables the Observer, removing the necessary event listeners and firing the `onDisable` callback if the Observer wasn't already disabled.

### Method
`disable()`

### Endpoint
N/A (This is a method call within the GSAP Observer plugin)

### Parameters
None

### Request Example
```javascript
// Assuming 'observer' is an instance of Observer
observer.disable();
```

### Response
#### Return Value
`void` - This method does not return a value.

#### Success Response (onDisable callback)
If the Observer was not already disabled, the `onDisable` callback function (if defined) will be executed.

#### Response Example
```javascript
// Example of onDisable callback
const observer = new Observer(element, {
  onDisable: () => {
    console.log('Observer has been disabled.');
  }
});

observer.disable();
```
```

--------------------------------

### GSAP Draggable: Controlling Context Menu and Event Defaults

Source: https://gsap.com/docs/v3/Plugins/Draggable

Configures whether Draggable should allow native context menus and prevent default event behaviors. `allowContextMenu` enables right-click or long-touch menus, while `allowEventDefault` can permit default actions like touch-scrolling, though typically it's recommended to let Draggable manage event defaults for optimal dragging.

```javascript
Draggable.create("#myElement", {
  allowContextMenu: true,
  allowEventDefault: false
});
```

--------------------------------

### GSAP v3 Timeline Properties

Source: https://gsap.com/docs/v3/GSAP/Timeline

This section outlines the various properties available on a GSAP v3 Timeline object.

```APIDOC
## GSAP v3 Timeline Properties

### Description
This section outlines the various properties available on a GSAP v3 Timeline object.

### Method
N/A (Properties of an object)

### Endpoint
N/A (Properties of an object)

### Parameters
#### Path Parameters
None

#### Query Parameters
None

#### Request Body
None

### Request Example
None

### Response
#### Success Response (200)
This refers to the properties of a GSAP Timeline object.

#### Response Example
```json
{
  "autoRemoveChildren": true, 
  "data": {},
  "labels": {},
  "parent": null, 
  "scrollTrigger": null,
  "smoothChildTiming": true,
  "vars": {}
}
```

## **Properties Details**

### autoRemoveChildren
- **Type**: Boolean
- **Description**: If `true`, child tweens and timelines will be removed as soon as they complete.

### data
- **Type**: *
- **Description**: A place to store any data you want (initially populated with `vars.data` if it exists).

### labels
- **Type**: Object
- **Description**: This stores any labels that have been added to the timeline.

### parent
- **Type**: Timeline
- **Description**: The parent Timeline to which the animation is attached. Anything that's not in a Timeline that you create is placed on the `gsap.globalTimeline` by default.

### scrollTrigger
- **Type**: ScrollTrigger | undefined
- **Description**: A handy way to access the ScrollTrigger associated with a timeline. This is only accessible if the timeline has a ScrollTrigger.

### smoothChildTiming
- **Type**: Boolean
- **Description**: Controls whether or not child tweens and timelines are repositioned automatically (changing their `startTime`) in order to maintain smooth playback when properties are changed on-the-fly.

### vars
- **Type**: Object
- **Description**: The configuration object passed into the original timeline via the constructor, like `gsap.timeline({onComplete: func});`
```

--------------------------------

### Spinnable Element Creation with Inertia (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/Draggable

Makes an element rotatable (spinnable) using the Draggable plugin with inertia enabled. This allows for a spinning effect with momentum-based motion after the drag gesture is released. Requires the Draggable plugin and InertiaPlugin.

```javascript
Draggable.create('#yourID', {
	type: 'rotation',
	inertia: true
});
```

--------------------------------

### Align transformOrigin with MotionPathPlugin (JavaScript)

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/alignOrigins

This function aligns the transformOrigin of 'fromElement' to match 'toElement's transformOrigin without a visual jump. It requires the MotionPathPlugin and uses GSAP utilities to calculate and apply the new origin and adjust element position.

```javascript
function alignOrigins(fromElement, toElement) {
  let [fromEl, toEl] = gsap.utils.toArray([fromElement, toElement]),
    a = window.getComputedStyle(toEl).transformOrigin.split(" "),
    newOrigin = MotionPathPlugin.convertCoordinates(toEl, fromEl, {
      x: parseFloat(a[0]),
      y: parseFloat(a[1]),
    }),
    bounds1 = fromEl.getBoundingClientRect(),
    bounds2;
  gsap.set(fromEl, {
    transformOrigin: newOrigin.x + "px " + newOrigin.y + "px",
  });
  bounds2 = fromEl.getBoundingClientRect();
  gsap.set(fromEl, {
    x: "+=" + (bounds1.left - bounds2.left),
    y: "+=" + (bounds1.top - bounds2.top),
  });
}
```

--------------------------------

### Align Motion Path to Element ('self')

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This snippet demonstrates using the 'self' value for the 'align' property. This effectively moves the motion path to the target element's current position, preventing initial jumps.

```javascript
align: "self"
```

--------------------------------

### Inertia Tween with Auto Velocity (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/static

Creates an inertia tween that automatically uses the velocity tracked by InertiaPlugin. The 'auto' value for a property tells GSAP to find the associated tracker and use its recorded velocity for the tween's end state, resulting in a natural glide to a stop.

```javascript
//first, start tracking "x" and "y":
InertiaPlugin.track(obj, "x,y");

//then, after at least 100ms, let's smoothly tween to EXACTLY x:200, y:300
gsap.to(obj, {
  inertia: {
    x: { end: 200 },
    y: { end: 300 },
  },
});

//and if you want things to use the defaults and have obj.x and obj.y glide to a stop based on the velocity rather than setting any destination values, just use "auto":
gsap.to(obj, {
  inertia: {
    x: "auto",
    y: "auto",
  },
});
```

--------------------------------

### Convert and Animate backgroundSize to Pixels with GSAP

Source: https://gsap.com/docs/v3/HelperFunctions/helpers/bgSize

This JavaScript function, `bgSize`, converts 'cover', 'contain', or percentage-based `backgroundSize` values into their pixel equivalents for a given element. It can optionally set the `backgroundSize` and is useful for GSAP animations where numerical interpolation is required. It handles image loading to determine native dimensions if not provided.

```javascript
/*
config is optional and can have any of the following properties:
- size [string] - the size to set and convert into px before it gets returned, like "cover" or "150% auto".
- nativeWidth [number] - native width of the image (in pixels)
- nativeHeight [number] - native height of the image (in pixels)

Simple example:
// returns current backgroundSize in px
bgSize(".class");

Advanced example:
// sets the backgroundSize to "cover" and returns it in the equivalent px-based amount assuming the image's native width is 600px and height is 400px.
bgSize(".class", {size: "cover", nativeWidth: 600, nativeHeight: 400});

Note: if you can define the nativeWidth and nativeHeight, it helps becaues it can skip tasks like creating
an Image and loading the URL to detect the native size automatically. Sometimes images don't load fast enough,
so skipping that step avoids the whole issue.
*/
function bgSize(element, config) {
  config = config || {};
  let e = gsap.utils.toArray(element)[0],
    cs = window.getComputedStyle(e),
    imageUrl = cs.backgroundImage,
    { nativeWidth, nativeHeight } = config,
    size = config.size || cs.backgroundSize,
    image,
    w,
    h,
    ew,
    eh,
    ratio;
  if (imageUrl && (!/\d/g.test(size) || size.indexOf("%") > -1)) {
    if (!nativeWidth || !nativeHeight) {
      image = new Image();
      image.setAttribute(
        "src",
        imageUrl.replace(/(^url\(\"|^url\('\|^url\(|\"\)$|\'\)$|\)$)/gi, "")
      );
      nativeWidth = image.naturalWidth;
      nativeHeight = image.naturalHeight;
    }
    ew = e.offsetWidth;
    eh = e.offsetHeight;
    if (!nativeWidth || !nativeHeight) {
      console.log("bgSize() failed;", imageUrl, "hasn't loaded yet.");
      nativeWidth = ew;
      nativeHeight = eh;
    }
    ratio = nativeWidth / nativeHeight;
    if (size === "cover" || size === "contain") {
      if ((size === "cover") === nativeWidth / ew > nativeHeight / eh) {
        h = eh;
        w = eh * ratio;
      } else {
        w = ew;
        h = ew / ratio;
      }
    } else {
      // "auto" or %
      size = size.split(" ");
      size.push("");
      w = ~size[0].indexOf("%")
        ? (ew * parseFloat(size[0])) / 100
        : nativeWidth;
      h = ~size[1].indexOf("%")
        ? (eh * parseFloat(size[1])) / 100
        : nativeHeight;
    }
    size = Math.ceil(w) + "px " + Math.ceil(h) + "px";
    config.size && (e.style.backgroundSize = size);
  }
  return size;
}
```

--------------------------------

### Configure Draggable with Force3D Disabled

Source: https://gsap.com/docs/v3/Plugins/Draggable

This snippet demonstrates disabling 'force3D' for a Draggable element. Disabling this can be beneficial if the element contains child elements that are animating, as it prevents potential conflicts with GPU layer compositing.

```javascript
Draggable.create(element, {
  force3D: false
});
```

--------------------------------

### Create Scoped Selectors with selector() - JavaScript

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The selector() method returns a selector function that is scoped to a particular Element, React ref, or Angular ElementRef. This is useful for targeting elements within a specific container, preventing unintended selections. This method is part of GSAP's utility methods.

```javascript
const selector = gsap.utils.selector(myElement);
const childElements = selector(".child-class");
```

--------------------------------

### Map Value Immediately with GSAP mapRange

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/mapRange%28%29

This method directly maps a given value from an input range (inMin, inMax) to an output range (outMin, outMax). It's useful for one-off calculations where you need the mapped value immediately. No external dependencies are required beyond the GSAP library.

```javascript
gsap.utils.mapRange(-10, 10, 100, 200, 0); // Returns 150
gsap.utils.mapRange(0, 100, 0, 500, 50); // Returns 250
```

--------------------------------

### isTracking Method

Source: https://gsap.com/docs/v3/Plugins/InertiaPlugin/VelocityTracker/.isTracking%28%29

The isTracking method returns a boolean value indicating whether the velocity of a specified target is currently being tracked by GSAP. This is typically used in conjunction with the VelocityTracker.track() method.

```APIDOC
## isTracking

### Description
Returns `true` if the target is being tracked, `false` if not.

### Method
GET

### Endpoint
/websites/gsap_v3/isTracking

### Parameters
#### Query Parameters
- **target** (Object) - Required - The GSAP target whose tracking status needs to be checked.

### Request Example
```json
{
  "target": "#myElement"
}
```

### Response
#### Success Response (200)
- **isTracking** (Boolean) - `true` if the target is being tracked, `false` otherwise.

#### Response Example
```json
{
  "isTracking": true
}
```
```

--------------------------------

### Wrap Number Range with Yoyo Effect (JavaScript)

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/wrapYoyo%28%29

This snippet shows how to use GSAP's wrapYoyo utility to wrap a number within a specified minimum and maximum range, creating a yoyo effect. When the number exceeds the maximum, it yoyos back towards the minimum, and when it's less than the minimum, it yoyos forward to the maximum.

```javascript
let num = gsap.utils.wrapYoyo(5, 10, 12); // 8
```

--------------------------------

### Add Animation to Timeline (Percentage Offset from Timeline End)

Source: https://gsap.com/docs/v3/GSAP/Timeline/add%28%29

Adds an animation to a GSAP timeline with a percentage offset relative to the end of the timeline. This percentage is based on the total duration of the animation being inserted.

```javascript
tl.add(animation, "-=25%");
tl.add(animation, "+=50%");
```

--------------------------------

### Define Motion Path using SVG Path Data String

Source: https://gsap.com/docs/v3/Plugins/MotionPathPlugin

This snippet illustrates how to define the motion path directly using an SVG path data string. This is useful for creating paths programmatically or when the path is not represented by an SVG element in the DOM.

```javascript
motionPath: {
  path: "M9,100c0,0,18-41,49-65"
}
```

--------------------------------

### onPress Callback Function - GSAP Draggable

Source: https://gsap.com/docs/v3/Plugins/Draggable

The onPress function is executed as soon as the mouse or touch press occurs on the target element. 'this' refers to the Draggable instance, allowing access to properties like 'target', 'maxX', 'minX', 'maxY', and 'minY'. The pointerEvent is passed as a parameter.

```javascript
onPress: function(pointerEvent) {
  // 'this' refers to the Draggable instance
  console.log("Mouse/Touch pressed down.");
  console.log("Target element: " + this.target);
  // Access pointerEvent properties like pageX, pageY, target, etc.
}
```

--------------------------------

### Setting Default Render Function for MorphSVGPlugin (JavaScript)

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

This code demonstrates how to set a global default render function for all MorphSVG animations using 'MorphSVGPlugin.defaultRender'. This is particularly useful for consistent canvas rendering across multiple tweens without needing to specify the render function in each individual tween.

```javascript
MorphSVGPlugin.defaultRender = yourFunction;
```

--------------------------------

### Scoped Selector with React Ref

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods/selector%28%29

Illustrates using GSAP's selector utility within a React component. A ref is created for the component's root element, and the selector function is then used to target descendant elements for GSAP animations, ensuring animations are confined to the component.

```javascript
let el = useRef();
let q = gsap.utils.selector(el);

useEffect(() => {
  // uses el.current.querySelectorAll() internally
  gsap.to(q(".box"), { x: 100 });
}, []);
```

--------------------------------

### Label Positioning in GSAP v3 Timeline

Source: https://gsap.com/docs/v3/GSAP/Timeline/call%28%29

Inserts a function call at a named label within the timeline. If the label does not exist, it is automatically created at the end of the timeline.

```javascript
tl.call(myFunction, null, "someLabel");
```

--------------------------------

### GSAP Utility: getUnit

Source: https://gsap.com/docs/v3/GSAP/UtilityMethods

The `getUnit` utility method extracts the unit from a string value, such as 'px', '%', or 'em'. It's helpful when you need to parse CSS values and work with their numerical and unit components separately. It returns the unit as a string.

```javascript
gsap.utils.getUnit("30px");  // Returns "px"
gsap.utils.getUnit("10em");   // Returns "em"
gsap.utils.getUnit("50");     // Returns ""
```

--------------------------------

### Convert SVG Shapes to Paths with MorphSVGPlugin

Source: https://gsap.com/docs/v3/Plugins/MorphSVGPlugin

Explains how to use the MorphSVGPlugin.convertToPath() utility to convert SVG elements like circles, rectangles, ellipses, and lines into path elements, which are necessary for morphing.

```javascript
MorphSVGPlugin.convertToPath("#elementID");
```

```javascript
MorphSVGPlugin.convertToPath("circle, rect, ellipse, line, polygon, polyline");
```

--------------------------------

### GSAP v3: Applying Easing Functions

Source: https://gsap.com/docs/v3/GSAP/Tween

The 'ease' property controls the rate of change during an animation, providing a specific feel. It can be a string (e.g., 'elastic', 'strong.inOut') or a function. The default is 'power1.out'.

```javascript
gsap.to(".myElement", {
  x: 100,
  ease: "elastic.out(1, 0.3)" // Applying an elastic ease
});

// Example with a custom ease function
const customEase = (progress) => Math.sin(progress * Math.PI);
gsap.to(".myElement", {
  x: 100,
  ease: customEase
});
```