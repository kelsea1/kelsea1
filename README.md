- 👋 Hi, I’m @kelsea1
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
kelsea1/kelsea1 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
Alright! Here's an example of a pomodoro timer implemented using HTML, CSS, and JavaScript:

HTML:
```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div class="timer">
    <h1 id="timeLeft">25:00</h1>
    <div class="controls">
      <button id="startBtn" onclick="startTimer()">Start</button>
      <button id="resetBtn" onclick="resetTimer()">Reset</button>
    </div>
  </div>
  
  <script src="script.js"></script>
</body>
</html>
```

CSS (styles.css):
```css
.timer {
  text-align: center;
  margin-top: 100px;
}

h1 {
  font-size: 60px;
}

.controls {
  margin-top: 20px;
}

button {
  font-size: 20px;
  padding: 10px 20px;
  margin: 5px;
}
```

JavaScript (script.js):
```javascript
var timeLeft = 25 * 60; // 25 minutes in seconds
var timer;
var running = false;

function startTimer() {
  if (!running) {
    timer = setInterval(function () {
      var minutes = Math.floor(timeLeft / 60);
      var seconds = timeLeft % 60;

      if (seconds < 10) {
        seconds = "0" + seconds;
      }

      document.getElementById("timeLeft").innerHTML = minutes + ":" + seconds;

      if (timeLeft === 0) {
        clearInterval(timer);
        alert("Time's up! Take a break.");
        running = false;
        document.getElementById("startBtn").innerHTML = "Start";
      }

      timeLeft--;
    }, 1000);

    running = true;
    document.getElementById("startBtn").innerHTML = "Pause";
  } else {
    clearInterval(timer);
    running = false;
    document.getElementById("startBtn").innerHTML = "Resume";
  }
}

function resetTimer() {
  clearInterval(timer);
  running = false;
  timeLeft = 25 * 60;
  document.getElementById("timeLeft").innerHTML = "25:00";
  document.getElementById("startBtn").innerHTML = "Start";
}
```

This implementation will display a pomodoro timer with a starting time of 25 minutes. You can start, pause, resume, and reset the timer using the buttons provided. The timer will visually countdown in minutes and seconds, and when it reaches 0, it will show an alert message.
