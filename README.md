<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Interaktives Quiz: Sport und Gesundheit</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      padding: 20px;
      color: #333;
    }
    h1 {
      text-align: center;
      color: #0066cc;
    }
    .question {
      background: #fff;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .result {
      font-weight: bold;
      margin-top: 10px;
    }
    button {
      margin-top: 10px;
      padding: 10px 15px;
      background-color: #0066cc;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #004c99;
    }
    #score {
      font-size: 18px;
      margin-top: 20px;
      text-align: center;
    }
  </style>
</head>
<body>

  <h1>Interaktives Quiz: Sport und Gesundheit</h1>

  <form id="quizForm">

    <div class="question">
      <p><strong>Frage 1:</strong> Welcher der folgenden Effekte gehört NICHT zu den positiven Auswirkungen von regelmäßigem Ausdauersport?</p>
      <input type="radio" name="q1" value="a"> a) Stärkung des Herz-Kreislauf-Systems<br>
      <input type="radio" name="q1" value="b"> b) Verbesserung der Immunabwehr<br>
      <input type="radio" name="q1" value="c"> c) Reduzierung der Knochendichte<br>
      <input type="radio" name="q1" value="d"> d) Ausschüttung von Glückshormonen<br>
      <p class="result" id="result1"></p>
    </div>

    <div class="question">
      <p><strong>Frage 2:</strong> Welche Rolle spielt Sport bei der Prävention psychischer Erkrankungen?</p>
      <input type="radio" name="q2" value="a"> a) Er kann Depressionen vorbeugen<br>
      <input type="radio" name="q2" value="b"> b) Er fördert Angstzustände<br>
      <input type="radio" name="q2" value="c"> c) Er erhöht das Suchtpotenzial<br>
      <input type="radio" name="q2" value="d"> d) Er verursacht Stresshormone<br>
      <p class="result" id="result2"></p>
    </div>

    <div class="question">
      <p><strong>Frage 3:</strong> Welcher dieser Aspekte wird durch Bewegung am wenigsten beeinflusst?</p>
      <input type="radio" name="q3" value="a"> a) Blutzuckerspiegel<br>
      <input type="radio" name="q3" value="b"> b) emotionale Stabilität<br>
      <input type="radio" name="q3" value="c"> c) genetische Veranlagung<br>
      <input type="radio" name="q3" value="d"> d) Schlafqualität<br>
      <p class="result" id="result3"></p>
    </div>

    <div class="question">
      <p><strong>Frage 4:</strong> Warum hilft Sport bei der Vorbeugung von Herz-Kreislauf-Erkrankungen?</p>
      <input type="radio" name="q4" value="a"> a) Weil er das Herz größer macht<br>
      <input type="radio" name="q4" value="b"> b) Weil er den Blutdruck senkt<br>
      <input type="radio" name="q4" value="c"> c) Weil er die Arterien verengt<br>
      <input type="radio" name="q4" value="d"> d) Weil er den Sauerstoffgehalt im Blut verringert<br>
      <p class="result" id="result4"></p>
    </div>

    <div class="question">
      <p><strong>Frage 5:</strong> Welche Methode eignet sich am besten, um langfristig vom Sport zu profitieren?</p>
      <input type="radio" name="q5" value="a"> a) Intensives Training ohne Pausen<br>
      <input type="radio" name="q5" value="b"> b) Unregelmäßiges Training<br>
      <input type="radio" name="q5" value="c"> c) Regelmäßiges moderates Training<br>
      <input type="radio" name="q5" value="d"> d) Nur mentale Übungen<br>
      <p class="result" id="result5"></p>
    </div>

    <div class="question">
      <p><strong>Frage 6:</strong> Welche Hormone werden beim Sport besonders aktiviert und fördern das Wohlbefinden?</p>
      <input type="radio" name="q6" value="a"> a) Cortisol<br>
      <input type="radio" name="q6" value="b"> b) Insulin<br>
      <input type="radio" name="q6" value="c"> c) Endorphine<br>
      <input type="radio" name="q6" value="d"> d) Adrenalin<br>
      <p class="result" id="result6"></p>
    </div>

    <button type="button" onclick="checkAnswers()">Auswerten</button>
    <div id="score"></div>

  </form>

  <script>
    function checkAnswers() {
      const correctAnswers = {
        q1: 'c',
        q2: 'a',
        q3: 'c',
        q4: 'b',
        q5: 'c',
        q6: 'c'
      };

      let score = 0;

      for (let i = 1; i <= 6; i++) {
        const answer = document.querySelector('input[name="q' + i + '"]:checked');
        const result = document.getElementById('result' + i);
        if (answer) {
          if (answer.value === correctAnswers['q' + i]) {
            result.textContent = "Richtig ✅";
            result.style.color = "green";
            score++;
          } else {
            result.textContent = "Falsch ❌";
            result.style.color = "red";
          }
        } else {
          result.textContent = "Keine Antwort ausgewählt ❗";
          result.style.color = "orange";
        }
      }

      document.getElementById("score").textContent = `Du hast ${score} von 6 Fragen richtig beantwortet.`;
    }
  </script>

</body>
</html>
