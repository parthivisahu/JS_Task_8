# JS_Task_8
# JavaScript Train Animation

This JavaScript code enables you to create a simple train animation with start, stop, and reset functionalities. The animation moves a train across the screen using CSS transformations and JavaScript timers.

## Usage

1. Include the JavaScript code in your HTML document or JavaScript file:

   ```html
   <div id="train"></div>

   <button onclick="startTrain()">Start</button>
   <button onclick="stopTrain()">Stop</button>
   <button onclick="resetTrain()">Reset</button>

   <script src="train-animation.js"></script>
   ```

2. Define the CSS styles for the train and the animation in your CSS file or the `<style>` section of your HTML:

   ```css
   #train {
     width: 100px;
     height: 50px;
     background-color: red;
     position: relative;
     left: 0;
     transition: left 2s linear;
   }
   ```

3. Include the JavaScript code for the animation:

   ```javascript
   let trainIntervalId;
   const train = document.getElementById('train');

   function startTrain() {
     trainIntervalId = setInterval(moveTrain, 2000);
   }

   function stopTrain() {
     clearInterval(trainIntervalId);
   }

   function resetTrain() {
     stopTrain();
     train.style.left = '0';
   }

   function moveTrain() {
     const currentPosition = parseFloat(train.style.left) || 0;
     train.style.left = `${currentPosition + 100}px`;
   }
   ```

4. Customize the animation styles, interval duration, and train movement according to your preferences.

   - In the `startTrain` function, you can modify the interval duration (`2000` in the example) to control the speed of the animation.
   - In the `moveTrain` function, adjust the distance the train moves (`100` in the example) to change the train's displacement in each animation step.
   - You can also customize the train's appearance by modifying the CSS styles for `#train`.

5. Test the animation by clicking the "Start," "Stop," and "Reset" buttons on the webpage. The train will start moving to the right at the specified interval when you click "Start." Use "Stop" to pause the train's movement, and "Reset" to bring the train back to its initial position.

## Example

HTML:

```html
<div id="train"></div>

<button onclick="startTrain()">Start</button>
<button onclick="stopTrain()">Stop</button>
<button onclick="resetTrain()">Reset</button>

<script src="train-animation.js"></script>
```

CSS:

```css
#train {
  width: 100px;
  height: 50px;
  background-color: red;
  position: relative;
  left: 0;
  transition: left 2s linear;
}
```

JavaScript (train-animation.js):

```javascript
let trainIntervalId;
const train = document.getElementById('train');

function startTrain() {
  trainIntervalId = setInterval(moveTrain, 2000);
}

function stopTrain() {
  clearInterval(trainIntervalId);
}

function resetTrain() {
  stopTrain();
  train.style.left = '0';
}

function moveTrain() {
  const currentPosition = parseFloat(train.style.left) || 0;
  train.style.left = `${currentPosition + 100}px`;
}
```

In this example, a train is represented by a `div` element with the id "train". The animation moves the train from left to right by updating its `left` CSS property in each animation step.

When you click the "Start" button, the `startTrain` function is called, which starts the train animation

 by repeatedly invoking the `moveTrain` function with a specified interval (`2000` milliseconds in this case). The `stopTrain` function stops the animation by clearing the interval, and the `resetTrain` function brings the train back to its initial position by setting its `left` style property to `0`.

Customize the CSS styles, animation interval, and train movement to achieve the desired train animation effect.
