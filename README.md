<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#120d19">
<title>How Well Do You Know Bree? ♡</title>

<style>
:root{
  --burgundy:#7d1638;
  --burgundy2:#a52d54;
  --blue:#a9dff2;
  --ink:#0c0912;
  --card:rgba(20,14,28,.88);
  --text:#fff8fc;
  --muted:#cbbdca;
  --gold:#ffd76a;
  --green:#7de2a7;
  --red:#ff7897;
}

*{
  box-sizing:border-box;
}

html,body{
  margin:0;
  min-height:100%;
  font-family:Georgia,"Times New Roman",serif;
  background:#09070d;
  color:var(--text);
}

body{
  overflow-x:hidden;
  background:
    radial-gradient(circle at 15% 15%,rgba(125,22,56,.35),transparent 28%),
    radial-gradient(circle at 85% 20%,rgba(169,223,242,.14),transparent 24%),
    radial-gradient(circle at 50% 90%,rgba(125,22,56,.25),transparent 35%),
    #09070d;
}

body:before,
body:after{
  content:"";
  position:fixed;
  inset:0;
  pointer-events:none;
  z-index:-1;

  background-image:
    radial-gradient(circle,rgba(255,255,255,.8) 0 1px,transparent 1.5px),
    radial-gradient(circle,rgba(169,223,242,.7) 0 1px,transparent 1.5px);

  background-size:97px 97px,151px 151px;
  background-position:10px 30px,55px 90px;
  opacity:.3;
}

body:after{
  animation:drift 20s linear infinite;
  opacity:.16;
}

@keyframes drift{
  to{
    transform:translate3d(40px,70px,0);
  }
}

.wrap{
  width:min(940px,92vw);
  margin:0 auto;
  padding:28px 0 55px;
}

header{
  text-align:center;
  padding:24px 10px 18px;
}

.mini{
  letter-spacing:.22em;
  text-transform:uppercase;
  font-size:.72rem;
  color:var(--blue);
}

h1{
  font-size:clamp(2.1rem,7vw,4.5rem);
  line-height:.95;
  margin:12px 0;
  color:#fff;
  text-shadow:0 0 25px rgba(165,45,84,.55);
}

.subtitle{
  color:var(--muted);
  font-size:1.05rem;
  line-height:1.6;
  max-width:650px;
  margin:auto;
}

.card{
  background:var(--card);
  border:1px solid rgba(255,255,255,.12);
  border-radius:28px;
  padding:clamp(22px,5vw,44px);
  box-shadow:
    0 25px 80px rgba(0,0,0,.5),
    0 0 50px rgba(125,22,56,.12);
  backdrop-filter:blur(12px);
}

.hidden{
  display:none!important;
}

input{
  width:100%;
  padding:16px 18px;
  border-radius:15px;
  border:1px solid rgba(255,255,255,.2);
  background:rgba(0,0,0,.3);
  color:white;
  font:inherit;
  font-size:1.05rem;
  outline:none;
}

input:focus{
  border-color:var(--blue);
  box-shadow:0 0 0 3px rgba(169,223,242,.1);
}

button{
  border:0;
  border-radius:15px;
  padding:15px 20px;
  font:inherit;
  font-weight:bold;
  cursor:pointer;
  transition:
    transform .18s,
    box-shadow .18s,
    background .18s;
}

button:hover{
  transform:translateY(-2px);
}

.primary{
  background:linear-gradient(
    135deg,
    var(--burgundy),
    var(--burgundy2)
  );
  color:white;
  box-shadow:0 10px 30px rgba(125,22,56,.3);
}

.primary:hover{
  box-shadow:0 14px 35px rgba(125,22,56,.5);
}

.secondary{
  background:rgba(255,255,255,.08);
  color:white;
  border:1px solid rgba(255,255,255,.13);
}

.actions{
  display:flex;
  gap:12px;
  flex-wrap:wrap;
  margin-top:18px;
}

