<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>🎁 Zábavní Test – Získej Startovní Bonus</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: Arial, sans-serif; background: #f9fbfd; margin: 0; padding: 0; }
    .box { max-width: 600px; margin: 40px auto; background: #fff; padding: 30px; border-radius: 12px; box-shadow: 0 4px 16px rgba(0,0,0,0.1); }
    h1, h2 { text-align: center; color: #2c3e50; }
    .step { display: none; margin-top: 20px; }
    .step.active { display: block; }
    label { display: block; margin: 12px 0; cursor: pointer; }
    button { width: 100%; padding: 12px; background: #1abc9c; color: white; border: none; border-radius: 6px; font-size: 16px; margin-top: 20px; cursor: pointer; }
    button:hover { background: #159a84; }
    .result { display: none; background: #eafaf7; padding: 25px; margin-top: 25px; border-left: 5px solid #1abc9c; text-align: center; }
    .footer { text-align: center; font-size: 12px; color: #7f8c8d; margin-top: 30px; }
    .progress-bar { height: 10px; background: #e0e0e0; border-radius: 5px; overflow: hidden; margin: 10px 0; }
    .progress { height: 10px; width: 0%; background: #1abc9c; transition: width 0.4s ease; }
  </style>
</head>
<body>
  <div class="box">
    <h1>🎯 Odpověz na 3 otázky a zjisti svůj bonus!</h1>

    <div class="step step1 active">
      <h2>Krok 1 z 3</h2>
      <p>Jaké hry tě nejvíc baví?</p>
      <label><input type="radio" name="q1"> 🎰 Automatové hry</label>
      <label><input type="radio" name="q1"> 🃏 Karetní souboje</label>
      <label><input type="radio" name="q1"> 🏆 Turnaje a výzvy</label>
      <button onclick="nextStep(1)">Pokračovat</button>
    </div>

    <div class="step step2">
      <h2>Krok 2 z 3</h2>
      <p>Kdy si nejraději odpočíváš?</p>
      <label><input type="radio" name="q2"> 🌞 Odpoledne</label>
      <label><input type="radio" name="q2"> 🌆 Večer</label>
      <label><input type="radio" name="q2"> 🌙 V noci</label>
      <button onclick="nextStep(2)">Pokračovat</button>
    </div>

    <div class="step step3">
      <h2>Krok 3 z 3</h2>
      <p>Vyber si talisman štěstí:</p>
      <label><input type="radio" name="q3"> 🍀 Čtyřlístek</label>
      <label><input type="radio" name="q3"> 🧲 Magnet na výhry</label>
      <label><input type="radio" name="q3"> 🦄 Magický jednorožec</label>
      <button onclick="showResult()">Zobrazit výsledek</button>
    </div>

    <div class="result" id="result">
      <h2>🎉 Gratulujeme!</h2>
      <p>Tvůj bonus <strong>+200%</strong> na začátek je připraven 🎁</p>
      <div class="progress-bar"><div id="progress" class="progress"></div></div>
      <p><strong>Zbývá čas:</strong> Aktivuj během 15 minut</p>
      <a href="https://www.tipsport.cz/vegas" target="_blank">
        <button>Zaregistrovat se</button>
      </a>
    </div>

    <div class="footer">
      ✔️ Legální v ČR · ✔️ Věk 18+ · ✔️ Ověřeno MFČR (Ministerstvo financí)
    </div>
  </div>

  <script>
    function nextStep(step) {
      if (document.querySelector(`input[name="q${step}"]:checked`)) {
        document.querySelector(`.step${step}`).classList.remove('active');
        document.querySelector(`.step${step + 1}`).classList.add('active');
      } else {
        alert("Prosím vyber možnost pro pokračování.");
      }
    }

    function showResult() {
      if (document.querySelector('input[name="q3"]:checked')) {
        document.querySelector('.step3').classList.remove('active');
        document.getElementById('result').style.display = 'block';
        setTimeout(() => {
          document.getElementById('progress').style.width = '100%';
        }, 300);
        window.scrollTo({ top: document.getElementById('result').offsetTop, behavior: 'smooth' });
      } else {
        alert("Vyber si talisman před pokračováním.");
      }
    }
  </script>
</body>
</html>
