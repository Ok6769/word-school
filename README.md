<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Französisch lernen</title>

<style>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 50px;
}

.container {
    max-width: 500px;
    margin: auto;
}

button {
    display: block;
    width: 100%;
    padding: 12px;
    margin: 10px 0;
    font-size: 18px;
    cursor: pointer;
}

#result {
    font-size: 20px;
    margin-top: 20px;
    font-weight: bold;
}
</style>
</head>
<body>

<div class="container">
    <h1>Französisch lernen</h1>

    <h2 id="word"></h2>

    <button onclick="checkAnswer(0)" id="btn0"></button>
    <button onclick="checkAnswer(1)" id="btn1"></button>
    <button onclick="checkAnswer(2)" id="btn2"></button>

    <p id="result"></p>

    <p>Punkte: <span id="score">0</span></p>
</div>

<script>
const questions = [
{word:"das Kino",answers:["le cinéma","le vampire","la pomme"],correct:0},
{word:"eine Spinne",answers:["une araignée","un chevalier","une sorcière"],correct:0},
{word:"ein Feind",answers:["un ennemi","un héros","un géant"],correct:0},
{word:"flink",answers:["agile","violent","honnête"],correct:0},
{word:"zuverlässig",answers:["fiable","cruel","jaloux"],correct:0},
{word:"der Ritter",answers:["le chevalier","le vampire","le géant"],correct:0},
{word:"mutig",answers:["courageux","belle","méchant"],correct:0},
{word:"der Mut",answers:["le courage","la magie","la force"],correct:0},
{word:"ehrlich",answers:["honnête","violent","jaloux"],correct:0},
{word:"grausam",answers:["cruel","agile","fiable"],correct:0},
{word:"böse",answers:["méchant","beau","immortel"],correct:0},
{word:"die Hexe",answers:["la sorcière","la fleur","la maison"],correct:0},
{word:"eifersüchtig",answers:["jaloux","ambitieux","violent"],correct:0},
{word:"der Vampir",answers:["le vampire","le héros","le chat"],correct:0},
{word:"unsterblich",answers:["immortel","courageux","honnête"],correct:0},
{word:"schwachhaft",answers:["bavard","beau","géant"],correct:0},
{word:"ehrgeizig",answers:["ambitieux","jaloux","agile"],correct:0},
{word:"der Held",answers:["le héros","le vampire","le chevalier"],correct:0},
{word:"riesig",answers:["géant","petit","agile"],correct:0},
{word:"schön",answers:["beau","cruel","fiable"],correct:0},
{word:"gewalttätig",answers:["violent","honnête","immortel"],correct:0}
];

let current = 0;
let score = 0;

function loadQuestion() {
document.getElementById("word").textContent =
questions[current].word;

for(let i=0;i<3;i++){
document.getElementById("btn"+i).textContent =
questions[current].answers[i];
}

document.getElementById("result").textContent = "";
}

function checkAnswer(choice) {
if(choice === questions[current].correct){
score++;
document.getElementById("result").textContent =
"✅ Richtig!";
} else {
document.getElementById("result").textContent =
"❌ Falsch!";
}

document.getElementById("score").textContent = score;

current++;

if(current < questions.length){
setTimeout(loadQuestion, 1000);
} else {
setTimeout(() => {
document.querySelector(".container").innerHTML =
`
<h1>Test beendet!</h1>
<h2>Dein Ergebnis: ${score}/${questions.length}</h2>

<button onclick="location.reload()">
Neu starten
</button>
`;
<h2>Dein Ergebnis: ${score}/${questions.length}</h2>`;
}, 1000);
}
}

loadQuestion();
</script>

</body>
</html>