.note{
  font-size:.86rem;
  color:var(--muted);
  line-height:1.5;
  margin-top:12px;
}

.error{
  color:var(--red);
  margin-top:10px;
  min-height:1.2em;
}

.quiz-top{
  display:flex;
  justify-content:space-between;
  gap:15px;
  align-items:center;
  color:var(--muted);
  font-size:.9rem;
  margin-bottom:15px;
}

.progress{
  height:8px;
  background:rgba(255,255,255,.09);
  border-radius:99px;
  overflow:hidden;
  margin-bottom:30px;
}

.progress>div{
  height:100%;
  background:linear-gradient(
    90deg,
    var(--burgundy),
    var(--blue)
  );
  width:0%;
  transition:width .3s;
}

.question{
  font-size:clamp(1.55rem,4vw,2.3rem);
  line-height:1.2;
  margin:0 0 25px;
}

.answers{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:13px;
}

.answer{
  text-align:left;
  background:rgba(255,255,255,.055);
  color:white;
  border:1px solid rgba(255,255,255,.12);
  min-height:70px;
  display:flex;
  align-items:center;
  gap:12px;
}

.answer .letter{
  width:34px;
  height:34px;
  border-radius:50%;
  display:grid;
  place-items:center;
  flex:none;
  background:rgba(169,223,242,.12);
  color:var(--blue);
  font-family:Arial,sans-serif;
  font-size:.8rem;
}

.answer:hover{
  background:rgba(125,22,56,.35);
  border-color:rgba(165,45,84,.8);
}

.answer.correct{
  background:rgba(125,226,167,.16);
  border-color:var(--green);
}

.answer.wrong{
  background:rgba(255,120,151,.13);
  border-color:var(--red);
}

.answer:disabled{
  cursor:default;
}

.answer:disabled:hover{
  transform:none;
}

.score-ring{
  width:180px;
  height:180px;
  border-radius:50%;
  margin:8px auto 24px;
  display:grid;
  place-items:center;

  background:
    conic-gradient(
      var(--blue) var(--score),
      rgba(255,255,255,.08) 0
    );

  position:relative;
}

.score-ring:after{
  content:"";
  position:absolute;
  inset:11px;
  background:#15101d;
  border-radius:50%;
}

.score-inner{
  position:relative;
  z-index:1;
  text-align:center;
}

.score-number{
  font-size:2.4rem;
  font-weight:bold;
}

.score-small{
  color:var(--muted);
  font-size:.8rem;
}

.result{
  text-align:center;
}

.result h2{
  font-size:2rem;
  margin:8px 0;
  color:var(--blue);
}

.result p{
  color:var(--muted);
  line-height:1.6;
}

.rank-pill{
  display:inline-block;
  padding:8px 14px;
  border-radius:99px;
  background:rgba(255,215,106,.12);
  color:var(--gold);
  font-weight:bold;
}

.leaderboard{
  margin-top:30px;
}

.leaderboard h3{
  text-align:center;
  font-size:1.5rem;
  margin-bottom:15px;
}

.table{
  border:1px solid rgba(255,255,255,.1);
  border-radius:18px;
  overflow:hidden;
}

.row{
  display:grid;
  grid-template-columns:58px 1fr 90px 85px;
  gap:8px;
  align-items:center;
  padding:13px 15px;
  background:rgba(255,255,255,.025);
}

.row:nth-child(even){
  background:rgba(255,255,255,.045);
}

.row.head{
  font-family:Arial,sans-serif;
  font-size:.72rem;
  text-transform:uppercase;
  letter-spacing:.08em;
  color:var(--muted);
  background:rgba(255,255,255,.07);
}

.row.you{
  outline:1px solid rgba(169,223,242,.5);
  background:rgba(169,223,242,.08);
}

.loading{
  text-align:center;
  color:var(--muted);
  padding:22px;
}

.empty{
  text-align:center;
  color:var(--muted);
  padding:22px;
}

.badge{
  font-size:1.2rem;
}

