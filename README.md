<html>

<head>
<meta http-equiv=Content-Type content="text/html; charset=unicode">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<title>Quiz Interativo - Fluxo do Recebimento</title>
<style>
<!--
@keyframes bounceIn {
    0% { transform: scale(0.3); opacity: 0; }
    50% { transform: scale(1.1); opacity: 1; }
    70% { transform: scale(0.9); }
    100% { transform: scale(1); }
  }
body
	{background: linear-gradient(180deg, #e7f0fd, #f5f7fa);}
h1
	{border-radius: 10px;
	box-shadow: 0 4px 10px rgba(0,0,0,0.2);}
.START-SCREEN
	{border-radius: 15px;
	box-shadow: 0 4px 15px rgba(0,0,0,0.1);
	animation: fadeInUp 1s ease;}
.END-SCREEN
	{border-radius: 15px;
	box-shadow: 0 4px 15px rgba(0,0,0,0.1);
	animation: fadeInUp 1s ease;}
.START-SCREEN input
	{border-radius: 8px;}
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
.QUIZ-CONTAINER
	{border-radius: 15px;
	box-shadow: 0 4px 15px rgba(0,0,0,0.1);}
.OPTIONS label
	{cursor: pointer;}
.CORRECT
	{border-radius: 6px;}
.INCORRECT
	{border-radius: 6px;}
.MEDAL
	{animation: bounceIn 1s ease;}
.RANKING
	{border-radius: 10px;}

 /* Font Definitions */
 @font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:"Aptos Display";}
@font-face
	{font-family:"Segoe UI Emoji";
	panose-1:2 11 5 2 4 2 4 2 2 3;}
@font-face
	{font-family:"Segoe UI";
	panose-1:2 11 5 2 4 2 4 2 2 3;}
@font-face
	{font-family:"Segoe UI Symbol";
	panose-1:2 11 5 2 4 2 4 2 2 3;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin:0cm;
	font-size:12.0pt;
	font-family:"Times New Roman",serif;}
h1
	{mso-style-link:"Título 1 Char";
	margin-right:0cm;
	margin-left:0cm;
	text-align:center;
	background:#005FA3;
	font-size:24.0pt;
	font-family:"Times New Roman",serif;
	color:white;
	font-weight:bold;}
h2
	{mso-style-link:"Título 2 Char";
	margin-right:0cm;
	margin-left:0cm;
	font-size:18.0pt;
	font-family:"Times New Roman",serif;
	font-weight:bold;}
p
	{margin-right:0cm;
	margin-left:0cm;
	font-size:12.0pt;
	font-family:"Times New Roman",serif;}
span.Ttulo1Char
	{mso-style-name:"Título 1 Char";
	mso-style-link:"Título 1";
	font-family:"Aptos Display",sans-serif;
	color:#0F4761;}
span.Ttulo2Char
	{mso-style-name:"Título 2 Char";
	mso-style-link:"Título 2";
	font-family:"Aptos Display",sans-serif;
	color:#0F4761;}
.MsoChpDefault
	{font-size:10.0pt;}
@page WordSection1
	{size:595.3pt 841.9pt;
	margin:70.85pt 3.0cm 70.85pt 3.0cm;}
div.WordSection1
	{page:WordSection1;}
-->
</style>

<meta charset=UTF-8>
<meta name=viewport content="width=device-width, initial-scale=1.0">
</head>

<body lang=PT-BR style='word-wrap:break-word'>

<div class=WordSection1>

<h1><span style='font-family:"Segoe UI",sans-serif'>Quiz Interativo – Fluxo do
Recebimento</span></h1>

<!-- Tela inicial -->

<div style='margin-top:30.0pt;margin-bottom:30.0pt' id=startScreen>

<h2 align=center style='text-align:center;background:white'><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#333333'>&#129504;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Bem-vindo(a) ao
Desafio do Conferente!</span></h2>

<p align=center style='text-align:center;background:white'><span
style='font-family:"Segoe UI",sans-serif;color:#333333'>Teste seus
conhecimentos sobre o <strong><span style='font-family:"Segoe UI",sans-serif'>Fluxo
do Recebimento</span></strong>.<br>
<br>
</span><span style='font-family:"Segoe UI Symbol",sans-serif;color:#333333'>⏱</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Você terá <strong><span
style='font-family:"Segoe UI",sans-serif'>3 minutos</span></strong> para
responder <strong><span style='font-family:"Segoe UI",sans-serif'>7 perguntas</span></strong>.<br>
</span><span style='font-family:"Segoe UI Emoji",sans-serif;color:#333333'>&#128161;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Cada resposta traz uma
explicação didática.<br>
<br>
Digite seu nome para começar: </span></p>

<input type=text id=playerName placeholder="Digite seu nome aqui">

<p class=MsoNormal align=center style='text-align:center;background:white'><span
style='font-family:"Segoe UI",sans-serif;color:#333333'><br>
</span><span style='font-family:"Segoe UI Emoji",sans-serif;color:#333333'><button onclick="startQuiz()">&#128640;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Iniciar Quiz</button> </span><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#333333'><button onclick="showRanking()">&#127942;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Mostrar Ranking Atual</button>
</span></p>

<div style='margin-top:15.0pt' id=rankingPreview>

<p class=MsoNormal align=center style='text-align:center;background:#EEF6FF'><b><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#005FA3;display:none'>&#127941;</span></b><b><span
style='font-family:"Segoe UI",sans-serif;color:#005FA3;display:none'> Top 3
Alunos</span></b></p>

<ul id="rankingListPreview"></ul>

</div>

</div>

<!-- Quiz -->

<div style='margin-top:7.5pt; display:none;' id=quiz></div>

<div style='margin-top:7.5pt' id=timerContainer>

<p class=MsoNormal align=center style='text-align:center'><b><span
style='font-size:15.0pt;font-family:"Segoe UI Symbol",sans-serif;color:#005FA3;
display:none'>⏱</span></b><b><span style='font-size:15.0pt;font-family:"Segoe UI",sans-serif;
color:#005FA3;display:none'> Tempo restante: <span id=timer>03:00</span></span></b></p>

</div>

<p class=MsoNormal><span style='font-family:"Segoe UI",sans-serif;color:#333333'><button id="verifyBtn" style="display:none;" onclick="checkAnswers()">Verificar
Respostas</button> </span></p>

<!-- Tela final -->

<div style='margin-top:30.0pt;margin-bottom:30.0pt; display:none;' id=endScreen>

<h2 align=center style='text-align:center;background:white'><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#333333;display:none'>&#127937;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333;display:none'> Resultado
Final</span></h2>

<div style='margin-top:15.0pt'>

<div align="center" id="medalDisplay" style="font-size: 60px;"></div>
<div align="center" id="scoreMessage" style="font-size: 22px; margin: 12px 0;"></div>

<p class=MsoNormal align=center style='text-align:center;background:#EEF6FF'><b><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#005FA3;'>🏆</span></b><b><span
style='font-family:"Segoe UI",sans-serif;color:#005FA3;'> Ranking
da Turma</span></b></p>
<ul id="rankingList"></ul>

</div>

<p class=MsoNormal align=center style='text-align:center;background:white'><span
style='font-family:"Segoe UI Emoji",sans-serif;color:#333333'><button onclick="restartQuiz()">&#128260;</span><span
style='font-family:"Segoe UI",sans-serif;color:#333333'> Jogar
Novamente</button> </span></p>

</div>

<p class=MsoNormal><script>
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
</script><!-- Sons --><audio id="soundCorrect" src="https://actions.google.com/sounds/v1/cartoon/clang_and_wobble.ogg"></audio><audio id="soundWrong" src="https://actions.google.com/sounds/v1/cartoon/wood_plank_flicks.ogg"></audio><audio id="soundEnd" src="https://actions.google.com/sounds/v1/cartoon/concussive_drum_hit.ogg"></audio>&nbsp;</p>

</div>

</body>

</html>
