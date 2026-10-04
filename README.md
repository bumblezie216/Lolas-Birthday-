<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>How Well Do You Know Bree?</title>
<style>
    * {
        box-sizing: border-box;
    }
    body {
        margin: 0;
        min-height: 100vh;
        font-family: Georgia, "Times New Roman", serif;
        background:
            radial-gradient(circle at top, #5b1735 0%, #240b18 45%, #090308 100%);
        color: #fff;
        overflow-x: hidden;
    }
    body::before {
        content: "";
        position: fixed;
        inset: 0;
        pointer-events: none;
        background-image:
            radial-gradient(circle, rgba(255,255,255,.8) 1px, transparent 1px),
            radial-gradient(circle, rgba(255,255,255,.5) 1px, transparent 1px);
        background-size: 90px 90px, 150px 150px;
        background-position: 10px 20px, 50px 80px;
        opacity: .18;
    }
    .container {
        width: min(900px, 92%);
        margin: auto;
        padding: 45px 0 70px;
    }
    .screen {
        display: none;
        animation: fadeIn .5s ease;
    }
    .screen.active {
        display: block;
    }
    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(15px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
    .card {
        background: rgba(20, 5, 13, .88);
        border: 1px solid rgba(255, 180, 210, .25);
        border-radius: 25px;
        padding: 35px;
        box-shadow:
            0 25px 70px rgba(0,0,0,.5),
            inset 0 0 40px rgba(255,80,150,.04);
        backdrop-filter: blur(10px);
    }
    .intro {
        text-align: center;
        padding: 55px 35px;
    }
    .heart {
        font-size: 65px;
        animation: heartbeat 1.8s infinite;
    }
    @keyframes heartbeat {
        0%,100% { transform: scale(1); }
        15% { transform: scale(1.12); }
        30% { transform: scale(1); }
    }
    h1 {
        font-size: clamp(35px, 7vw, 65px);
        margin: 15px 0;
        color: #ffd7e6;
    }
    h2 {
        color: #ffc4da;
        font-size: 30px;
    }
    .subtitle {
        color: #d8aabb;
        font-size: 18px;
        line-height: 1.7;
    }
    input[type="text"] {
        width: 100%;
        max-width: 450px;
        padding: 17px 20px;
        border-radius: 14px;
        border: 1px solid #9c526f;
        background: rgba(0,0,0,.35);
        color: white;
        font-size: 18px;
        outline: none;
        margin: 20px auto;
        display: block;
        text-align: center;
    }
    input[type="text"]:focus {
        border-color: #ff9fc3;
        box-shadow: 0 0 20px rgba(255,120,170,.2);
    }
    button {
        border: none;
        border-radius: 14px;
        padding: 15px 28px;
        font-size: 17px;
        font-family: inherit;
        cursor: pointer;
        transition: .2s;
    }
    .primary {
        background: linear-gradient(135deg, #e86c9c, #9f315e);
        color: white;
        box-shadow: 0 8px 25px rgba(180,50,100,.3);
    }
    button:hover {
        transform: translateY(-2px);
        filter: brightness(1.1);
    }
    button:disabled {
        opacity: .5;
        cursor: not-allowed;
        transform: none;
    }
    .quiz-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 20px;
        margin-bottom: 25px;
    }
    .progress {
        color: #d8aabb;
    }
    .progress-bar {
        width: 100%;
        height: 8px;
        background: rgba(255,255,255,.08);
        border-radius: 20px;
        overflow: hidden;
        margin-bottom: 30px;
    }
    .progress-fill {
        height: 100%;
        width: 0%;
        background: linear-gradient(90deg, #9f315e, #ff9fc3);
        transition: width .3s ease;
    }
    .question {
        font-size: 28px;
        line-height: 1.35;
        color: #fff0f6;
        margin-bottom: 25px;
    }
    .answers {
        display: grid;
        gap: 12px;
    }
    .answer {
        width: 100%;
        text-align: left;
        background: rgba(255,255,255,.055);
        border: 1px solid rgba(255,180,210,.18);
        color: #fff;
        padding: 18px;
        border-radius: 14px;
    }
    .answer:hover {
        background: rgba(255,150,190,.1);
        border-color: #b85b7e;
    }
    .answer.selected {
        background: rgba(190,65,110,.3);
        border-color: #ff91b9;
    }
    .answer.correct {
        background: rgba(60,160,100,.25);
        border-color: #72e09a;
    }
    .answer.wrong {
        background: rgba(180,40,60,.3);
        border-color: #ff7184;
    }
    .quiz-controls {
        display: flex;
        justify-content: space-between;
        margin-top: 30px;
    }
    .small-btn {
        background: rgba(255,255,255,.08);
        color: white;
        border: 1px solid rgba(255,255,255,.15);
    }
    .result {
        text-align: center;
    }
    .score-circle {
        width: 180px;
        height: 180px;
        border-radius: 50%;
        margin: 30px auto;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background:
            radial-gradient(circle, #260c19 55%, transparent 56%),
            conic-gradient(#ff8fb8 var(--score), #3a1727 0);
    }
    .score-number {
        font-size: 48px;
        font-weight: bold;
        color: #ffd7e6;
    }
    .score-label {
        color: #cda8b7;
    }
    .result-message {
        font-size: 20px;
        line-height: 1.6;
        color: #e8cbd6;
    }
    .leaderboard {
        margin-top: 35px;
    }
    .leaderboard h3 {
        color: #ffc4da;
        font-size: 25px;
    }
    .leader-row {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 15px 18px;
        margin: 8px 0;
        border-radius: 12px;
        background: rgba(255,255,255,.05);
    }
    .rank {
        width: 35px;
        font-weight: bold;
        color: #ffadc8;
    }
    .player-name {
        flex: 1;
        text-align: left;
    }
    .player-score {
        font-weight: bold;
        color: #ffd1e2;
    }
    .empty {
        color: #aa8a98;
        font-style: italic;
    }
    .note {
        font-size: 13px;
        color: #92717f;
        margin-top: 20px;
    }
    @media(max-width:600px) {
        .card {
            padding: 25px 18px;
        }
        .question {
            font-size: 23px;
        }
        .quiz-header {
            align-items: flex-start;
            flex-direction: column;
        }
    }
</style>
</head>
<body>
<div class="container">
    <!-- START -->
    <section id="startScreen" class="screen active">
        <div class="card intro">
            <div class="heart">♡</div>
            <h1>How Well Do You Know Bree?</h1>
            <p class="subtitle">
                Think you know Bree?<br>
                Let's see how well you actually know her.
            </p>
            <input
                type="text"
                id="playerName"
                placeholder="Enter your name..."
                maxlength="30"
            >
            <button class="primary" onclick="startQuiz()">
                Start the Quiz
            </button>
        </div>
    </section>
    <!-- QUIZ -->
    <section id="quizScreen" class="screen">
        <div class="card">
            <div class="quiz-header">
                <div>
                    <strong id="welcome"></strong>
                </div>
                <div class="progress" id="progressText">
                    Question 1 of 30
                </div>
            </div>
            <div class="progress-bar">
                <div class="progress-fill" id="progressFill"></div>
            </div>
            <div id="questionText" class="question"></div>
            <div id="answers" class="answers"></div>
            <div class="quiz-controls">
                <button
                    class="small-btn"
                    id="backBtn"
                    onclick="previousQuestion()"
                    disabled
                >
                    ← Back
                </button>
                <button
                    class="primary"
                    id="nextBtn"
                    onclick="nextQuestion()"
                    disabled
                >
                    Next →
                </button>
            </div>
        </div>
    </section>
    <!-- RESULTS -->
    <section id="resultScreen" class="screen">
        <div class="card result">
            <div class="heart">♡</div>
            <h1 id="resultTitle">Quiz Complete</h1>
            <p class="subtitle" id="resultName"></p>
            <div
                class="score-circle"
                id="scoreCircle"
                style="--score: 0%"
            >
                <div class="score-number" id="scoreNumber">0%</div>
                <div class="score-label">Bree knowledge</div>
            </div>
            <p class="result-message" id="resultMessage"></p>
            <button class="primary" onclick="showLeaderboard()">
                See Who Knows Bree Best
            </button>
            <button
                class="small-btn"
                onclick="location.reload()"
                style="margin-left:8px"
            >
                Take Again
            </button>
            <div id="leaderboard" class="leaderboard"></div>
            <p class="note">
                Scores are saved in this browser.
            </p>
        </div>
    </section>
</div>
<script>
const questions = [
    {
        question: "What is Bree's biggest pet peeve?",
        answers: [
            "Loud chewing",
            "People being late",
            "Messy rooms",
            "Slow walkers"
        ],
        correct: 0
    },
    {
        question: "What instantly annoys Bree?",
        answers: [
            "People who interpret others",
            "People who talk too quietly",
            "People who ask too many questions",
            "People who text too much"
        ],
        correct: 0
    },
    {
        question: "What does Bree do when she is bored?",
        answers: [
            "Write",
            "Watch television",
            "Go shopping",
            "Play games"
        ],
        correct: 0
    },
    {
        question: "What is Bree's favourite kind of weather?",
        answers: [
            "Rainy and stormy",
            "Hot and sunny",
            "Snowy",
            "Foggy"
        ],
        correct: 0
    },
    {
        question: "What does Bree love most about sunsets?",
        answers: [
            "The colours",
            "The temperature",
            "The silence",
            "Taking photographs"
        ],
        correct: 0
    },
    {
        question: "What animal does Bree love?",
        answers: [
            "Cats",
            "Dogs",
            "Dolphins",
            "Horses"
        ],
        correct: 0
    },
    {
        question: "What is Bree's favourite colour?",
        answers: [
            "Burgundy",
            "Baby blue",
            "Pink",
            "Purple"
        ],
        correct: 0
    },
    {
        question: "What is Bree's height?",
        answers: [
            "5'10",
            "5'6",
            "5'8",
            "6'0"
        ],
        correct: 0
    },
    {
        question: "What does Bree enjoy doing when she has words in her head?",
        answers: [
            "Writing",
            "Painting",
            "Singing",
            "Cooking"
        ],
        correct: 0
    },
    {
        question: "What does Bree dislike eating?",
        answers: [
            "Sushi",
            "Pizza",
            "Pasta",
            "Burgers"
        ],
        correct: 0
    },
    {
        question: "What name does Bree sometimes go by?",
        answers: [
            "Putiputi",
            "Lola",
            "Liliana",
            "Yuna"
        ],
        correct: 0
    },
    {
        question: "What is Bree's favourite kind of writing?",
        answers: [
            "Poetry",
            "News articles",
            "Essays",
            "Recipes"
        ],
        correct: 0
    },
    {
        question: "What does Bree tend to do when she has too many thoughts?",
        answers: [
            "Write them down",
            "Go running",
            "Clean the house",
            "Watch movies"
        ],
        correct: 0
    },
    {
        question: "What country does Bree live in?",
        answers: [
            "New Zealand",
            "Australia",
            "Canada",
            "United States"
        ],
        correct: 0
    },
    {
        question: "What is Bree's favourite place to see the sunset?",
        answers: [
            "The beach",
            "A city rooftop",
            "A forest",
            "A mountain"
        ],
        correct: 0
    },
    {
        question: "What does Bree love about the ocean?",
        answers: [
            "The feeling of freedom",
            "The crowds",
            "The noise",
            "The heat"
        ],
        correct: 0
    },
    {
        question: "What does Bree prefer when writing music?",
        answers: [
            "Female vocals or piano",
            "Heavy metal",
            "Rap",
            "Instrumental rock"
        ],
        correct: 0
    },
    {
        question: "What colour is strongly associated with Bree?",
        answers: [
            "Burgundy",
            "Neon green",
            "Orange",
            "Yellow"
        ],
        correct: 0
    },
    {
        question: "What is one thing Bree can spend a lot of time doing?",
        answers: [
            "Writing",
            "Gardening",
            "Fishing",
            "Running"
        ],
        correct: 0
    },
    {
        question: "What kind of stories does Bree enjoy creating?",
        answers: [
            "Romantic and emotional stories",
            "Crime reports",
            "Historical textbooks",
            "Cooking guides"
        ],
        correct: 0
    },
    {
        question: "What does Bree like looking at in the night sky?",
        answers: [
            "Stars",
            "Airplanes",
            "Clouds only",
            "Street lights"
        ],
        correct: 0
    },
    {
        question: "Which natural phenomenon has Bree used as inspiration for poetry?",
        answers: [
            "The northern lights",
            "Earthquakes",
            "Volcanoes",
            "Hurricanes"
        ],
        correct: 0
    },
    {
        question: "What does Bree like about poetry?",
        answers: [
            "Being able to turn feelings into words",
            "Following strict rules",
            "Keeping everything factual",
            "Making everything rhyme"
        ],
        correct: 0
    },
    {
        question: "What kind of atmosphere does Bree often like in creative projects?",
        answers: [
            "Galaxy and stars",
            "Bright neon",
            "Minimal white",
            "Tropical jungle"
        ],
        correct: 0
    },
    {
        question: "What is Bree's relationship with Lola?",
        answers: [
            "They are dating",
            "They are cousins",
            "They are colleagues",
            "They are neighbours"
        ],
        correct: 0
    },
    {
        question: "What does Bree call Lola instead of 'babe'?",
        answers: [
            "Baby or my love",
            "Sweetheart only",
            "Darling only",
            "Princess"
        ],
        correct: 0
    },
    {
        question: "What does Bree love about Lola's voice?",
        answers: [
            "It helps her through storms",
            "It makes her laugh",
            "It wakes her up",
            "It helps her study"
        ],
        correct: 0
    },
    {
        question: "What does Bree want to experience with Lola someday?",
        answers: [
            "Dancing, singing, painting and travelling through life together",
            "Only travelling",
            "Only cooking together",
            "Only watching films"
        ],
        correct: 0
    },
    {
        question: "How long have Bree and Liliana been best friends?",
        answers: [
            "Six years",
            "Two years",
            "Four years",
            "Ten years"
        ],
        correct: 0
    },
    {
        question: "What is one thing Bree is especially passionate about?",
        answers: [
            "Putting emotions into words",
            "Competitive sports",
            "Car racing",
            "Cooking competitions"
        ],
        correct: 0
    }
];
// Shuffle the questions while keeping the answers attached.
questions.sort(() => Math.random() - 0.5);
let currentQuestion = 0;
let score = 0;
let selectedAnswer = null;
let player = "";
function startQuiz() {
    const input = document.getElementById("playerName");
    player = input.value.trim();
    if (!player) {
        input.focus();
        input.placeholder = "Please enter your name first...";
        return;
    }
    document.getElementById("startScreen").classList.remove("active");
    document.getElementById("quizScreen").classList.add("active");
    document.getElementById("welcome").textContent =
        "Good luck, " + player + " ♡";
    showQuestion();
}
function showQuestion() {
    const q = questions[currentQuestion];
    selectedAnswer = null;
    document.getElementById("questionText").textContent =
        q.question;
    document.getElementById("progressText").textContent =
        `Question ${currentQuestion + 1} of ${questions.length}`;
    document.getElementById("progressFill").style.width =
        ((currentQuestion + 1) / questions.length * 100) + "%";
    const answers = document.getElementById("answers");
    answers.innerHTML = "";
    q.answers.forEach((answer, index) => {
        const button = document.createElement("button");
        button.className = "answer";
        button.textContent = answer;
        button.onclick = () => selectAnswer(index, button);
        answers.appendChild(button);
    });
    document.getElementById("nextBtn").disabled = true;
    document.getElementById("backBtn").disabled =
        currentQuestion === 0;
}
function selectAnswer(index, button) {
    selectedAnswer = index;
    document.querySelectorAll(".answer").forEach(btn => {
        btn.classList.remove("selected");
    });
    button.classList.add("selected");
    document.getElementById("nextBtn").disabled = false;
}
function nextQuestion() {
    if (selectedAnswer === null) return;
    if (selectedAnswer === questions[currentQuestion].correct) {
        score++;
    }
    currentQuestion++;
    if (currentQuestion >= questions.length) {
        finishQuiz();
    } else {
        showQuestion();
    }
}
function previousQuestion() {
    if (currentQuestion === 0) return;
    currentQuestion--;
    showQuestion();
}
function finishQuiz() {
    const percentage =
        Math.round((score / questions.length) * 100);
    document.getElementById("quizScreen")
        .classList.remove("active");
    document.getElementById("resultScreen")
        .classList.add("active");
    document.getElementById("resultName").textContent =
        `${player}, you scored ${score} out of ${questions.length}.`;
    document.getElementById("scoreNumber").textContent =
        percentage + "%";
    document.getElementById("scoreCircle")
        .style.setProperty("--score", percentage + "%");
    let message;
    if (percentage === 100) {
        message =
            "You got every single question right. You officially know Bree ridiculously well.";
    } else if (percentage >= 90) {
        message =
            "Okay... you REALLY know Bree. That's seriously impressive.";
    } else if (percentage >= 75) {
        message =
            "You know Bree pretty damn well. There are only a few things left to learn.";
    } else if (percentage >= 50) {
        message =
            "Not bad! You know Bree, but there is definitely more studying to do.";
    } else if (percentage >= 25) {
        message =
            "Bree might need to give you a little homework.";
    } else {
        message =
            "We may need to question whether you know Bree at all.";
    }
    document.getElementById("resultMessage").textContent =
        message;
    saveScore(player, score, questions.length);
}
function saveScore(name, score, total) {
    const results =
        JSON.parse(localStorage.getItem("breeQuizResults")) || [];
    results.push({
        name: name,
        score: score,
        total: total,
        percentage: Math.round((score / total) * 100),
        date: new Date().toISOString()
    });
    results.sort((a, b) => b.percentage - a.percentage);
    localStorage.setItem(
        "breeQuizResults",
        JSON.stringify(results)
    );
}
function showLeaderboard() {
    const results =
        JSON.parse(localStorage.getItem("breeQuizResults")) || [];
    const board =
        document.getElementById("leaderboard");
    if (results.length === 0) {
        board.innerHTML =
            "<h3>Leaderboard</h3><p class='empty'>No scores yet.</p>";
        return;
    }
    board.innerHTML = "<h3>♡ Bree's Leaderboard ♡</h3>";
    results.forEach((result, index) => {
        const row = document.createElement("div");
        row.className = "leader-row";
        row.innerHTML = `
            <span class="rank">#${index + 1}</span>
            <span class="player-name">${escapeHTML(result.name)}</span>
            <span class="player-score">
                ${result.score}/${result.total} · ${result.percentage}%
            </span>
        `;
        board.appendChild(row);
    });
}
function escapeHTML(text) {
    const div = document.createElement("div");
    div.textContent = text;
    return div.innerHTML;
}
</script>
</body>
</html>
