<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Class 12 PCM Quiz</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 30px;
      background-color: #f5f5f5;
    }
    .container {
      max-width: 800px;
      margin: auto;
      background-color: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 { color: #2c3e50; }
    .question {
      margin-bottom: 20px;
    }
    .question h4 {
      margin-bottom: 10px;
    }
    .options label {
      display: block;
      margin-bottom: 5px;
      cursor: pointer;
    }
    button {
      padding: 10px 20px;
      background-color: #3498db;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    .timer {
      font-size: 20px;
      font-weight: bold;
      margin-bottom: 20px;
      color: #e74c3c;
    }
    #result {
      margin-top: 20px;
      padding: 15px;
      border-radius: 8px;
      background-color: #ecf0f1;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Class 12 PCM Quiz</h2>
    <p><strong>Marking Scheme:</strong> ✅ Correct: +4, ❌ Incorrect: -3, ➖ Skipped: -1</p>
    <p><strong>Instructions:</strong> All questions are single correct. Do not mark more than one option. Time: 20 minutes</p>

    <div class="timer" id="timer">Time left: 20:00</div>

    <form id="quizForm">
      <div class="question">
        <h4>Student Name:</h4>
        <input type="text" name="studentName" required />
      </div>
      <div class="question">
        <h4>Roll Number:</h4>
        <input type="text" name="rollNo" required />
      </div>

      <div class="question">
        <h4>1. Which of the following is a positive deviated non-ideal solution?</h4>
        <div class="options">
          <label><input type="radio" name="q1" value="A"> Benzene, Toluene</label>
          <label><input type="radio" name="q1" value="B"> Pyridine, Acetic acid</label>
          <label><input type="radio" name="q1" value="C"> Benzene, Acetone</label>
          <label><input type="radio" name="q1" value="D"> Aniline, Acetone</label>
        </div>
      </div>

      <div class="question">
        <h4>2. The vapour pressure of a pure liquid A is 40 mm Hg at 310 K... 10Xₐ?</h4>
        <div class="options">
          <label><input type="radio" name="q2" value="A"> 5.5</label>
          <label><input type="radio" name="q2" value="B"> 8</label>
          <label><input type="radio" name="q2" value="C"> 12.5</label>
          <label><input type="radio" name="q2" value="D"> 5</label>
        </div>
      </div>

      <div class="question">
        <h4>3. Calculate: 5 + 55 + 555 + 5555 + 55555 = ?</h4>
        <div class="options">
          <label><input type="radio" name="q3" value="A"> 61725</label>
          <label><input type="radio" name="q3" value="B"> 61726</label>
          <label><input type="radio" name="q3" value="C"> 61732</label>
          <label><input type="radio" name="q3" value="D"> 61730</label>
        </div>
      </div>

      <div class="question">
        <h4>4. If (log₂(x))/4 = (log₂(y))/6 = (log₂(z))/(3k)... value of k?</h4>
        <div class="options">
          <label><input type="radio" name="q4" value="A"> 8</label>
          <label><input type="radio" name="q4" value="B"> –1</label>
          <label><input type="radio" name="q4" value="C"> 1</label>
          <label><input type="radio" name="q4" value="D"> –8</label>
        </div>
      </div>

      <div class="question">
        <h4>5. An aluminium rod with Young’s modulus Y = 7.0×10¹⁰ N/m² undergoes strain 0.04%</h4>
        <div class="options">
          <label><input type="radio" name="q5" value="A"> 11200</label>
          <label><input type="radio" name="q5" value="B"> 5600</label>
          <label><input type="radio" name="q5" value="C"> 2800</label>
          <label><input type="radio" name="q5" value="D"> 8400</label>
        </div>
      </div>

      <div class="question">
        <h4>6. If Young’s modulus Y = 2×10¹⁰, Poisson ratio = 0.3, find compressibility:</h4>
        <div class="options">
          <label><input type="radio" name="q6" value="A"> 6×10⁻¹⁰</label>
          <label><input type="radio" name="q6" value="B"> 6×10⁻⁹</label>
          <label><input type="radio" name="q6" value="C"> 2.4×10⁻¹⁰</label>
          <label><input type="radio" name="q6" value="D"> 2.4×10⁻⁹</label>
        </div>
      </div>

      <div class="question">
        <h4>7. Final expression: (a×b) + (5/6 × 1/xy) - 2 + (mM/180) = ?</h4>
        <div class="options">
          <label><input type="radio" name="q7" value="A"> 64</label>
          <label><input type="radio" name="q7" value="B"> 27.7</label>
          <label><input type="radio" name="q7" value="C"> 97</label>
          <label><input type="radio" name="q7" value="D"> 99</label>
        </div>
      </div>

      <button type="submit">Submit Quiz</button>
    </form>

    <div id="result" style="display:none;"></div>
  </div>

  <script>
    const timerDisplay = document.getElementById('timer');
    let time = 20 * 60;

    function updateTimer() {
      const minutes = Math.floor(time / 60);
      const seconds = time % 60;
      timerDisplay.textContent = \`Time left: \${minutes.toString().padStart(2, '0')}:\${seconds.toString().padStart(2, '0')}\`;
      if (time > 0) {
        time--;
        setTimeout(updateTimer, 1000);
      } else {
        alert("Time's up! Auto-submitting the quiz.");
        document.getElementById('quizForm').requestSubmit();
      }
    }

    updateTimer();

    const answerKey = {
      q1: "C",
      q2: "B",
      q3: "A",
      q4: "D",
      q5: "B",
      q6: "B",
      q7: "C"
    };

    document.getElementById('quizForm').addEventListener('submit', function(e) {
      e.preventDefault();
      let form = e.target;
      let correct = 0, incorrect = 0, skipped = 0;

      for (let i = 1; i <= 7; i++) {
        const q = form["q" + i];
        if (!q || !q.value) {
          skipped++;
        } else if (q.value === answerKey["q" + i]) {
          correct++;
        } else {
          incorrect++;
        }
      }

      const score = correct * 4 + incorrect * -3 + skipped * -1;

      const result = document.getElementById("result");
      result.style.display = "block";
      result.innerHTML = `
        <strong>Result Report for ${form.studentName.value} (Roll No: ${form.rollNo.value})</strong><br>
        ✅ Correct: ${correct}<br>
        ❌ Incorrect: ${incorrect}<br>
        ➖ Skipped: ${skipped}<br>
        📊 Total Score: ${score}
      `;
    });
  </script>
</body>
</html>
