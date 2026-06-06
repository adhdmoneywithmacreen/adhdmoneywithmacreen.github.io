```html
<!-- =========================================
90 DAYS ADHD DIGITAL DAILY PLANNER
STACK:
HTML + CSS + JAVASCRIPT
READY FOR GITHUB + VERCEL + NETLIFY

FOLDER STRUCTURE:

/adhd-planner
    index.html
    style.css
    app.js
    /assets
        logo.jpg
        background.jpg

PUT:
FIRST IMAGE = logo.jpg
SECOND IMAGE = background.jpg
========================================= -->

<!-- =========================
index.html
========================= -->

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>90 Days ADHD Planner</title>

  <link rel="stylesheet" href="style.css"/>

  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>

<body>

  <div class="overlay"></div>

  <!-- HERO -->
  <section class="hero">

    <div class="hero-content">

      <img src="assets/logo.jpg" class="hero-logo"/>

      <h1 class="animated-text">
        <span>DISCIPLINE TODAY.</span>
        <span>FREEDOM TOMORROW.</span>
      </h1>

      <button class="start-btn">
        START YOUR JOURNEY
      </button>

    </div>

  </section>

  <!-- MAIN APP -->
  <main class="dashboard">

    <!-- LEFT -->
    <section class="left-panel">

      <!-- GOOGLE CALENDAR -->
      <div class="card calendar-card">

        <h2>Calendar</h2>

        <iframe
          src="https://calendar.google.com/calendar/embed?src=en.kenyan%23holiday%40group.v.calendar.google.com"
          style="border:0"
          width="100%"
          height="400"
          frameborder="0"
          scrolling="no">
        </iframe>

      </div>

      <!-- COUNTDOWN -->
      <div class="card countdown-card">

        <h2>90 Day Countdown</h2>

        <div id="countdown">
          Day 1 of 90
        </div>

      </div>

      <!-- PURPOSE MAP -->
      <div class="card circles-card">

        <div class="circle c1">
          WHAT I CARE ABOUT
        </div>

        <div class="circle c2">
          WHAT I'M GOOD AT
        </div>

        <div class="circle c3">
          SOMETHING CHALLENGING
        </div>

        <div class="circle c4">
          LONG TERM
        </div>

      </div>

      <!-- HABITS -->
      <div class="habit-section">

        <div class="card">

          <h2>Daily Non Negotiables</h2>

          <label><input type="checkbox"/> Medication</label>
          <label><input type="checkbox"/> Deep Work</label>
          <label><input type="checkbox"/> Water</label>
          <label><input type="checkbox"/> Exercise</label>
          <label><input type="checkbox"/> Sleep</label>

        </div>

        <div class="card">

          <h2>Other Habits</h2>

          <textarea placeholder="Add habits..."></textarea>

        </div>

      </div>

      <!-- HABIT TRACKER -->
      <div class="card">

        <h2>90 Days Habit Tracker</h2>

        <canvas id="habitChart"></canvas>

      </div>

      <!-- SUNFLOWER GAME -->
      <div class="card sunflower-card">

        <h2>Sunflower Growth</h2>

        <div class="sunflowers">
          🌱 🌿 🌻 🌻 🌻
        </div>

      </div>

    </section>

    <!-- RIGHT -->
    <section class="right-panel">

      <!-- TOP -->
      <div class="top-info">

        <div class="card">
          <h3>Date</h3>
          <p id="todayDate"></p>
        </div>

        <div class="card">
          <h3>Mood</h3>

          <select id="mood">
            <option>Focused</option>
            <option>Low Dopamine</option>
            <option>Overwhelmed</option>
            <option>Hyperfocused</option>
          </select>

        </div>

        <div class="card">
          <h3>Medication Peak</h3>

          <input type="time"/>

        </div>

      </div>

      <!-- ADHD TASK CIRCLE -->
      <div class="card task-circle-card">

        <div class="task-circle">

          <div class="quarter q1">
            Today's Tasks
          </div>

          <div class="quarter q2">
            Organize
          </div>

          <div class="quarter q3">
            Distill
          </div>

          <div class="quarter q4">
            Deadlines
          </div>

        </div>

      </div>

      <!-- 333 -->
      <div class="task-grid">

        <div class="card">

          <h2>3/3/3 Method</h2>

          <ul>
            <li>3 Hr Important</li>
            <li>3 Small Urgent</li>
            <li>3 Maintenance</li>
          </ul>

        </div>

        <div class="card">

          <h2>Artificial Deadlines</h2>

          <textarea></textarea>

        </div>

        <div class="card frog-card">

          <h2>Eat The Frog</h2>

          <div class="frog">
            🐸
          </div>

          <div class="progress">

            <div class="bar"></div>

          </div>

        </div>

      </div>

      <!-- SELF CARE -->
      <div class="selfcare-grid">

        <div class="card">

          <h2>Daily Self Care</h2>

          <label><input type="checkbox"/> Shower</label>
          <label><input type="checkbox"/> Stretch</label>
          <label><input type="checkbox"/> Walk</label>
          <label><input type="checkbox"/> Journal</label>

          <div class="progress">
            <div class="bar"></div>
          </div>

        </div>

        <div class="card">

          <h2>Meals</h2>

          <label><input type="checkbox"/> Breakfast</label>
          <label><input type="checkbox"/> Lunch</label>
          <label><input type="checkbox"/> Dinner</label>

        </div>

        <div class="card">

          <h2>Medication Tracker</h2>

          <canvas id="medChart"></canvas>

        </div>

      </div>

      <!-- FOREST GAME -->
      <div class="card forest-card">

        <h2>Forest Growth</h2>

        <div class="forest">
          🌲 🌳 🌲 🦌
        </div>

      </div>

      <!-- BRAIN DUMP -->
      <div class="card">

        <h2>Brain Dump</h2>

        <textarea placeholder="Write anything..."></textarea>

      </div>

    </section>

  </main>

  <script src="app.js"></script>

</body>
</html>
```