footer{
  text-align:center;
  color:#7f7180;
  font-size:.75rem;
  margin-top:20px;
}

@media(max-width:650px){

  .answers{
    grid-template-columns:1fr;
  }

  .row{
    grid-template-columns:42px 1fr 72px 65px;
    font-size:.85rem;
  }

  .row.head{
    font-size:.62rem;
  }

  .card{
    border-radius:22px;
  }
}
</style>
</head>

<body>

<div class="wrap">

<header>

  <div class="mini">
    A tiny test of friendship, love &amp; memory
  </div>

  <h1>
    How Well Do You Know Bree? ♡
  </h1>

  <div class="subtitle">
    52 questions. One Bree. Absolutely no excuses.
  </div>

</header>


<!-- START SCREEN -->

<section id="startScreen" class="card">

  <h2>
    Think you know Bree?
  </h2>

  <p
    class="subtitle"
    style="text-align:left"
  >
    Enter your name, answer all 52 questions,
    and see where you land on the leaderboard.
  </p>

  <label
    for="nameInput"
    style="display:block;margin:24px 0 8px"
  >
    Your name
  </label>

  <input
    id="nameInput"
    maxlength="30"
    autocomplete="name"
    placeholder="e.g. Lola"
  >

  <div
    id="nameError"
    class="error"
  ></div>

  <div class="actions">

    <button
      class="primary"
      id="startBtn"
    >
      Start the quiz ♡
    </button>

    <button
      class="secondary"
      id="viewBoardBtn"
    >
      View leaderboard
    </button>

  </div>

  <p class="note">
    Use a first name or nickname only.
    Your name and score will appear on the shared leaderboard.
  </p>

</section>


<!-- QUIZ SCREEN -->

<section
  id="quizScreen"
  class="card hidden"
>

  <div class="quiz-top">

    <span id="questionCounter">
      Question 1 of 52
    </span>

    <span id="playerLabel"></span>

  </div>

  <div class="progress">
    <div id="progressBar"></div>
  </div>

  <h2
    id="questionText"
    class="question"
  ></h2>

  <div
    id="answers"
    class="answers"
  ></div>

</section>


<!-- RESULT SCREEN -->

<section
  id="resultScreen"
  class="card hidden"
>

  <div class="result">

    <div class="mini">
      Quiz complete ♡
    </div>

    <h2 id="resultHeading"></h2>

    <div
      id="scoreRing"
      class="score-ring"
    >

      <div class="score-inner">

        <div
          id="scoreNumber"
          class="score-number"
        >
          0/52
        </div>

        <div
          id="scorePercent"
          class="score-small"
        >
          0%
        </div>

      </div>

    </div>

    <div
      id="rankPill"
      class="rank-pill"
    ></div>

    <p id="resultMessage"></p>

    <div
      class="actions"
      style="justify-content:center"
    >

      <button
        class="primary"
        id="retryBtn"
      >
        Try again
      </button>

      <button
        class="secondary"
        id="backBtn"
      >
        Back to start
      </button>

    </div>

  </div>


  <div class="leaderboard">

    <h3>
      🏆 Bree's Leaderboard
    </h3>

    <div
      id="leaderboard"
      class="table"
    >
      <div class="loading">
        Loading scores...
      </div>
    </div>

  </div>

</section>


<!-- LEADERBOARD SCREEN -->

<section
  id="boardScreen"
  class="card hidden"
>

  <div class="result">

    <div class="mini">
      Who knows Bree best?
    </div>

    <h2>
      🏆 Leaderboard
    </h2>

  </div>

  <div
    id="leaderboardStandalone"
    class="table"
  >
    <div class="loading">
      Loading scores...
    </div>
  </div>

  <div
    class="actions"
    style="justify-content:center"
  >

    <button
      class="primary"
      id="boardStartBtn"
    >
      Take the quiz
    </button>

    <button
      class="secondary"
      id="boardHomeBtn"
    >
      Back
    </button>

  </div>

</section>


<footer>
  Made with love for Bree ♡
