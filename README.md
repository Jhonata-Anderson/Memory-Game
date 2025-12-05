# 🃏 Jogo da Memória (Memory Game)

Uma implementação clássica e visualmente agradável do jogo da memória, desenvolvida com **HTML, CSS e JavaScript**.



---

## ✨ Visão Geral do Jogo

O **Jogo da Memória** desafia o jogador a encontrar e emparelhar todos os ícones idênticos no tabuleiro 4x4.

* **Objetivo:** Virar duas cartas por vez. Se os ícones forem iguais, elas permanecem abertas. Encontre todos os 8 pares para vencer.
* **Design:** Estilo moderno e dinâmico, utilizando a fonte **Press Start 2P** e com transições de giro **3D** nas cartas.
* **Controle:** O botão **RESET GAME** permite reiniciar o jogo a qualquer momento.

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Função no Projeto |
| :--- | :--- |
| **HTML5** | Estrutura da página (`.game`, `.container`). |
| **CSS3** | Estilização, layout Flexbox, animações de giro **3D** (`transform: rotateY`) e animação de `hover`. |
| **JavaScript** | Lógica principal: embaralhamento, **gerenciamento de cliques** e **verificação de pares**. |

---

## ⚙️ Funcionalidades e Lógica (JavaScript)

A lógica central do jogo reside no arquivo `src/scripts/engine.js`:

### 1. Inicialização e Embaralhamento

* Define-se um array de **8 pares de emojis**.
* O array é **embaralhado** usando `emojis.sort(() => (Math.random() > 0.5) ? 2: -1);` para garantir que as cartas estejam em posições aleatórias.
* O *loop* de criação anexa dinamicamente os elementos (`div.item`) ao contêiner `.game` no HTML, atribuindo um emoji e o evento `onclick` a cada um.

### 2. Gerenciamento de Cliques e Tempo

A função `handleClick()` gerencia a abertura das cartas:

* Permite que no máximo **duas cartas** estejam abertas simultaneamente (`openCards.length < 2`).
* Adiciona a classe `.boxOpen` à carta clicada, ativando a animação de giro.
* Quando duas cartas estão abertas, a função `checkMatch` é chamada após um atraso de **500ms** (`setTimeout`) para permitir que o usuário visualize as cartas antes da verificação.

### 3. Verificação de Pares (`checkMatch`)

Esta função compara as duas cartas abertas:

* **Acerto:** Se `openCards[0].innerHTML === openCards[1].innerHTML`, a classe `.boxMatch` é adicionada, mantendo as cartas permanentemente viradas.
* **Erro:** Caso contrário, a classe `.boxOpen` é removida, e as cartas são viradas para baixo novamente.
* **Vitória:** A condição de vitória é verificada: se o número total de elementos com a classe `.boxMatch` for igual ao total de cartas, o jogo é encerrado com um alerta de vitória.

---

## 👨‍💻 Expert

<p>
    <img 
      align=left 
      margin=10 
      width=80 
      src="https://avatars.githubusercontent.com/u/168501597?v=4"
    />
    <p>&nbsp&nbsp&nbspJhonata Anderson<br>
    &nbsp&nbsp&nbsp
    <a href="https://github.com/Jhonata-Anderson">
    GitHub</a>&nbsp;|&nbsp;
    <a href="https://www.linkedin.com/in/jhonata-anderson/">LinkedIn</a>
&nbsp;|&nbsp;
</p>
<br/><br/>
<p>Feito com 💙 como parte da Trilha de CSS da Digital Innovation One (DIO).</p>
