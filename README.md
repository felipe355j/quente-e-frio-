Jogo Quente e Frio com p5.js: Como Funciona e Como Jogar

"Quente e Frio" é aquele jogo simples em que você tenta adivinhar a localização de algo com base em dicas de proximidade. O objetivo é simples: quanto mais perto você chega, mais quente fica a dica.

Agora, imagina colocar isso no mundo digital com p5.js, que é uma biblioteca em JavaScript para fazer desenhos e interações em tempo real. Vamos montar um jogo "Quente e Frio" de forma simples usando a biblioteca, e ainda vamos deixar tudo visualmente legal.

O Básico do Jogo em p5.js
Visualização do Jogo: O jogo pode ser bem simples. Vamos ter um fundo e um ponto aleatório que você precisa encontrar. Quando você clicar na tela, o jogo vai te dizer se está "quente", "morno" ou "frio", baseado na distância entre seu clique e o ponto.

Como Funciona:

O jogo coloca um ponto aleatório na tela, que você não pode ver.

Quando você clica em um local, o jogo calcula a distância entre o seu clique e o ponto e te dá um feedback: "quente" se estiver perto ou "frio" se estiver longe.

A ideia é você ir clicando até acertar o ponto, e, claro, o jogo vai te dando dicas para te guiar.

Tecnologias Envolvidas:

p5.js: A biblioteca usada para fazer a parte gráfica e as interações.

JavaScript: Para programar toda a lógica por trás do jogo.

HTML/CSS: Para estruturar e estilizar a página onde o jogo vai acontecer.

Exemplo de Código Simples
Aqui está o código para um jogo básico de Quente e Frio:

javascript
Copiar
Editar
let targetX, targetY;

function setup() {
  createCanvas(400, 400);
  targetX = random(width);  // Ponto alvo aleatório
  targetY = random(height); // Ponto alvo aleatório
}

function draw() {
  background(220);
  
  // Desenho invisível do ponto alvo
  fill(255, 0, 0);
  noStroke();
  ellipse(targetX, targetY, 10, 10);
  
  // Pega a posição do mouse
  let d = dist(mouseX, mouseY, targetX, targetY);
  
  // Verifica a proximidade
  if (d < 20) {
    fill(255, 0, 0);
    textSize(32);
    text("Quente!", 10, height - 10);
  } else if (d < 50) {
    fill(255, 165, 0);
    textSize(32);
    text("Morno!", 10, height - 10);
  } else {
    fill(0, 0, 255);
    textSize(32);
    text("Frio!", 10, height - 10);
  }
}

function mousePressed() {
  let d = dist(mouseX, mouseY, targetX, targetY);
  
  if (d < 10) {
    alert("Você encontrou o ponto! Parabéns!");
    // Reposiciona o ponto alvo
    targetX = random(width);
    targetY = random(height);
  }
}
Como Jogar:
Clique em qualquer lugar da tela. A cada clique, o jogo te avisa se está "quente", "morno" ou "frio".

A ideia é chegar o mais perto possível do ponto vermelho.

Quando você clicar bem no ponto, o jogo diz "Você encontrou o ponto!" e o jogo reinicia com um novo ponto aleatório.

Explicação do Código:
O ponto vermelho (targetX, targetY) é a posição secreta que o jogador precisa encontrar.

A função dist() calcula a distância entre o seu clique e o ponto. Dependendo da proximidade, o jogo muda a mensagem que aparece na tela, indicando "quente", "morno" ou "frio".

O feedback visual é dado com cores: vermelho para "quente", laranja para "morno" e azul para "frio".

Quando você clica perto o suficiente do ponto (distância menor que 10), o jogo reinicia com um novo ponto aleatório.

Tecnologias Utilizadas:
p5.js para desenhar e gerenciar interações gráficas.

JavaScript para a lógica do jogo.

HTML/CSS para estruturar e estilizar a página (se necessário).