</footer>

</div>


<script type="module">

/* ============================================================
   FIREBASE
   ============================================================ */

import {
  initializeApp
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-app.js";

import {
  getFirestore,
  collection,
  addDoc,
  serverTimestamp,
  query,
  orderBy,
  limit,
  getDocs
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-firestore.js";


/*
   PASTE YOUR FIREBASE CONFIG HERE.

   Firebase Console
   → Project settings
   → Your apps
   → Web app
*/

const firebaseConfig = {

  apiKey:
    "PASTE_API_KEY_HERE",

  authDomain:
    "PASTE_PROJECT_ID.firebaseapp.com",

  projectId:
    "PASTE_PROJECT_ID",

  storageBucket:
    "PASTE_PROJECT_ID.firebasestorage.app",

  messagingSenderId:
    "PASTE_SENDER_ID",

  appId:
    "PASTE_APP_ID"

};


let db = null;

const firebaseReady =
  !firebaseConfig.apiKey.startsWith("PASTE_");


if(firebaseReady){

  try{

    const app =
      initializeApp(firebaseConfig);

    db =
      getFirestore(app);

  }catch(err){

    console.error(
      "Firebase initialisation failed:",
      err
    );

  }

}


/* ============================================================
   BREE'S 52 QUESTIONS
   ============================================================ */

const questions = [

  {
    q:"What is Bree's favourite colour?",
    a:[
      "Baby blue",
      "Burgundy",
      "Pink",
      "Black"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite number?",
    a:[
      "7",
      "13",
      "21",
      "27"
    ],
    c:2
  },

  {
    q:"What is Bree's favourite movie genre?",
    a:[
      "Comedy",
      "Romance/Horror",
      "Action",
      "Fantasy"
    ],
    c:1
  },

  {
    q:"What is Bree afraid of?",
    a:[
      "Clowns, moths and rainbows",
      "Dogs, spiders and heights",
      "Thunder, knives and snakes",
      "The ocean, birds and darkness"
    ],
    c:0
  },

  {
    q:"What is Bree's favourite animal?",
    a:[
      "Elephant",
      "Dolphin",
      "Cat",
      "Stingray"
    ],
    c:0
  },

  {
    q:"When is Bree's birthday?",
    a:[
      "June 12th",
      "June 18th",
      "June 21st",
      "July 21st"
    ],
    c:2
  },

  {
    q:"What would Bree choose?",
    a:[
      "Money",
      "Fame",
      "Love",
      "Power"
    ],
    c:2
  },

  {
    q:"If Bree could travel to any country, which would she choose?",
    a:[
      "Japan",
      "Greece",
      "Italy",
      "Canada"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite food?",
    a:[
      "Sushi",
      "Butter chicken",
      "Pizza",
      "Lasagne"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite fruit?",
    a:[
      "Strawberry",
      "Watermelon",
      "Mango",
      "Peach"
    ],
    c:2
  },

  {
    q:"What is Bree's favourite flower?",
    a:[
      "Sunflowers",
      "Lilies/white roses",
      "Tulips",
      "Roses"
    ],
    c:1
  },

  {
    q:"Does Bree prefer the countryside or the city?",
    a:[
      "City",
      "Countryside",
      "Beach town",
      "Mountains"
    ],
    c:1
  },

  {
    q:"Is Bree introverted or extroverted?",
    a:[
      "Introverted",
      "Extroverted",
      "Neither",
      "It depends"
    ],
    c:1
  },

  {
    q:"If Bree had one million dollars, what would she do with it?",
    a:[
      "Buy a sports car",
      "Travel the world",
      "Give it to Lola",
      "Keep every cent"
    ],
    c:2
  },

  {
    q:"How many tattoos does Bree have?",
    a:[
      "None",
      "1–5",
      "10–20",
      "30+"
    ],
    c:3
  },

  {
    q:"How old was Bree when she broke her wrist?",
    a:[
      "4",
      "6",
      "8",
      "10"
    ],
    c:1
  },

  {
    q:"What country did Bree use to live in?",
    a:[
      "Australia",
      "Wales",
      "Canada",
      "Ireland"
    ],
    c:1
  },

  {
    q:"What are Bree's cats' names?",
    a:[
      "Luna & Simba",
      "Lola & Luna",
      "Simba & Milo",
      "Luna & Leo"
    ],
    c:0
  },

  {
    q:"How tall is Bree?",
    a:[
      "5'4 / 163 cm",
      "5'7 / 170 cm",
      "5'10 / 179 cm",
      "6'0 / 183 cm"
    ],
    c:2
  },

  {
    q:"What has Bree wanted to see since she was a little girl?",
    a:[
      "A solar eclipse",
      "The northern lights",
      "A volcano",
      "The pyramids"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite hobby?",
    a:[
      "Painting",
      "Gaming",
      "Poetry",
      "Cooking"
    ],
    c:2
  },

  {
    q:"What is Bree's favourite season?",
    a:[
      "Summer",
      "Winter",
      "Spring",
      "Autumn"
    ],
    c:3
  },

  {
    q:"What is Bree's favourite time of day?",
    a:[
      "Morning",
      "Afternoon",
      "Evening",
      "Night"
    ],
    c:3
  },

  {
    q:"Does Bree prefer sunrise or sunset?",
    a:[
      "Sunrise",
      "Sunset",
      "Both equally",
      "Neither"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite type of weather?",
    a:[
      "Sunny",
      "Rain",
      "Snow",
      "Wind"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite drink?",
    a:[
      "Coffee",
      "Apple juice",
      "Coke",
      "Tea"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite dessert?",
    a:[
      "Chocolate cake",
      "Cheesecake",
      "Lime ice cream",
      "Pavlova"
    ],
    c:2
  },

  {
    q:"What food does Bree hate the most?",
    a:[
      "Vegetables",
      "Seafood",
      "Chocolate",
      "Cheese"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite takeaway?",
    a:[
      "McDonald's",
      "Pizza",
      "Halal snack pack",
      "Fish and chips"
    ],
    c:2
  },

  {
    q:"What is Bree's favourite type of music?",
    a:[
      "Pop",
      "Rock",
      "Country",
      "Classical"
    ],
    c:2
  },

  {
    q:"What is Bree's favourite song?",
    a:[
      "Baby Blue",
      "The One That Got Away",
      "Perfect",
      "Ocean Eyes"
    ],
    c:0
  },

  {
    q:"What is Bree's favourite TV show?",
    a:[
      "Friends",
      "Bridgerton",
      "The Vampire Diaries",
      "Grey's Anatomy"
    ],
    c:1
  },

  {
    q:"What is Bree's favourite book?",
    a:[
      "The Alchemist",
      "Me Before You",
      "The Notebook",
      "Pride and Prejudice"
    ],
    c:0
  },

  {
    q:"What is Bree's biggest pet peeve?",
    a:[
      "Loud chewing",
      "Slow walkers",
      "People being late",
      "Messy rooms"
    ],
    c:0
  },

  {
    q:"What instantly annoys Bree?",
    a:[
      "People who interpret others",
      "People who interrupt others",
      "People who whisper",
      "People who ask questions"
    ],
    c:0
  },

  {
    q:"What does Bree do when she is bored?",
    a:[
      "Sleep",
      "Write",
      "Cook",
      "Go shopping"
    ],
    c:1
  },

  {
    q:"What does Bree do when she is nervous?",
    a:[
      "Laugh loudly",
      "Talk under her breath",
      "Sing",
      "Go completely silent"
    ],
    c:1
  },

  {
    q:"What could Bree talk about for hours?",
    a:[
      "Football",
      "Greek mythology",
      "Cars",
      "Cooking"
    ],
    c:1
  },

  {
    q:"What does Bree spend money on?",
    a:[
      "Clothes",
      "Food",
      "Make-up",
      "Technology"
    ],
    c:1
  },

  {
    q:"What would Bree do first if she became rich?",
    a:[
      "Buy a car",
      "Buy a house for herself",
      "Buy Lola a house",
      "Start a business"
    ],
    c:2
  },

  {
    q:"What is Bree obsessed with?",
    a:[
      "Rugby league",
      "Formula 1",
      "Cricket",
      "Tennis"
    ],
    c:0
  },

  {
    q:"What would Bree absolutely refuse to do?",
    a:[
      "Go skydiving",
      "Eat sushi",
      "Suck toes",
      "Sing in public"
    ],
    c:2
  },

  {
    q:"If Bree could have one superpower, what would she choose?",
    a:[
      "Read minds",
      "Fly",
      "Teleportation",
      "Become invisible"
    ],
    c:2
  },

  {
    q:"What has Bree wanted since childhood?",
    a:[
      "A dancing robot",
      "A pony",
      "A tree house",
      "A private island"
    ],
    c:0
  },

  {
    q:"What does Bree wish people understood about her?",
    a:[
      "She is always confident",
      "She is introverted and sometimes just wants to listen and not speak",
      "She hates being alone",
      "She never gets nervous"
    ],
    c:1
  },

  {
    q:"What does Bree value above almost everything?",
    a:[
      "Money",
      "Honesty",
      "Popularity",
      "Success"
    ],
    c:1
  },

  {
    q:"What instantly makes Bree's day better?",
    a:[
      "Coffee",
      "Music",
      "Lola",
      "Shopping"
    ],
    c:2
  },

  {
    q:"What is Bree secretly sentimental about?",
    a:[
      "Old clothes",
      "When people remember her birthday because everyone forgets",
      "Expensive gifts",
      "Photos of herself"
    ],
    c:1
  },

  {
    q:"What is Bree's biggest weakness?",
    a:[
      "Food",
      "The people she loves",
      "Shopping",
      "Animals"
    ],
    c:1
  },

  {
    q:"What would Bree choose over material things?",
    a:[
      "Fame",
      "Love",
      "Money",
      "Power"
    ],
    c:1
  },

  {
    q:"What kind of life does Bree want?",
    a:[
      "A famous one",
      "A busy one",
      "A peaceful one",
      "A luxurious one"
    ],
    c:2
  },

  {
    q:"What does Bree want Lola to remember forever?",
    a:[
      "Every gift she has given her",
      "The way I love",
      "Every date",
      "Every conversation"
    ],
    c:1
  }

];


/* ============================================================
   QUIZ LOGIC
   ============================================================ */

function shuffle(arr){

  const copy = [...arr];

  for(
    let i = copy.length - 1;
    i > 0;
    i--
  ){

    const j =
      Math.floor(
        Math.random() * (i + 1)
      );

    [
      copy[i],
      copy[j]
    ] = [
      copy[j],
      copy[i]
    ];
  }

  return copy;
}


let quizQuestions = [];

let current = 0;

let score = 0;

let playerName = "";

let locked = false;


const $ = id =>
  document.getElementById(id);


const startScreen =
  $("startScreen");

const quizScreen =
  $("quizScreen");

const resultScreen =
  $("resultScreen");

const boardScreen =
  $("boardScreen");


function showOnly(screen){

  [
    startScreen,
    quizScreen,
    resultScreen,
    boardScreen
  ].forEach(x =>
    x.classList.add("hidden")
  );

  screen.classList.remove("hidden");

  window.scrollTo({
    top:0,
    behavior:"smooth"
  });
}


/* ============================================================
   START
   ============================================================ */

function startQuiz(){

  const name =
    $("nameInput")
      .value
      .trim()
      .replace(/\s+/g," ");

  if(!name){

    $("nameError").textContent =
      "Please enter your name first ♡";

    $("nameInput").focus();

    return;
  }

  $("nameError").textContent = "";

  playerName =
    name.slice(0,30);

  quizQuestions =
    shuffle(questions);

  current = 0;

  score = 0;

  $("playerLabel").textContent =
    playerName;

  showOnly(quizScreen);

  renderQuestion();
}


/* ============================================================
   SHOW QUESTION
   ============================================================ */

function renderQuestion(){

  locked = false;

  const item =
    quizQuestions[current];

  $("questionCounter").textContent =
    `Question ${current + 1} of ${quizQuestions.length}`;

  $("progressBar").style.width =
    `${(current / quizQuestions.length) * 100}%`;

  $("questionText").textContent =
    item.q;

  const answers =
    $("answers");

  answers.innerHTML = "";

  const letters =
    ["A","B","C","D"];


  item.a.forEach(
    (answer,index) => {

      const btn =
        document.createElement("button");

      btn.className =
        "answer";

      btn.innerHTML =
        `
        <span class="letter">
          ${letters[index]}
        </span>

        <span>
          ${answer}
        </span>
        `;

      btn.addEventListener(
        "click",
        () =>
          chooseAnswer(index,btn)
      );

      answers.appendChild(btn);

    }
  );
}


/* ============================================================
   ANSWER
   ============================================================ */

function chooseAnswer(index,button){

  if(locked) return;

  locked = true;

  const item =
    quizQuestions[current];

  const buttons =
    [...$("answers").children];

  buttons.forEach(
    b =>
      b.disabled = true
  );


  if(index === item.c){

    score++;

    button.classList.add(
      "correct"
    );

  }else{

    button.classList.add(
      "wrong"
    );

    buttons[item.c]
      .classList.add("correct");

  }


  setTimeout(
    () => {

      current++;

      if(
        current <
        quizQuestions.length
      ){

        renderQuestion();

      }else{

        finishQuiz();

      }

    },
    420
  );
}


/* ============================================================
   RESULT TIERS
   ============================================================ */

function getTier(percent){

  if(percent >= 90){

    return [
      "Bree's Soulmate",
      "You know Bree ridiculously well. Bree may have to start worrying about how closely you've been paying attention.",
      "💍"
    ];

  }

  if(percent >= 75){

    return [
      "You Really Know Bree",
      "Okay... you've definitely been paying attention. Bree is impressed.",
      "❤️"
    ];

  }

  if(percent >= 60){

    return [
      "Pretty Damn Good",
      "Not bad at all. You know Bree better than most people do.",
      "✨"
    ];

  }

  if(percent >= 40){

    return [
      "You've Been Paying Attention",
      "You know some things. There is still a lot of Bree lore to learn.",
      "👀"
    ];

  }

  if(percent >= 20){

    return [
      "Do You Even Know Bree?",
      "Bree would like to have a little chat with you about this performance.",
      "😭"
    ];

  }

  return [
    "Bree Is Filing A Complaint",
    "This score is so bad that Bree may need to introduce herself again.",
    "💀"
  ];
}


/* ============================================================
   FINISH
   ============================================================ */

async function finishQuiz(){

  $("progressBar").style.width =
    "100%";

  const percent =
    Math.round(
      (score / questions.length) * 100
    );

  const [
    title,
    message,
    emoji
  ] =
    getTier(percent);


  $("resultHeading").textContent =
    title;

  $("scoreNumber").textContent =
    `${score}/${questions.length}`;

  $("scorePercent").textContent =
    `${percent}%`;

  $("scoreRing").style.setProperty(
    "--score",
    `${percent}%`
  );

  $("rankPill").textContent =
    `${emoji} ${title}`;

  $("resultMessage").textContent =
    message;

  showOnly(resultScreen);

  await saveScore();

  await loadLeaderboard(
    $("leaderboard"),
    playerName,
    score
  );
}


/* ============================================================
   SAVE SCORE
   ============================================================ */

async function saveScore(){

  if(!db){

    console.warn(
      "Firebase is not configured. Score cannot be shared online."
    );

    return;
  }


  try{

    await addDoc(
      collection(
        db,
        "breeQuizScores"
      ),
      {
        name:playerName,
        score:score,
        total:questions.length,
        percentage:
          Math.round(
            (score / questions.length) * 100
          ),
        createdAt:
          serverTimestamp()
      }
    );

  }catch(err){

    console.error(
      "Could not save score:",
      err
    );

  }
}


/* ============================================================
   LEADERBOARD
   ============================================================ */

function medal(i){

  if(i === 0)
    return "🥇";

  if(i === 1)
    return "🥈";

  if(i === 2)
    return "🥉";

  return `${i + 1}`;
}


async function loadLeaderboard(
  container,
  highlightName = "",
  highlightScore = -1
){

  container.innerHTML =
    '<div class="loading">Loading scores...</div>';


  if(!db){

    container.innerHTML =
      `
      <div class="empty">
        Leaderboard is offline until Firebase is connected.
      </div>
      `;

    return;
  }


  try{

    const q =
      query(
        collection(
          db,
          "breeQuizScores"
        ),
        orderBy(
          "score",
          "desc"
        ),
        limit(50)
      );


    const snap =
      await getDocs(q);


    if(snap.empty){

      container.innerHTML =
        `
        <div class="empty">
          No scores yet. Be the first!
        </div>
        `;

      return;
    }


    container.innerHTML = "";


    const head =
      document.createElement("div");

    head.className =
      "row head";

    head.innerHTML =
      `
      <div>Rank</div>
      <div>Name</div>
      <div>Score</div>
      <div>%</div>
      `;

    container.appendChild(head);


    snap.docs.forEach(
      (doc,i) => {

        const d =
          doc.data();

        const row =
          document.createElement("div");

        row.className =
          "row";


        if(
          highlightName &&
          d.name === highlightName &&
          d.score === highlightScore
        ){

          row.classList.add("you");

        }


        row.innerHTML =
          `
          <div class="badge">
            ${medal(i)}
          </div>

          <div>
            ${escapeHtml(d.name)}
          </div>

          <div>
            ${Number(d.score)}/${questions.length}
          </div>

          <div>
            ${Number(d.percentage)}%
          </div>
          `;


        container.appendChild(row);

      }
    );

  }catch(err){

    console.error(err);

    container.innerHTML =
      `
      <div class="empty">
        Could not load the leaderboard.
        Check your Firebase setup and Firestore rules.
      </div>
      `;

  }
}


/* ============================================================
   SECURITY
   ============================================================ */

function escapeHtml(value){

  return String(value).replace(
    /[&<>"']/g,

    m =>
      ({
        "&":"&amp;",
        "<":"&lt;",
        ">":"&gt;",
        '"':"&quot;",
        "'":"&#039;"
      }[m])
  );

}


/* ============================================================
   BUTTONS
   ============================================================ */

$("startBtn")
  .addEventListener(
    "click",
    startQuiz
  );


$("nameInput")
  .addEventListener(
    "keydown",
    e => {

      if(e.key === "Enter")
        startQuiz();

    }
  );


$("viewBoardBtn")
  .addEventListener(
    "click",
    async () => {

      showOnly(boardScreen);

      await loadLeaderboard(
        $("leaderboardStandalone")
      );

    }
  );


$("boardStartBtn")
  .addEventListener(
    "click",
    () =>
      showOnly(startScreen)
  );


$("boardHomeBtn")
  .addEventListener(
    "click",
    () =>
      showOnly(startScreen)
  );


$("retryBtn")
  .addEventListener(
    "click",
    () => {

      $("nameInput").value =
        playerName;

      showOnly(startScreen);

      window.setTimeout(
        () => startQuiz(),
        50
      );

    }
  );


$("backBtn")
  .addEventListener(
    "click",
    () => {

      $("nameInput").value = "";

      showOnly(startScreen);

    }
  );


/* Confirm there are exactly 52 questions. */

if(questions.length !== 52){

  console.error(
    `Expected 52 questions, found ${questions.length}.`
  );

}

</script>

</body>
</html>
