<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Quiz Interativo - Fluxo do Recebimento</title>
<style>
  body {
    font-family: "Segoe UI", sans-serif;
    background: linear-gradient(180deg, #e7f0fd, #f5f7fa);
    color: #333;
    margin: 0;
    padding: 20px;
  }
  h1 {
    text-align: center;
    background: #005fa3;
    color: white;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
  }
  .start-screen, .end-screen {
    max-width: 700px;
    margin: 40px auto;
    background: white;
    padding: 30px;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    text-align: center;
    animation: fadeInUp 1s ease;
  }
  .start-screen input {
    padding: 10px;
    border-radius: 8px;
    border: 1px solid #ccc;
    width: 80%;
    margin-top: 10px;
    font-size: 16px;
  }
  button {
    background-color: #0078d7;
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 16px;
    margin: 15px auto;
    transition: 0.3s;
  }
  button:hover { background-color: #005fa3; transform: scale(1.05); }
  .quiz-container {
    max-width: 850px;
    margin: 30px auto;
    background: white;
    padding: 25px;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    display: none;
  }
  .question { font-weight: bold; margin-top: 15px; }
  .options label { display: block; margin: 8px 0; cursor: pointer; }
  .correct { background: #e8f9f0; border-left: 6px solid #2ecc71; color: #2b8a3e; padding: 8px; border-radius: 6px; }
  .incorrect { background: #fdecea; border-left: 6px solid #e74c3c; color: #c0392b; padding: 8px; border-radius: 6px; }
  .timer { text-align: center; font-size: 20px; font-weight: bold; color: #005fa3; margin-top: 10px; }
  .medal { font-size: 80px; animation: bounceIn 1s ease; }
  .gold { color: gold; }
  .silver { color: silver; }
  .bronze { color: #cd7f32; }
  .ranking {
    background: #eef6ff;
    padding: 15px;
    border-radius: 10px;
    margin-top: 20px;
    font-size: 16px;
    text-align: left;
  }
  .ranking h4 { text-align: center; color: #005fa3; }
  .ranking ol { padding-left: 25px; }
  @keyframes bounceIn {
    0% { transform: scale(0.3); opacity: 0; }
    50% { transform: scale(1.1); opacity: 1; }
    70% { transform: scale(0.9); }
    100% { transform: scale(1); }
  }
</style>
</head>
<body>
<h1>Quiz Interativo – Fluxo do Recebimento</h1>

<!-- Tela inicial -->
<div id="startScreen" class="start-screen">
  <h2>🧠 Bem-vindo(a) ao Desafio do Conferente!</h2>
  <p>
    Teste seus conhecimentos sobre o <strong>Fluxo do Recebimento</strong>.<br><br>
    ⏱ Você terá <strong>3 minutos</strong> para responder <strong>7 perguntas</strong>.<br>
    💡 Cada resposta traz uma explicação didática.<br><br>
    Digite seu nome para começar:
  </p>
  <input type="text" id="playerName" placeholder="Digite seu nome aqui">
  <br>
  <button onclick="startQuiz()">🚀 Iniciar Quiz</button>
  <button onclick="showRanking()">🏆 Mostrar Ranking Atual</button>
  <div class="ranking" id="rankingPreview" style="display:none;">
    <h4>🏅 Top 3 Alunos</h4>
    <ol id="rankingListPreview"></ol>
  </div>
</div>

<!-- Quiz -->
<div class="timer" id="timerContainer" style="display:none;">⏱ Tempo restante: <span id="timer">03:00</span></div>
<div class="quiz-container" id="quiz"></div>
<button id="verifyBtn" style="display:none;" onclick="checkAnswers()">Verificar Respostas</button>

<!-- Tela final -->
<div id="endScreen" class="end-screen" style="display:none;">
  <h2>🏁 Resultado Final</h2>
  <div id="medalDisplay" class="medal"></div>
  <h3 id="scoreMessage"></h3>
  <div class="ranking">
    <h4>🏆 Ranking da Turma</h4>
    <ol id="rankingList"></ol>
  </div>
  <button onclick="restartQuiz()">🔄 Jogar Novamente</button>
</div>

<!-- Sons -->
<audio id="soundCorrect" src="https://actions.google.com/sounds/v1/cartoon/clang_and_wobble.ogg"></audio>
<audio id="soundWrong" src="https://actions.google.com/sounds/v1/cartoon/wood_plank_flicks.ogg"></audio>
<audio id="soundEnd" src="https://actions.google.com/sounds/v1/cartoon/concussive_drum_hit.ogg"></audio>

<script>
const quizData = [
  {question:"1. Qual é a primeira etapa do fluxo de recebimento de materiais em uma empresa?",
  options:["A conferência quantitativa","A entrada da nota fiscal no sistema","A triagem na portaria","O armazenamento dos produtos"],
  correct:2, explanation:"A triagem na portaria é a primeira etapa, onde se verifica documentação e agendamento da entrega."},
  {question:"2. A conferência quantitativa tem como objetivo:",
  options:["Verificar se o produto tem o mesmo preço do pedido","Checar a quantidade física recebida com a nota fiscal","Verificar o tipo de embalagem utilizada","Avaliar a qualidade do fornecedor"],
  correct:1, explanation:"Compara-se a quantidade física com o que consta na nota fiscal, garantindo precisão nas entregas."},
  {question:"3. O que caracteriza a conferência qualitativa?",
  options:["Avaliar o peso total do caminhão","Comparar o produto com o pedido e suas especificações","Calcular o valor total da nota fiscal","Registrar o recebimento no sistema ERP"],
  correct:1, explanation:"A conferência qualitativa verifica se os produtos atendem ao pedido e especificações técnicas."},
  {question:"4. Após a conferência, o que deve ser feito com a Nota Fiscal?",
  options:["Ela deve ser arquivada pelo motorista","Ela deve ser carimbada e registrada no sistema de recebimento","Ela deve ser entregue diretamente ao almoxarifado","Ela deve ser devolvida ao fornecedor"],
  correct:1, explanation:"A nota fiscal deve ser carimbada e registrada no sistema com data e número de recebimento."},
  {question:"5. Qual destas é uma prática essencial de segurança na área de recebimento?",
  options:["Permitir entrada de visitantes sem crachá","Executar tarefas sem EPI","Controlar o acesso e usar EPIs","Deixar o veículo descarregar sem supervisão"],
  correct:2, explanation:"O controle de acesso e uso de EPIs são exigências da NR-11, garantindo segurança operacional."},
  {question:"6. O que é a conferência cega?",
  options:["Quando o conferente não sabe as quantidades da nota fiscal","Quando o conferente fecha os olhos","Quando o fornecedor não envia nota fiscal","Quando o recebimento é automático"],
  correct:0, explanation:"Na conferência cega, o conferente não tem acesso à nota fiscal, evitando erros e fraudes."},
  {question:"7. Segundo Ballou (2015), qual é o objetivo principal da logística de recebimento?",
  options:["Aumentar o tempo de permanência das cargas","Assegurar materiais certos, quantidades certas e menor custo","Priorizar rapidez em detrimento da qualidade","Reduzir o número de fornecedores"],
  correct:1, explanation:"A logística de recebimento busca eficiência e precisão no fluxo de entrada de materiais."}
];

let timer, timeLeft = 180, playerName = "";

function startQuiz() {
  playerName = document.getElementById("playerName").value.trim();
  if (!playerName) { alert("Por favor, insira seu nome!"); return; }

  document.getElementById("startScreen").style.display = "none";
  document.getElementById("quiz").style.display = "block";
  document.getElementById("verifyBtn").style.display = "block";
  document.getElementById("timerContainer").style.display = "block";
  loadQuiz();
  startTimer();
}

function loadQuiz() {
  const quizContainer = document.getElementById('quiz');
  quizContainer.innerHTML = '';
  quizData.forEach((q, i) => {
    const div = document.createElement('div');
    div.classList.add('question-block');
    div.innerHTML = `<p class="question">${q.question}</p><div class="options">
      ${q.options.map((opt, j) => `<label><input type="radio" name="q${i}" value="${j}"> ${opt}</label>`).join('')}
    </div>`;
    quizContainer.appendChild(div);
  });
}

function checkAnswers() {
  clearInterval(timer);
  let score = 0;
  const soundCorrect = document.getElementById("soundCorrect");
  const soundWrong = document.getElementById("soundWrong");

  quizData.forEach((q, i) => {
    const sel = document.querySelector(`input[name="q${i}"]:checked`);
    const exp = document.createElement('div');
    if (sel && parseInt(sel.value) === q.correct) {
      score++; exp.classList.add('correct'); exp.textContent = "✅ " + q.explanation; soundCorrect.play();
    } else {
      exp.classList.add('incorrect'); exp.textContent = "❌ " + q.explanation; soundWrong.play();
    }
    document.getElementsByClassName('question-block')[i].appendChild(exp);
  });
  showResults(score);
}

function showResults(score) {
  document.getElementById('quiz').style.display = "none";
  document.getElementById('verifyBtn').style.display = "none";
  document.getElementById('timerContainer').style.display = "none";
  const medalDisplay = document.getElementById('medalDisplay');
  const scoreMessage = document.getElementById('scoreMessage');
  const soundEnd = document.getElementById('soundEnd');
  soundEnd.play();

  if (score >= 6) { medalDisplay.textContent = "🥇"; medalDisplay.className = "medal gold"; scoreMessage.textContent = `${playerName}, excelente! ${score}/7 (Medalha de Ouro)`; }
  else if (score >= 4) { medalDisplay.textContent = "🥈"; medalDisplay.className = "medal silver"; scoreMessage.textContent = `${playerName}, bom trabalho! ${score}/7 (Prata)`; }
  else { medalDisplay.textContent = "🥉"; medalDisplay.className = "medal bronze"; scoreMessage.textContent = `${playerName}, continue praticando! ${score}/7 (Bronze)`; }

  updateRanking(playerName, score);
  document.getElementById('endScreen').style.display = "block";
}

function updateRanking(name, score) {
  let ranking = JSON.parse(localStorage.getItem("ranking")) || [];
  ranking.push({ name, score });
  ranking.sort((a,b) => b.score - a.score);
  ranking = ranking.slice(0, 3);
  localStorage.setItem("ranking", JSON.stringify(ranking));
  renderRanking(ranking);
}

function renderRanking(ranking) {
  const list = document.getElementById('rankingList');
  list.innerHTML = ranking.map(r => `<li><strong>${r.name}</strong> — ${r.score} acertos</li>`).join('');
}

function showRanking() {
  const ranking = JSON.parse(localStorage.getItem("ranking")) || [];
  const previewDiv = document.getElementById("rankingPreview");
  const list = document.getElementById("rankingListPreview");
  if (ranking.length === 0) {
    list.innerHTML = "<li>Nenhum resultado registrado ainda.</li>";
  } else {
    list.innerHTML = ranking.map(r => `<li><strong>${r.name}</strong> — ${r.score} acertos</li>`).join('');
  }
  previewDiv.style.display = "block";
}

function restartQuiz() {
  document.getElementById('endScreen').style.display = "none";
  document.getElementById('startScreen').style.display = "block";
  document.getElementById('playerName').value = "";
  timeLeft = 180;
  clearInterval(timer);
}

function startTimer() {
  const timerEl = document.getElementById('timer');
  clearInterval(timer);
  timer = setInterval(() => {
    const m = Math.floor(timeLeft / 60);
    const s = timeLeft % 60;
    timerEl.textContent = `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
    timeLeft--;
    if (timeLeft < 0) { clearInterval(timer); checkAnswers(); }
  }, 1000);
}
</script>
</body>
</html>
