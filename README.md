!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Clarvoint – Past Life Generator</title>
  <style>
    body {
      margin: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont;
      background: radial-gradient(circle at top, #0a1a2f, #020617);
      color: #e5f0ff;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .card {
      background: rgba(10, 20, 40, 0.85);
      padding: 28px;
      border-radius: 16px;
      max-width: 340px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.6);
    }
    h1 {
      color: #4fc3ff;
      margin-bottom: 6px;
    }
    button {
      margin-top: 18px;
      padding: 12px 18px;
      font-size: 16px;
      border: none;
      border-radius: 999px;
      background: linear-gradient(135deg, #4fc3ff, #7c9cff);
      color: #020617;
      cursor: pointer;
    }
    .result {
      margin-top: 18px;
      font-size: 14px;
      line-height: 1.5;
      opacity: 0;
      transition: opacity 0.6s ease;
    }
    .result.show {
      opacity: 1;
    }
  </style>
</head>
<body>

<div class="card">
  <h1>Clarvoint</h1>
  <p>Past life generator</p>

  <button onclick="generatePastLife()">Reveal Past Life</button>

  <div id="result" class="result"></div>
</div>

<script>
const eras = [
  "Ancient Egypt", "Medieval Europe", "Feudal Japan",
  "Mayan Civilization", "Victorian England",
  "Ancient Greece", "Silk Road Asia", "Early Americas"
];

const roles = [
  "healer", "scribe", "warrior", "artisan",
  "monk", "navigator", "merchant", "storykeeper"
];

const locations = [
  "near a great river", "within stone walls",
  "on a trade route", "in a mountain village",
  "by the sea", "beneath desert skies"
];

const endings = [
  "peacefully with age",
  "during a time of conflict",
  "from illness",
  "while protecting others",
  "on a long journey",
  "after completing important work"
];

const lessons = [
  "learning patience",
  "letting go of fear",
  "trusting intuition",
  "balancing duty and desire",
  "speaking truth",
  "carrying wisdom forward"
];

function pick(arr) {
  return arr[Math.floor(Math.random() * arr.length)];
}

function generatePastLife() {
  const text = `
You lived during <b>${pick(eras)}</b> as a <b>${pick(roles)}</b>.
Your life unfolded ${pick(locations)}.
You passed ${pick(endings)}.

Your soul carried forward a lesson of <b>${pick(lessons)}</b>.
  `;
  const result = document.getElementById("result");
  result.innerHTML = text;
  result.classList.remove("show");
  setTimeout(() => result.classList.add("show"), 50);
}
</script>

</body>
</html>