---

```css
/* =========================
style.css
========================= */

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:sans-serif;
}

body{
  background:url("assets/background.jpg");
  background-size:cover;
  background-position:center;
  color:#222;
}

.overlay{
  position:fixed;
  inset:0;
  background:rgba(255,255,255,0.65);
  backdrop-filter:blur(5px);
  z-index:-1;
}

.hero{
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
}

.hero-content{
  background:rgba(255,255,255,0.2);
  backdrop-filter:blur(15px);
  padding:40px;
  border-radius:30px;
}

.hero-logo{
  width:250px;
  border-radius:20px;
}

.animated-text{
  margin-top:30px;
  font-size:3rem;
  color:#fff;
}

.animated-text span{
  display:block;
  animation:fadeText 6s infinite;
}

.animated-text span:last-child{
  animation-delay:3s;
}

@keyframes fadeText{
  0%{opacity:0;}
  20%{opacity:1;}
  50%{opacity:1;}
  100%{opacity:0;}
}

.start-btn{
  margin-top:30px;
  padding:15px 40px;
  border:none;
  border-radius:40px;
  background:#b7c96b;
  cursor:pointer;
  font-size:1rem;
}

.dashboard{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:20px;
  padding:30px;
}

.card{
  background:rgba(255,255,255,0.55);
  backdrop-filter:blur(10px);
  border-radius:20px;
  padding:20px;
  margin-bottom:20px;
}

.top-info{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:15px;
}

.habit-section{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:20px;
}

.circles-card{
  position:relative;
  height:450px;
}

.circle{
  width:220px;
  height:220px;
  border-radius:50%;
  position:absolute;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:20px;
  font-weight:bold;
}

.c1{
  background:#bedadc;
  top:0;
  left:80px;
}

.c2{
  background:#d8b48c;
  top:0;
  right:50px;
}

.c3{
  background:#89a6a8;
  bottom:20px;
  left:0;
}

.c4{
  background:#b7c96b;
  bottom:20px;
  right:0;
}

.task-circle{
  width:450px;
  height:450px;
  border-radius:50%;
  overflow:hidden;
  margin:auto;
  position:relative;
}

.quarter{
  width:50%;
  height:50%;
  position:absolute;
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
}

.q1{
  top:0;
  left:0;
  background:#bedadc;
}

.q2{
  top:0;
  right:0;
  background:#dfe9c5;
}

.q3{
  bottom:0;
  left:0;
  background:#89a6a8;
}

.q4{
  bottom:0;
  right:0;
  background:#b7c96b;
}

.task-grid,
.selfcare-grid{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:20px;
}

.progress{
  height:12px;
  background:#ddd;
  border-radius:20px;
  overflow:hidden;
  margin-top:15px;
}

.bar{
  width:60%;
  height:100%;
  background:#b7c96b;
}

.sunflowers,
.forest,
.frog{
  font-size:3rem;
  text-align:center;
  margin-top:20px;
}

textarea{
  width:100%;
  min-height:120px;
  border:none;
  padding:15px;
  border-radius:15px;
  margin-top:10px;
}

label{
  display:block;
  margin-top:12px;
}

@media(max-width:1200px){

  .dashboard{
    grid-template-columns:1fr;
  }

  .task-grid,
  .selfcare-grid,
  .habit-section,
  .top-info{
    grid-template-columns:1fr;
  }

  .task-circle{
    width:320px;
    height:320px;
  }

}
```

---

```javascript
// =========================
// app.js
// =========================

// DATE
const today = new Date();

document.getElementById("todayDate").innerHTML =
today.toDateString();

// COUNTDOWN
let currentDay = 1;

const countdown =
document.getElementById("countdown");

setInterval(()=>{

  if(currentDay < 90){
    currentDay++;
  }

  countdown.innerHTML =
  `Day ${currentDay} of 90`;

}, 86400000);

// HABIT CHART
const ctx =
document.getElementById('habitChart');

new Chart(ctx, {

  type:'line',

  data:{

    labels:[
      'Week1',
      'Week2',
      'Week3',
      'Week4',
      'Week5',
      'Week6',
      'Week7',
      'Week8',
      'Week9',
      'Week10',
      'Week11',
      'Week12'
    ],

    datasets:[{

      label:'Habits',

      data:[
        20,
        35,
        40,
        55,
        60,
        68,
        72,
        78,
        81,
        88,
        91,
        97
      ],

      borderColor:'#89a6a8',
      backgroundColor:'#bedadc',
      tension:0.4

    }]

  }

});

// MEDICATION CHART
const medCtx =
document.getElementById('medChart');

new Chart(medCtx, {

  type:'line',

  data:{

    labels:[
      '8AM',
      '10AM',
      '12PM',
      '2PM',
      '4PM',
      '6PM'
    ],

    datasets:[{

      label:'Medication Peak',

      data:[
        10,
        40,
        90,
        70,
        35,
        10
      ],

      borderColor:'#b7c96b',
      tension:0.4

    }]

  }

});
```

