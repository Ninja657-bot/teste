<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz Sekiro</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            min-height: 100vh;
            font-family: Arial, Helvetica, sans-serif;
            background:
                radial-gradient(circle at top, #292929 0%, #111 45%, #050505 100%);
            color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 720px;
            background: rgba(20, 20, 20, 0.97);
            border: 1px solid #383838;
            border-radius: 18px;
            padding: 35px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.7);
        }

        .inicio,
        .resultado {
            text-align: center;
        }

        .logo {
            font-size: 3.2rem;
            font-weight: bold;
            letter-spacing: 6px;
            color: #d62828;
            margin-bottom: 10px;
        }

        .subtitulo {
            color: #aaa;
            font-size: 1rem;
            margin-bottom: 30px;
        }

        .descricao {
            color: #bbb;
            line-height: 1.7;
            margin: 0 auto 30px;
            max-width: 560px;
        }

        .aviso {
            background: #191919;
            border: 1px solid #333;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 25px;
            color: #999;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .botao {
            display: inline-block;
            padding: 14px 32px;
            border: none;
            border-radius: 9px;
            background: #b82020;
            color: white;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.25s ease;
        }

        .botao:hover {
            background: #d32f2f;
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(200, 30, 30, 0.25);
        }

        .cabecalho {
            text-align: center;
            margin-bottom: 30px;
        }

        .cabecalho h1 {
            font-size: 2rem;
            color: #d62828;
            letter-spacing: 2px;
            margin-bottom: 8px;
        }

        .cabecalho p {
            color: #999;
        }

        .progresso-area {
            margin-bottom: 25px;
        }

        .informacoes-progresso {
            display: flex;
            justify-content: space-between;
            color: #aaa;
            font-size: 0.9rem;
            margin-bottom: 8px;
        }

        .barra-fundo {
            width: 100%;
            height: 7px;
            background: #303030;
            border-radius: 10px;
            overflow: hidden;
        }

        .barra-progresso {
            width: 10%;
            height: 100%;
            background: #c62828;
            border-radius: 10px;
            transition: width 0.4s ease;
        }

        .pergunta {
            font-size: 1.35rem;
            line-height: 1.5;
            margin-bottom: 25px;
        }

        .alternativas {
            display: grid;
            gap: 13px;
        }

        .alternativa {
            width: 100%;
            padding: 17px 18px;
            border: 1px solid #3b3b3b;
            border-radius: 11px;
            background: #191919;
            color: #eee;
            text-align: left;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.25s ease;
        }

        .alternativa:hover:not(:disabled) {
            background: #252525;
            border-color: #777;
            transform: translateY(-2px);
        }

        .alternativa:disabled {
            cursor: default;
        }

        .alternativa.correta {
            background: #173d28;
            border-color: #35a866;
            color: #7ff0a9;
        }

        .alternativa.errada {
            background: #451b1b;
            border-color: #d84b4b;
            color: #ff8585;
        }

        .feedback {
            min-height: 25px;
            margin-top: 20px;
            color: #bbb;
            text-align: center;
            line-height: 1.5;
            font-size: 0.95rem;
        }

        .botao-proxima {
            display: block;
            margin: 22px auto 0;
            padding: 13px 28px;
            border: none;
            border-radius: 9px;
            background: #b82020;
            color: white;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.25s ease;
        }

        .botao-proxima:hover {
            background: #d32f2f;
            transform: translateY(-2px);
        }

        .pontuacao-final {
            font-size: 4rem;
            font-weight: bold;
            margin: 15px 0;
        }

        .resultado h2 {
            font-size: 2rem;
            color: #d62828;
            margin-bottom: 15px;
        }

        .mensagem-resultado {
            color: #aaa;
            line-height: 1.6;
        }

        .classificacao {
            margin: 25px 0;
            padding: 18px;
            background: #191919;
            border-radius: 10px;
            border: 1px solid #333;
        }

        .classificacao h3 {
            color: #eee;
            margin-bottom: 8px;
        }

        .classificacao p {
            color: #999;
            line-height: 1.5;
        }

        .oculto {
            display: none;
        }

        @keyframes aparecer {
            from {
                opacity: 0;
                transform: translateY(12px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .animar {
            animation: aparecer 0.45s ease;
        }

        @media (max-width: 600px) {
            .container {
                padding: 25px 18px;
            }

            .logo {
                font-size: 2.4rem;
                letter-spacing: 4px;
            }

            .cabecalho h1 {
                font-size: 1.7rem;
            }

            .pergunta {
                font-size: 1.15rem;
            }

            .alternativa {
                padding: 15px;
            }

            .pontuacao-final {
                font-size: 3.2rem;
            }
        }
    </style>
</head>

<body>

    <main class="container">

        <!-- MENU INICIAL -->
        <section id="inicio" class="inicio animar">

            <div class="logo">SEKIRO</div>

            <p class="subtitulo">
                Sombras Morrem Duas Vezes
            </p>

            <p class="descricao">
                Teste seus conhecimentos sobre a história, personagens,
                mecânicas e mundo de Sekiro: Shadows Die Twice.
            </p>

            <div class="aviso">
                O quiz possui <strong>10 perguntas</strong>.
                Cada pergunta possui quatro alternativas e apenas uma resposta correta.
            </div>

            <button class="botao" onclick="iniciarQuiz()">
                Iniciar Quiz
            </button>

        </section>


        <!-- QUIZ -->
        <section id="quiz" class="oculto">

            <header class="cabecalho">
                <h1>SEKIRO</h1>
                <p>Teste seus conhecimentos</p>
            </header>

            <div class="progresso-area">

                <div class="informacoes-progresso">
                    <span id="numero-pergunta">Pergunta 1 de 10</span>
                    <span id="pontuacao">0 pontos</span>
                </div>

                <div class="barra-fundo">
                    <div id="barra-progresso" class="barra-progresso"></div>
                </div>

            </div>

            <div id="pergunta" class="pergunta"></div>

            <div id="alternativas" class="alternativas"></div>

            <div id="feedback" class="feedback"></div>

            <button id="botao-proxima" class="botao-proxima oculto">
                Próxima pergunta
            </button>

        </section>


        <!-- RESULTADO -->
        <section id="resultado" class="resultado oculto">

            <h2>O duelo terminou.</h2>

            <div class="pontuacao-final">
                <span id="pontuacao-final">0</span>/10
            </div>

            <p id="mensagem-resultado" class="mensagem-resultado"></p>

            <div class="classificacao">

                <h3 id="titulo-classificacao"></h3>

                <p id="descricao-classificacao"></p>

            </div>

            <button class="botao" onclick="reiniciarQuiz()">
                Jogar novamente
            </button>

        </section>

    </main>


    <script>

        const perguntas = [

            {
                pergunta: "Qual é o verdadeiro nome do protagonista de Sekiro?",
                alternativas: [
                    "Lobo",
                    "Kuro",
                    "Coruja",
                    "Genichiro"
                ],
                correta: 0,
                explicacao:
                    "O protagonista é conhecido como Lobo, um shinobi que jurou proteger Kuro."
            },

            {
                pergunta: "Quem é o senhor que Lobo jurou proteger?",
                alternativas: [
                    "Isshin Ashina",
                    "Kuro",
                    "Coruja",
                    "Genichiro Ashina"
                ],
                correta: 1,
                explicacao:
                    "Kuro é o Herdeiro Divino e o senhor protegido por Lobo."
            },

            {
                pergunta: "Qual é a principal mecânica utilizada para derrotar a defesa dos inimigos?",
                alternativas: [
                    "Resistência",
                    "Sangramento",
                    "Postura",
                    "Energia"
                ],
                correta: 2,
                explicacao:
                    "A Postura é fundamental em Sekiro. Ao quebrá-la, Lobo pode realizar um Golpe Mortal."
            },

            {
                pergunta: "Qual é o principal objetivo de Lobo e Kuro durante grande parte da história?",
                alternativas: [
                    "Conquistar o Castelo de Ashina e dominar o Japão",
                    "Romper a imortalidade de Kuro e encerrar o ciclo da imortalidade",
                    "Destruir todos os shinobi e abandonar Ashina",
                    "Servir a Genichiro e fortalecer o exército de Ashina"
                ],
                correta: 1,
                explicacao:
                    "Lobo e Kuro procuram uma forma de romper a herança da imortalidade e acabar com o ciclo ligado ao sangue do Herdeiro Divino."
            },

            {
                pergunta: "Quem é o pai adotivo de Lobo e um dos grandes shinobi da história?",
                alternativas: [
                    "Genichiro Ashina",
                    "Isshin Ashina",
                    "Coruja",
                    "O Escultor"
                ],
                correta: 2,
                explicacao:
                    "Coruja é o pai adotivo de Lobo e uma das figuras mais importantes de sua história."
            },

            {
                pergunta: "Qual é o nome da região onde fica o Castelo de Ashina?",
                alternativas: [
                    "Hirata",
                    "Vale Submerso",
                    "Ashina",
                    "Palácio da Fonte"
                ],
                correta: 2,
                explicacao:
                    "O Castelo de Ashina está localizado na região de Ashina e é um dos principais locais do jogo."
            },

            {
                pergunta: "Quem é o líder do clã Ashina e o lendário guerreiro conhecido como Espada Divina?",
                alternativas: [
                    "Genichiro Ashina",
                    "Isshin Ashina",
                    "Coruja",
                    "Lobo"
                ],
                correta: 1,
                explicacao:
                    "Isshin Ashina é o lendário fundador e líder do clã Ashina."
            },

            {
                pergunta: "Qual ferramenta permite que Lobo utilize um gancho para alcançar locais elevados?",
                alternativas: [
                    "Prótese Shinobi",
                    "Lança de Chamas",
                    "Machado Carregado",
                    "Leque Divino"
                ],
                correta: 0,
                explicacao:
                    "A Prótese Shinobi possui o gancho, permitindo que Lobo alcance locais elevados e atravesse grandes distâncias."
            },

            {
                pergunta: "Quem está diretamente relacionado à criação e ao aprimoramento da Prótese Shinobi?",
                alternativas: [
                    "Emma",
                    "O Escultor",
                    "Genichiro",
                    "Kuro"
                ],
                correta: 1,
                explicacao:
                    "O Escultor é responsável por modificar e aprimorar a Prótese Shinobi de Lobo."
            },

            {
                pergunta: "O que acontece quando Lobo quebra completamente a Postura de um inimigo?",
                alternativas: [
                    "O inimigo recupera toda a vida",
                    "Lobo perde sua Prótese Shinobi",
                    "Lobo pode executar um Golpe Mortal",
                    "O inimigo fica permanentemente invencível"
                ],
                correta: 2,
                explicacao:
                    "Quando a Postura de um inimigo é quebrada, Lobo pode realizar um Golpe Mortal."
            }

        ];


        let perguntaAtual = 0;
        let pontos = 0;
        let respondeu = false;


        const elementoPergunta =
            document.getElementById("pergunta");

        const elementoAlternativas =
            document.getElementById("alternativas");

        const elementoFeedback =
            document.getElementById("feedback");

        const botaoProxima =
            document.getElementById("botao-proxima");

        const numeroPergunta =
            document.getElementById("numero-pergunta");

        const elementoPontuacao =
            document.getElementById("pontuacao");

        const barraProgresso =
            document.getElementById("barra-progresso");


        function iniciarQuiz() {

            document.getElementById("inicio")
                .classList.add("oculto");

            document.getElementById("quiz")
                .classList.remove("oculto");

            carregarPergunta();
        }


        function carregarPergunta() {

            respondeu = false;

            const pergunta =
                perguntas[perguntaAtual];

            numeroPergunta.textContent =
                `Pergunta ${perguntaAtual + 1} de ${perguntas.length}`;

            elementoPontuacao.textContent =
                `${pontos} ${pontos === 1 ? "ponto" : "pontos"}`;

            barraProgresso.style.width =
                `${((perguntaAtual + 1) / perguntas.length) * 100}%`;

            elementoPergunta.textContent =
                pergunta.pergunta;

            elementoAlternativas.innerHTML = "";

            elementoFeedback.textContent = "";

            botaoProxima.classList.add("oculto");

            pergunta.alternativas.forEach(
                (alternativa, indice) => {

                    const botao =
                        document.createElement("button");

                    botao.className =
                        "alternativa";

                    botao.textContent =
                        alternativa;

                    botao.addEventListener(
                        "click",
                        () => selecionarResposta(
                            indice,
                            botao
                        )
                    );

                    elementoAlternativas
                        .appendChild(botao);
                }
            );
        }


        function selecionarResposta(
            indiceSelecionado,
            botaoSelecionado
        ) {

            if (respondeu) {
                return;
            }

            respondeu = true;

            const pergunta =
                perguntas[perguntaAtual];

            const botoes =
                document.querySelectorAll(".alternativa");

            botoes.forEach(botao => {
                botao.disabled = true;
            });


            if (
                indiceSelecionado ===
                pergunta.correta
            ) {

                botaoSelecionado
                    .classList.add("correta");

                pontos++;

                elementoFeedback.textContent =
                    "Resposta correta! " +
                    pergunta.explicacao;

            } else {

                botaoSelecionado
                    .classList.add("errada");

                botoes[pergunta.correta]
                    .classList.add("correta");

                elementoFeedback.textContent =
                    "Resposta incorreta. " +
                    pergunta.explicacao;
            }


            elementoPontuacao.textContent =
                `${pontos} ${pontos === 1 ? "ponto" : "pontos"}`;


            botaoProxima
                .classList.remove("oculto");


            if (
                perguntaAtual ===
                perguntas.length - 1
            ) {

                botaoProxima.textContent =
                    "Ver resultado";
            }
        }


        botaoProxima.addEventListener(
            "click",
            () => {

                perguntaAtual++;

                if (
                    perguntaAtual <
                    perguntas.length
                ) {

                    carregarPergunta();

                } else {

                    mostrarResultado();
                }
            }
        );


        function mostrarResultado() {

            document.getElementById("quiz")
                .classList.add("oculto");

            document.getElementById("resultado")
                .classList.remove("oculto");


            document.getElementById("pontuacao-final")
                .textContent = pontos;


            let mensagem;
            let titulo;
            let descricao;


            if (pontos === 10) {

                mensagem =
                    "Você domina os caminhos de Ashina.";

                titulo =
                    "Mestre Shinobi";

                descricao =
                    "Nenhum golpe foi desperdiçado. Seu conhecimento sobre Sekiro é digno de um verdadeiro shinobi.";

            } else if (pontos >= 8) {

                mensagem =
                    "Você conhece profundamente a história de Ashina.";

                titulo =
                    "Shinobi Veterano";

                descricao =
                    "Poucos segredos escapam ao seu conhecimento. Você está muito próximo do domínio completo.";

            } else if (pontos >= 6) {

                mensagem =
                    "Seu treinamento deu bons resultados.";

                titulo =
                    "Shinobi Experiente";

                descricao =
                    "Você conhece bem o mundo de Sekiro, mas ainda existem alguns detalhes para dominar.";

            } else if (pontos >= 4) {

                mensagem =
                    "A jornada ainda está apenas começando.";

                titulo =
                    "Shinobi em Treinamento";

                descricao =
                    "Você conhece alguns dos segredos de Ashina, mas ainda precisa aprimorar seu conhecimento.";

            } else {

                mensagem =
                    "Você foi derrotado... por enquanto.";

                titulo =
                    "Aprendiz Shinobi";

                descricao =
                    "Até mesmo os maiores guerreiros precisam começar de algum lugar. Continue treinando.";
            }


            document.getElementById(
                "mensagem-resultado"
            ).textContent = mensagem;


            document.getElementById(
                "titulo-classificacao"
            ).textContent = titulo;


            document.getElementById(
                "descricao-classificacao"
            ).textContent = descricao;
        }


        function reiniciarQuiz() {

            perguntaAtual = 0;
            pontos = 0;

            document.getElementById("resultado")
                .classList.add("oculto");

            document.getElementById("inicio")
                .classList.remove("oculto");

            botaoProxima.textContent =
                "Próxima pergunta";
        }

    </script>

</body>
</html>
