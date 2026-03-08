# 🎓 Guia Completo: Construindo Seu Portfólio com JavaScript Vanilla

> **Para quem é este guia?**  
> Este material foi criado para você que já tem noções básicas de lógica de programação e quer aprender desenvolvimento web **fazendo**. Em vez de apenas copiar código, você vai **pensar**, **experimentar** e **construir** seu próprio portfólio do zero.

---

## 📚 O que você vai aprender

- ✅ Estruturar uma página web com **HTML5 semântico**
- ✅ Estilizar com **CSS moderno** (Flexbox, variáveis, animações)
- ✅ Manipular o DOM com **JavaScript vanilla**
- ✅ Transformar dados em HTML com **`.map()`**
- ✅ Ordenar, filtrar e condicionar exibição de dados
- ✅ Criar navegação dinâmica (carrossel)
- ✅ Publicar seu site no **GitHub Pages** (de graça!)
- ✅ Configurar **domínio customizado** (opcional)

---

## 🛠️ Pré-requisitos

- Noções básicas de lógica (variáveis, loops, condicionais)
- Editor de código (VS Code, Sublime, qualquer um)
- Navegador moderno (Chrome, Firefox, Edge)
- Vontade de aprender!

---

## 📂 Estrutura do Projeto

No final, seu projeto terá esta estrutura:

```
meu-portfolio/
├── index.html       (estrutura da página)
├── style.css        (estilos visuais)
├── script.js        (lógica JavaScript)
└── imagens/
    └── foto.jpg     (sua foto de perfil)
```

---

## 📋 Checklist do Projeto

Use isso para acompanhar seu progresso. Marque cada item conforme avançar nas fases.

### Fase 1 — HTML Estático (esqueleto com conteúdo)

- [x] Criar `index.html` com `<!DOCTYPE html>`, `<head>` e `<body>`
- [x] Configurar `<head>`: charset, viewport, title e link para o CSS
- [x] Criar `<header>` com `<img>` (foto), `<h1>` (nome) e `<p>` (subtítulo)
- [x] Criar `<section id="sobre">` com parágrafos de apresentação
- [ ] Criar `<section id="experiencias">`: 2 blocos com `<h3>`, empresa, período e descrição
- [ ] Criar `<section id="skills">`: lista de tecnologias em `<span>`
- [ ] Criar `<section id="projetos">`: 2 blocos com imagem, título, descrição e link `<a>`
- [ ] Criar `<footer id="contato">` com links de email, GitHub e LinkedIn
- [ ] Adicionar `<script src="script.js">` no final do `<body>`
- [ ] Criar pasta `imagens/` e adicionar foto de perfil e imagens dos projetos

### Fase 2 — CSS (seção por seção: adicionar classe no HTML → estilizar no CSS)

- [x] Criar `style.css` com reset (`*`) e variáveis no `:root` (cores, espaçamentos)
- [x] Adicionar `class="container"` nas `<div>` internas → estilizar centralização e largura máxima no `body`
- [x] Adicionar `class="header"` no `<header>` → estilizar com gradiente, foto circular (`.foto-perfil`) e tipografia
- [x] Adicionar `class` nas seções gerais → definir padding e estilizar `h2` com linha decorativa via `::after`
- [x] Adicionar `class="sobre"` → estilizar fundo branco e parágrafos centralizados
- [ ] Adicionar `class="card-experiencia"` e `class="badge atual/passada"` → borda lateral colorida, sombra e hover com `translateY`
- [ ] Adicionar `class="skills"` na section e `class="skill-tag"` nos `<span>` → Flexbox com `flex-wrap` e hover com `scale`
- [ ] Adicionar `class="card-projeto"`, `class="projeto-img"` e `class="btn"` → overflow hidden, imagem, botão estilizado com hover
- [ ] Adicionar `class="contato"` no `<footer>` → fundo colorido, links com borda e hover invertido
- [ ] Adicionar media query `@media (max-width: 768px)` para responsividade mobile

### Fase 3 — JavaScript Básico

- [ ] Criar `script.js` com array `experiencias` (objetos com tipo, cargo, empresa, período, descrição)
- [ ] Substituir cards estáticos no HTML por `<div id="container-experiencias"></div>`
- [ ] Usar `document.getElementById()` para capturar o container
- [ ] Usar `.map()` + template literals para transformar cada objeto em string HTML
- [ ] Usar `.join('')` para unir o array de strings e injetar com `.innerHTML`

### Fase 4 — JavaScript Avançado

- [ ] Ordenar experiências com `.sort()` (atual primeiro)
- [ ] Filtrar experiências com `.filter()` (ex: só atuais ou só passadas)
- [ ] Usar operador ternário para exibição condicional do badge
- [ ] Usar o índice do `.map()` para alternar estilos ou numerar cards

### Fase 5 — Aplicação Prática

- [ ] Criar array `skills` e gerar as tags dinamicamente com `.map()`
- [ ] Criar array `projetos` e gerar os cards dinamicamente com `.map()`
- [ ] Remover todos os cards estáticos do HTML (seções 100% dinâmicas)
- [ ] Refatorar: separar dados, funções de renderização e seletores do DOM

### Apêndice A — Carrossel de Experiências

- [ ] Adicionar botões de navegação (anterior/próximo) no HTML
- [ ] Controlar índice da experiência visível com variável de estado
- [ ] Adicionar event listeners nos botões para atualizar o índice e re-renderizar
- [ ] Tratar bordas (não avançar além do último, não voltar além do primeiro)

### Apêndice B — Deploy no GitHub Pages

- [ ] Criar repositório no GitHub
- [ ] Fazer o primeiro `git add`, `git commit` e `git push`
- [ ] Ativar GitHub Pages nas configurações (branch `main`, pasta raiz)
- [ ] Acessar o link gerado e confirmar que o site está online
- [ ] (Opcional) Configurar domínio customizado

### Apêndice C — Dark Mode _(bônus)_

- [ ] Criar botão toggle no HTML
- [ ] Adicionar variáveis de tema escuro no CSS (classe `.dark` no `<body>`)
- [ ] Detectar preferência do sistema com `prefers-color-scheme` no JS
- [ ] Usar `localStorage` para salvar e restaurar a preferência do usuário
- [ ] Adicionar event listener no botão para alternar a classe de tema

---

# 🏗️ FASE 1: HTML Estático - A Estrutura

> **Pergunta Inicial**: Se você fosse apresentar-se profissionalmente em uma página, quais informações mostraria?

Provavelmente você pensou em: foto, nome, descrição, experiências, habilidades, projetos e formas de contato. É exatamente isso que vamos construir!

## 1.1 - Criando o Esqueleto HTML

Crie um arquivo chamado `index.html` e vamos começar:

```html
<!DOCTYPE html>
<!-- 
  DOCTYPE: Informa ao navegador que este é um documento HTML5.
  É como dizer "Ei navegador, vou falar HTML moderno com você!"
-->

<html lang="pt-BR">
  <!-- 
  <html>: É a raiz de tudo. Tudo que você criar ficará dentro dela.
  lang="pt-BR": Informa o idioma (importante para acessibilidade e SEO)
-->

  <head>
    <!-- 
    <head>: A "cabeça" do documento. Contém informações SOBRE a página,
    mas que não aparecem diretamente na tela (metadados).
  -->

    <meta charset="UTF-8" />
    <!-- charset: Define o conjunto de caracteres (permite acentos, ç, etc.) -->

    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- viewport: Faz o site funcionar bem em celulares (responsivo) -->

    <title>Meu Portfólio | Desenvolvedor</title>
    <!-- title: O texto que aparece na aba do navegador -->

    <link rel="stylesheet" href="style.css" />
    <!-- link: Conecta este HTML ao arquivo CSS (estilos) -->
  </head>

  <body>
    <!-- 
    <body>: O "corpo" do documento. TUDO que aparece na tela fica aqui.
  -->

    <!-- ========== CABEÇALHO ========== -->
    <header class="header">
      <!-- 
      <header>: Cabeçalho semântico da página.
      class="header": Um "apelido" para estilizar no CSS
    -->

      <div class="container">
        <img src="imagens/foto.jpg" alt="Foto de perfil" class="foto-perfil" />
        <!-- 
        <img>: Elemento para exibir imagens
        src: Caminho da imagem
        alt: Texto alternativo (aparece se a imagem não carregar + acessibilidade)
      -->

        <h1>Seu Nome Aqui</h1>
        <!-- <h1>: Título principal (Heading 1) - o mais importante da página -->

        <p class="subtitulo">Desenvolvedor Full Stack</p>
        <!-- <p>: Parágrafo de texto -->
      </div>
    </header>

    <!-- ========== SOBRE MIM ========== -->
    <section class="sobre" id="sobre">
      <!-- 
      <section>: Seção semântica - agrupa conteúdo relacionado
      id="sobre": Identificador único (útil para links âncora)
    -->

      <div class="container">
        <h2>Sobre Mim</h2>
        <!-- <h2>: Subtítulo (Heading 2) - hierarquia de importância -->

        <p>
          Olá! Sou um desenvolvedor apaixonado por tecnologia e resolução de
          problemas. Comecei minha jornada na programação em 2022 e desde então
          venho aprendendo e criando projetos incríveis.
        </p>
        <p>
          Tenho experiência com desenvolvimento web, sempre buscando escrever
          código limpo e criar interfaces intuitivas.
        </p>
      </div>
    </section>

    <!-- ========== EXPERIÊNCIAS ========== -->
    <section class="experiencias" id="experiencias">
      <div class="container">
        <h2>Experiências Profissionais</h2>

        <!-- Vamos criar 2 cards manualmente (depois transformaremos em JS) -->

        <div class="card-experiencia">
          <span class="badge atual">ATUAL</span>
          <h3>Desenvolvedor Front-end</h3>
          <p class="empresa">Tech Solutions Ltda</p>
          <p class="periodo">2023 - Presente</p>
          <p class="descricao">
            Desenvolvimento de interfaces responsivas utilizando HTML, CSS e
            JavaScript. Foco em experiência do usuário e performance.
          </p>
        </div>

        <div class="card-experiencia">
          <span class="badge passada">PASSADA</span>
          <h3>Estagiário de Desenvolvimento</h3>
          <p class="empresa">Byte Factory</p>
          <p class="periodo">2022 - 2023</p>
          <p class="descricao">
            Suporte no desenvolvimento de aplicações web. Correção de bugs e
            implementação de pequenas funcionalidades.
          </p>
        </div>
      </div>
    </section>

    <!-- ========== HABILIDADES ========== -->
    <section class="skills" id="skills">
      <div class="container">
        <h2>Habilidades</h2>

        <div class="skills-container">
          <!-- Lista estática (depois transformaremos em JS) -->
          <span class="skill-tag">HTML5</span>
          <span class="skill-tag">CSS3</span>
          <span class="skill-tag">JavaScript</span>
          <span class="skill-tag">Git & GitHub</span>
          <span class="skill-tag">Responsive Design</span>
        </div>
      </div>
    </section>

    <!-- ========== PROJETOS ========== -->
    <section class="projetos" id="projetos">
      <div class="container">
        <h2>Projetos</h2>

        <div class="card-projeto">
          <img
            src="imagens/projeto1.png"
            alt="Calculadora"
            class="projeto-img"
          />
          <div class="projeto-info">
            <h3>Calculadora JavaScript</h3>
            <p>
              Calculadora funcional com operações básicas, construída com JS
              vanilla.
            </p>
            <a
              href="https://github.com/seu-usuario/calculadora"
              target="_blank"
              class="btn"
            >
              Ver no GitHub
            </a>
            <!-- 
            <a>: Link (âncora)
            href: Destino do link
            target="_blank": Abre em nova aba
          --></div>
        </div>

        <div class="card-projeto">
          <img
            src="imagens/projeto2.png"
            alt="To-Do List"
            class="projeto-img"
          />
          <div class="projeto-info">
            <h3>Lista de Tarefas</h3>
            <p>Aplicação de gerenciamento de tarefas com localStorage.</p>
            <a
              href="https://github.com/seu-usuario/todo-list"
              target="_blank"
              class="btn"
            >
              Ver no GitHub
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- ========== CONTATO ========== -->
    <footer class="contato" id="contato">
      <!-- <footer>: Rodapé semântico da página -->

      <div class="container">
        <h2>Entre em Contato</h2>
        <div class="contato-links">
          <a href="mailto:seu-email@exemplo.com">📧 Email</a>
          <a href="https://github.com/seu-usuario" target="_blank">💻 GitHub</a>
          <a href="https://linkedin.com/in/seu-perfil" target="_blank"
            >💼 LinkedIn</a
          >
        </div>
        <p class="copyright">© 2024 Seu Nome. Todos os direitos reservados.</p>
      </div>
    </footer>

    <script src="script.js"></script>
    <!-- 
    <script>: Conecta este HTML ao arquivo JavaScript
    Colocamos no FINAL do body para garantir que o HTML carregue primeiro
  --></body>
</html>
```

<!-- parei aq dia 08/03                             . -->

### 🤔 Perguntas para Reflexão

1. **Por que colocamos o `<script>` no final do `<body>`?**
   <details>
   <summary>Clique para ver a resposta</summary>

   Porque o JavaScript precisa acessar os elementos HTML. Se ele rodar antes do HTML carregar, não vai encontrar nada! Colocando no final, garantimos que tudo já está na tela.
   </details>

2. **Qual a diferença entre `<h1>` e `<h2>`?**
   <details>
   <summary>Clique para ver a resposta</summary>

   São níveis de hierarquia. `<h1>` é o título principal (só deve ter um por página), `<h2>` são subtítulos, `<h3>` são sub-subtítulos, e assim por diante até `<h6>`. É como capítulos de um livro.
   </details>

---

## 1.2 - Criando a Pasta de Imagens

Antes de testar, crie uma pasta chamada `imagens` no mesmo local do seu `index.html` e coloque:

- Uma foto sua (renomeie para `foto.jpg`)
- Imagens de placeholder para os projetos (ou use serviços como `https://via.placeholder.com/400x250`)

---

## 1.3 - Testando no Navegador

Abra o arquivo `index.html` diretamente no navegador (duplo clique ou arraste para a janela do Chrome/Firefox).

**O que você vê?**  
Provavelmente uma página "feia", sem cores, tudo empilhado. Isso é **normal**! O HTML é apenas a estrutura. Agora vamos dar estilo.

---

# 🎨 FASE 2: CSS - Dando Vida ao Projeto

> **Pergunta**: Como você descreveria visualmente um portfólio profissional? Cores sóbrias? Moderno? Minimalista?

Vamos criar um estilo moderno e limpo.

## 2.1 - Criando o Arquivo CSS

Crie um arquivo chamado `style.css` na mesma pasta do `index.html`:

```css
/* ========================================
   RESET E CONFIGURAÇÕES GLOBAIS
   ======================================== */

/*
  * (asterisco): Seletor universal - seleciona TODOS os elementos
  
  Por padrão, navegadores adicionam margens e paddings.
  Resetamos tudo para ter controle total.
*/
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  /*
    box-sizing: border-box faz com que padding e border 
    sejam incluídos no tamanho total do elemento.
    Facilita MUITO os cálculos de layout!
  */
}

/*
  :root é como uma "caixa de variáveis globais" do CSS.
  Usamos para definir cores, tamanhos, etc. que vamos reutilizar.
  
  É como criar constantes em programação!
*/
:root {
  --cor-primaria: #6c5ce7; /* Roxo vibrante */
  --cor-secundaria: #00b894; /* Verde-água */
  --cor-texto: #2d3436; /* Cinza escuro */
  --cor-texto-claro: #636e72; /* Cinza médio */
  --cor-fundo: #f5f6fa; /* Cinza clarinho */
  --cor-branco: #ffffff;
  --cor-sombra: rgba(0, 0, 0, 0.1); /* Preto transparente para sombras */

  --espacamento: 20px;
  --border-radius: 10px;
}

/*
  body: Estilos aplicados ao corpo inteiro da página
*/
body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  /*
    font-family: Define a fonte do texto.
    Colocamos várias como "plano B" caso a primeira não esteja disponível.
  */

  color: var(--cor-texto);
  /*
    var(--nome-da-variavel): Pega o valor que definimos no :root
    Se quisermos mudar a cor do texto no site inteiro, mudamos só no :root!
  */

  line-height: 1.6;
  /* line-height: Espaçamento entre linhas (1.6 = 160% do tamanho da fonte) */

  background-color: var(--cor-fundo);
}

/*
  .container: Classe que usamos para centralizar e limitar largura do conteúdo
  
  O ponto (.) antes significa que estamos selecionando uma CLASSE
*/
.container {
  max-width: 1200px;
  /* max-width: Largura máxima - não vai passar disso mesmo em telas grandes */

  margin: 0 auto;
  /*
    margin: 0 auto é um "truque" clássico para centralizar horizontalmente.
    0 = margem vertical (cima/baixo)
    auto = margem horizontal (esquerda/direita) - divide o espaço igualmente
  */

  padding: 0 var(--espacamento);
  /* padding: Espaço INTERNO (entre a borda e o conteúdo) */
}

/* ========================================
   CABEÇALHO
   ======================================== */

.header {
  background: linear-gradient(
    135deg,
    var(--cor-primaria),
    var(--cor-secundaria)
  );
  /*
    linear-gradient: Cria um degradê (transição suave entre cores)
    135deg: Ângulo da transição (diagonal)
  */

  color: var(--cor-branco);
  text-align: center;
  /* text-align: center centraliza o texto horizontalmente */

  padding: 60px 20px;
}

.foto-perfil {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  /*
    border-radius: 50% transforma um quadrado em círculo!
    (Funciona se width e height forem iguais)
  */

  object-fit: cover;
  /*
    object-fit: cover faz a imagem preencher o espaço sem distorcer.
    É como "zoom para caber"
  */

  border: 5px solid var(--cor-branco);
  /* border: Borda ao redor da imagem */

  box-shadow: 0 5px 20px var(--cor-sombra);
  /*
    box-shadow: Sombra do elemento
    Sintaxe: horizontal vertical blur cor
  */

  margin-bottom: 20px;
}

.header h1 {
  font-size: 2.5rem;
  /* rem: Unidade relativa ao tamanho da fonte raiz (geralmente 16px) */
  /* 2.5rem = 2.5 × 16px = 40px */

  margin-bottom: 10px;
}

.subtitulo {
  font-size: 1.2rem;
  opacity: 0.9;
  /* opacity: Transparência (0 = invisível, 1 = opaco) */
}

/* ========================================
   SEÇÕES GERAIS
   ======================================== */

section {
  padding: 60px 20px;
}

section h2 {
  font-size: 2rem;
  color: var(--cor-primaria);
  margin-bottom: 30px;
  text-align: center;
  position: relative;
  /* position: relative permite posicionar elementos filhos de forma absoluta */
}

/*
  ::after é um "pseudo-elemento" - cria um elemento virtual
  Vamos usar para criar uma linha decorativa abaixo do título
*/
section h2::after {
  content: "";
  /* content: '' é obrigatório para ::after funcionar */

  display: block;
  width: 60px;
  height: 4px;
  background: var(--cor-secundaria);
  margin: 10px auto 0;
  border-radius: 2px;
}

/* ========================================
   SOBRE MIM
   ======================================== */

.sobre {
  background: var(--cor-branco);
}

.sobre p {
  max-width: 800px;
  margin: 0 auto 20px;
  /* Centraliza o parágrafo e adiciona espaço embaixo */

  font-size: 1.1rem;
  color: var(--cor-texto-claro);
  text-align: center;
}

/* ========================================
   EXPERIÊNCIAS
   ======================================== */

.card-experiencia {
  background: var(--cor-branco);
  border-radius: var(--border-radius);
  padding: 25px;
  margin-bottom: 20px;

  /*
    Flexbox: Sistema de layout poderoso para organizar elementos
  */
  position: relative;
  /* Permite posicionar o badge de forma absoluta */

  border-left: 5px solid var(--cor-primaria);
  /* Barra colorida na esquerda */

  box-shadow: 0 2px 10px var(--cor-sombra);

  transition: all 0.3s ease;
  /*
    transition: Anima mudanças de propriedades
    all = todas as propriedades
    0.3s = duração de 300 milissegundos
    ease = curva de animação suave
  */
}

/*
  :hover é uma "pseudo-classe" - aplica estilos quando o mouse passa por cima
*/
.card-experiencia:hover {
  transform: translateY(-5px);
  /*
    transform: translateY move o elemento no eixo Y (vertical)
    -5px = move 5 pixels para CIMA
  */

  box-shadow: 0 5px 20px var(--cor-sombra);
  /* Sombra fica maior no hover, criando efeito de "elevação" */
}

.badge {
  display: inline-block;
  /* inline-block permite definir width/height em elementos inline */

  padding: 5px 15px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: bold;
  text-transform: uppercase;
  /* text-transform: uppercase deixa todo texto em MAIÚSCULAS */

  margin-bottom: 10px;
}

.badge.atual {
  background: var(--cor-secundaria);
  color: var(--cor-branco);
}

.badge.passada {
  background: var(--cor-texto-claro);
  color: var(--cor-branco);
}

.card-experiencia h3 {
  color: var(--cor-primaria);
  margin-bottom: 10px;
}

.empresa {
  font-weight: bold;
  /* font-weight: bold deixa o texto em negrito */

  color: var(--cor-texto);
  margin-bottom: 5px;
}

.periodo {
  font-size: 0.9rem;
  color: var(--cor-texto-claro);
  margin-bottom: 15px;
}

.descricao {
  color: var(--cor-texto-claro);
  line-height: 1.6;
}

/* ========================================
   HABILIDADES
   ======================================== */

.skills {
  background: var(--cor-branco);
}

.skills-container {
  display: flex;
  /*
    Flexbox ativado! Agora os elementos filhos podem ser organizados
    de forma flexível (lado a lado, empilhados, centralizados, etc.)
  */

  flex-wrap: wrap;
  /*
    flex-wrap: wrap faz os elementos "quebrarem" para a próxima linha
    quando não couberem na largura disponível.
    
    É como texto que quebra linha automaticamente!
  */

  gap: 15px;
  /*
    gap: Espaço entre os itens flex (super prático!)
    Antes do gap, tínhamos que usar margin em cada item
  */

  justify-content: center;
  /*
    justify-content: Alinha itens no eixo PRINCIPAL (horizontal, neste caso)
    center = centraliza
  */
}

.skill-tag {
  background: var(--cor-fundo);
  color: var(--cor-primaria);
  padding: 10px 20px;
  border-radius: 25px;
  font-weight: 500;
  border: 2px solid var(--cor-primaria);

  transition: all 0.3s ease;
}

.skill-tag:hover {
  background: var(--cor-primaria);
  color: var(--cor-branco);
  transform: scale(1.05);
  /*
    transform: scale aumenta ou diminui o tamanho
    1.05 = 105% do tamanho original
  */
}

/* ========================================
   PROJETOS
   ======================================== */

.card-projeto {
  background: var(--cor-branco);
  border-radius: var(--border-radius);
  overflow: hidden;
  /*
    overflow: hidden corta tudo que ultrapassar as bordas.
    Útil com border-radius para arredondar cantos de imagens
  */

  box-shadow: 0 2px 10px var(--cor-sombra);
  margin-bottom: 30px;

  transition: all 0.3s ease;
}

.card-projeto:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 20px var(--cor-sombra);
}

.projeto-img {
  width: 100%;
  height: 250px;
  object-fit: cover;
}

.projeto-info {
  padding: 25px;
}

.projeto-info h3 {
  color: var(--cor-primaria);
  margin-bottom: 10px;
}

.projeto-info p {
  color: var(--cor-texto-claro);
  margin-bottom: 20px;
}

.btn {
  display: inline-block;
  padding: 10px 25px;
  background: var(--cor-primaria);
  color: var(--cor-branco);
  text-decoration: none;
  /* text-decoration: none remove o sublinhado padrão de links */

  border-radius: 5px;
  transition: all 0.3s ease;
  font-weight: 500;
}

.btn:hover {
  background: var(--cor-secundaria);
  transform: translateY(-2px);
}

/* ========================================
   CONTATO
   ======================================== */

.contato {
  background: var(--cor-primaria);
  color: var(--cor-branco);
  text-align: center;
  padding: 60px 20px;
}

.contato h2 {
  color: var(--cor-branco);
}

.contato h2::after {
  background: var(--cor-branco);
}

.contato-links {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin: 30px 0;
  flex-wrap: wrap;
}

.contato-links a {
  color: var(--cor-branco);
  text-decoration: none;
  font-size: 1.1rem;
  padding: 10px 20px;
  border: 2px solid var(--cor-branco);
  border-radius: 5px;
  transition: all 0.3s ease;
}

.contato-links a:hover {
  background: var(--cor-branco);
  color: var(--cor-primaria);
}

.copyright {
  margin-top: 30px;
  font-size: 0.9rem;
  opacity: 0.8;
}

/* ========================================
   RESPONSIVIDADE (para telas pequenas)
   ======================================== */

/*
  @media: "Media queries" - aplica estilos apenas em certas condições
  max-width: 768px = aplica apenas se a largura da tela for 768px ou menos
  (tablets e celulares)
*/

/* Parei aq dia 08/03 */

@media (max-width: 768px) {
  .header h1 {
    font-size: 2rem;
  }

  section h2 {
    font-size: 1.5rem;
  }

  .foto-perfil {
    width: 120px;
    height: 120px;
  }

  .contato-links {
    flex-direction: column;
    /* Empilha os links verticalmente em telas pequenas */
  }
}
```

### 🤔 Perguntas para Reflexão

1. **O que acontece se você mudar `--cor-primaria` no `:root`?**
   <details>
   <summary>Resposta</summary>

   TODAS as partes do site que usam `var(--cor-primaria)` mudam automaticamente! É por isso que variáveis CSS são tão poderosas - mude uma vez, afeta tudo.
   </details>

2. **Por que usamos `display: flex` no `.skills-container`?**
   <details>
   <summary>Resposta</summary>

   Para que as tags de habilidades fiquem lado a lado e se organizem automaticamente. O `flex-wrap: wrap` faz elas "quebrarem" para a próxima linha quando não couberem, como palavras em um parágrafo.
   </details>

---

## 2.2 - Testando o CSS

Atualize a página no navegador (F5). Agora sim! Você deve ver um portfólio visual mente agradável, com cores, espaçamentos e animações ao passar o mouse.

---

# 🚀 FASE 3: JavaScript - A Primeira Refatoração

> **Pergunta Crítica**: Imagine que você tem 10 experiências profissionais. Você prefere escrever 10 blocos de HTML manualmente, ou deixar o JavaScript fazer isso automaticamente?

Exato! Vamos transformar nossos dados em código reutilizável.

## 3.1 - Entendendo o Conceito

Atualmente, nossos 2 cards de experiência estão "escritos à mão" no HTML. Se quisermos adicionar mais, teríamos que copiar e colar o HTML inteiro, mudando cada detalhe manualmente.

**A ideia**: Guardar os dados em um lugar (JavaScript) e usar código para gerar o HTML automaticamente.

## 3.2 - Criando o Arquivo JavaScript

Crie um arquivo chamado `script.js` na mesma pasta:

```javascript
/* ==========================================
   📦 DADOS DAS EXPERIÊNCIAS
   ========================================== */

/*
  CONCEITO: Array de Objetos
  
  - Array (lista): Estrutura que guarda vários itens em ordem
    Exemplo: ['maçã', 'banana', 'laranja']
  
  - Objeto: Estrutura que guarda pares "chave: valor"
    Exemplo: { nome: 'João', idade: 25 }
  
  - Array de Objetos: Lista de objetos
    Cada experiência é um objeto com suas propriedades (cargo, empresa, etc.)
*/

const experiencias = [
  {
    tipo: "atual",
    cargo: "Desenvolvedor Front-end",
    empresa: "Tech Solutions Ltda",
    periodo: "2023 - Presente",
    descricao:
      "Desenvolvimento de interfaces responsivas utilizando HTML, CSS e JavaScript. Foco em experiência do usuário e performance.",
  },
  {
    tipo: "passada",
    cargo: "Estagiário de Desenvolvimento",
    empresa: "Byte Factory",
    periodo: "2022 - 2023",
    descricao:
      "Suporte no desenvolvimento de aplicações web. Correção de bugs e implementação de pequenas funcionalidades.",
  },
  {
    tipo: "passada",
    cargo: "Freelancer Web Design",
    empresa: "Autônomo",
    periodo: "2021 - 2022",
    descricao:
      "Criação de sites institucionais para pequenas empresas. Design responsivo e otimização para SEO.",
  },
];

/*
  PERGUNTA: Quantas experiências temos agora?
  Resposta: 3! E adicionamos a terceira sem tocar no HTML.
*/
```

### 🤔 Momento de Reflexão

**Antes de continuar**: Como você acha que o JavaScript poderia "pegar" esse array e transformar em HTML na tela?

<details>
<summary>Dica</summary>

Precisamos de 3 etapas:

1. **Buscar** onde no HTML vamos colocar os cards
2. **Transformar** cada objeto do array em uma string de HTML
3. **Inserir** essas strings no HTML

</details>

---

## 3.3 - Conceito: O `document`

```javascript
/* ==========================================
   🌐 O OBJETO 'document'
   ========================================== */

/*
  O que é 'document'?
  
  'document' é um objeto GLOBAL criado automaticamente pelo navegador.
  Ele representa toda a árvore de elementos HTML da sua página.
  
  ANALOGIA: Pense no 'document' como a "porta de entrada" para sua página.
  Se você quer buscar, modificar, adicionar ou remover elementos HTML,
  você sempre começa pelo 'document'.
  
  Métodos mais usados:
  - document.getElementById('id')     → Busca elemento por ID
  - document.querySelector('.classe') → Busca elemento por seletor CSS
  - document.createElement('div')     → Cria novo elemento
*/

// Exemplo prático:
console.log(document);
/*
  Abra o DevTools (F12 → aba Console) e veja o que aparece!
  Você verá toda a estrutura HTML da página.
*/
```

---

## 3.4 - Buscando o Container

Agora precisamos dizer ao JavaScript "onde" colocar nossos cards. Primeiro, vamos preparar o HTML:

**No `index.html`, SUBSTITUA** a seção de experiências por:

```html
<!-- ========== EXPERIÊNCIAS ========== -->
<section class="experiencias" id="experiencias">
  <div class="container">
    <h2>Experiências Profissionais</h2>

    <!-- Container vazio - o JS vai preencher aqui -->
    <div id="container-experiencias"></div>
  </div>
</section>
```

**No `script.js`, adicione**:

```javascript
/* ==========================================
   🎯 BUSCANDO O CONTAINER
   ========================================== */

const containerExperiencias = document.getElementById("container-experiencias");

/*
  EXPLICAÇÃO LINHA POR LINHA:
  
  1. document → Objeto que representa a página
  2. .getElementById() → Método que busca um elemento pelo ID
  3. 'container-experiencias' → O ID que demos no HTML
  4. containerExperiencias → Variável que agora "aponta" para aquela <div>
  
  ANALOGIA: É como pegar o controle remoto (containerExperiencias)
  de uma TV específica (div#container-experiencias) para poder controlá-la.
*/

// Teste: vamos verificar se pegamos o elemento certo
console.log(containerExperiencias);
/*
  Abra o console (F12) e você deve ver:
  <div id="container-experiencias"></div>
  
  Se aparecer 'null', significa que o ID está errado ou não existe!
*/
```

---

## 3.5 - O Método `.map()` - Transformando Dados

> **Pergunta**: Se você tem uma lista de números `[1, 2, 3]` e quer o dobro de cada um `[2, 4, 6]`, como faria?

Em programação, poderíamos usar um loop `for`. Mas existe uma forma mais elegante: `.map()`!

```javascript
/* ==========================================
   🗺️ ENTENDENDO O .map()
   ========================================== */

/*
  O que é .map()?
  
  .map() é um MÉTODO de arrays que:
  1. Percorre cada item do array
  2. Aplica uma função em cada item
  3. Retorna um NOVO array com os resultados
  
  IMPORTANTE: Não modifica o array original!
*/

// Exemplo simples:
const numeros = [1, 2, 3];

const dobrados = numeros.map((numero) => {
  return numero * 2;
});

console.log(dobrados); // [2, 4, 6]
console.log(numeros); // [1, 2, 3] - original intacto!

/*
  SINTAXE:
  
  array.map((item) => {
    return alguma_coisa;
  });
  
  - item: É cada elemento do array (um de cada vez)
  - => : "Arrow function" - jeito moderno de escrever funções
  - return: O que você quer que entre no novo array
*/
```

### 🤔 Exercício Mental

Se temos um array de experiências, e queremos um array de HTMLs (um para cada experiência), o que usamos?

<details>
<summary>Resposta</summary>

`.map()`! Vamos transformar cada objeto de experiência em uma string HTML.

</details>

---

## 3.6 - Gerando HTML com Template Literals

```javascript
/* ==========================================
   📝 TEMPLATE LITERALS
   ========================================== */

/*
  O que são Template Literals?
  
  São strings modernas do JavaScript que permitem:
  1. Escrever texto em múltiplas linhas
  2. Inserir variáveis/expressões dentro do texto
  
  SINTAXE: Usa crase ` ` em vez de aspas ' ' ou " "
*/

// Jeito antigo (concatenação):
const nome = "João";
const idade = 25;
const frase = "Olá, meu nome é " + nome + " e tenho " + idade + " anos.";

// Jeito moderno (template literal):
const fraseModerna = `Olá, meu nome é ${nome} e tenho ${idade} anos.`;

/*
  ${variavel} → Injeta o valor da variável no texto
  
  Vantagem: Fica MUITO mais legível, especialmente com HTML!
*/
```

---

## 3.7 - Juntando Tudo: .map() + Template Literals

Agora vem a mágica! Adicione no `script.js`:

```javascript
/* ==========================================
   ✨ TRANSFORMANDO DADOS EM HTML
   ========================================== */

const cardsHTML = experiencias.map((exp) => {
  /*
    EXPLICAÇÃO:
    
    - experiencias.map() → Percorre cada experiência
    - (exp) → Nome que demos para cada experiência (poderia ser qualquer nome)
    - exp.cargo → Acessa a propriedade 'cargo' do objeto
  */

  return `
    <div class="card-experiencia">
      <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
      <h3>${exp.cargo}</h3>
      <p class="empresa">${exp.empresa}</p>
      <p class="periodo">${exp.periodo}</p>
      <p class="descricao">${exp.descricao}</p>
    </div>
  `;

  /*
    O QUE ESTÁ ACONTECENDO AQUI?
    
    1. Para cada 'exp' no array 'experiencias'
    2. Criamos um bloco de HTML (string)
    3. Usamos ${exp.propriedade} para injetar os dados
    4. Retornamos essa string
    
    RESULTADO: cardsHTML será um ARRAY de strings HTML!
  */
});

// Vamos ver o que temos:
console.log(cardsHTML);
/*
  Você verá algo como:
  [
    '<div class="card-experiencia">...</div>',
    '<div class="card-experiencia">...</div>',
    '<div class="card-experiencia">...</div>'
  ]
  
  Um array com 3 strings HTML!
*/
```

### 🤔 Pergunta

Olhe essa linha:

```javascript
<span class="badge ${exp.tipo}">
  ${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}
</span>
```

**O que é `exp.tipo === 'atual' ? 'ATUAL' : 'PASSADA'`?**

<details>
<summary>Resposta</summary>

É um **operador ternário** - um "if resumido".

**Sintaxe**: `condição ? se_true : se_false`

Lê-se: "Se `exp.tipo` for igual a 'atual', retorna 'ATUAL', senão retorna 'PASSADA'"

É como escrever:

```javascript
if (exp.tipo === "atual") {
  return "ATUAL";
} else {
  return "PASSADA";
}
```

Mas em uma linha!

</details>

---

## 3.8 - Método `.join()` - Transformando Array em String

```javascript
/* ==========================================
   🔗 O MÉTODO .join()
   ========================================== */

/*
  Temos um problema: cardsHTML é um ARRAY de strings.
  Mas o HTML espera UMA ÚNICA string!
  
  Exemplo do problema:
  ['<div>A</div>', '<div>B</div>'] → queremos '<div>A</div><div>B</div>'
*/

// O método .join() resolve isso!
const textoFinal = cardsHTML.join("");

/*
  .join('separador') → Junta os itens do array em uma string
  
  - .join(',') → Coloca vírgula entre os itens
  - .join(' ') → Coloca espaço entre os itens
  - .join('') → Junta SEM NADA entre os itens (o que queremos!)
*/

// Exemplo:
const frutas = ["maçã", "banana", "laranja"];
console.log(frutas.join(", ")); // "maçã, banana, laranja"
console.log(frutas.join("")); // "maçãbananalraranja"
```

---

## 3.9 - Propriedade `.innerHTML` - Injetando no DOM

```javascript
/* ==========================================
   💉 INJETANDO HTML NA PÁGINA
   ========================================== */

/*
  .innerHTML: Propriedade que representa o conteúdo HTML de um elemento.
  
  - LER: const conteudo = elemento.innerHTML;
  - ESCREVER: elemento.innerHTML = '<p>Novo conteúdo</p>';
*/

// Agora vamos injetar nossos cards no container!
containerExperiencias.innerHTML = cardsHTML.join("");

/*
  O QUE ACONTECEU:
  
  1. cardsHTML.join('') → Juntou as 3 strings HTML em uma só
  2. containerExperiencias.innerHTML = ... → Colocou essa string dentro da <div>
  
  RESULTADO: Os cards aparecem na tela!
*/
```

---

## 3.10 - Código Completo da FASE 3

Seu `script.js` completo até agora:

```javascript
// ========== DADOS ==========
const experiencias = [
  {
    tipo: "atual",
    cargo: "Desenvolvedor Front-end",
    empresa: "Tech Solutions Ltda",
    periodo: "2023 - Presente",
    descricao:
      "Desenvolvimento de interfaces responsivas utilizando HTML, CSS e JavaScript. Foco em experiência do usuário e performance.",
  },
  {
    tipo: "passada",
    cargo: "Estagiário de Desenvolvimento",
    empresa: "Byte Factory",
    periodo: "2022 - 2023",
    descricao:
      "Suporte no desenvolvimento de aplicações web. Correção de bugs e implementação de pequenas funcionalidades.",
  },
  {
    tipo: "passada",
    cargo: "Freelancer Web Design",
    empresa: "Autônomo",
    periodo: "2021 - 2022",
    descricao:
      "Criação de sites institucionais para pequenas empresas. Design responsivo e otimização para SEO.",
  },
];

// ========== BUSCAR CONTAINER ==========
const containerExperiencias = document.getElementById("container-experiencias");

// ========== TRANSFORMAR DADOS EM HTML ==========
const cardsHTML = experiencias.map((exp) => {
  return `
    <div class="card-experiencia">
      <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
      <h3>${exp.cargo}</h3>
      <p class="empresa">${exp.empresa}</p>
      <p class="periodo">${exp.periodo}</p>
      <p class="descricao">${exp.descricao}</p>
    </div>
  `;
});

// ========== INJETAR NO DOM ==========
containerExperiencias.innerHTML = cardsHTML.join("");
```

### ✅ Teste

Atualize a página. Você deve ver 3 cards de experiência! E o melhor: para adicionar mais, basta adicionar um objeto no array `experiencias`. Nada de mexer no HTML!

---

# 🔥 FASE 4: .map() Avançado - Ordenação, Filtro e Transformações

Agora que você entende o básico, vamos explorar o poder real do `.map()` e métodos relacionados!

## 4.1 - Ordenação com `.sort()`

> **Pergunta**: Como você mostraria suas experiências? Da mais recente para a mais antiga, ou o contrário?

Vamos adicionar ordenação aos nossos dados.

### Preparando os Dados

Primeiro, vamos adicionar uma propriedade numérica `ano` para facilitar a ordenação:

```javascript
const experiencias = [
  {
    tipo: "atual",
    cargo: "Desenvolvedor Front-end",
    empresa: "Tech Solutions Ltda",
    periodo: "2023 - Presente",
    ano: 2023, // ← NOVO!
    descricao:
      "Desenvolvimento de interfaces responsivas utilizando HTML, CSS e JavaScript.",
  },
  {
    tipo: "passada",
    cargo: "Estagiário de Desenvolvimento",
    empresa: "Byte Factory",
    periodo: "2022 - 2023",
    ano: 2022, // ← NOVO!
    descricao:
      "Suporte no desenvolvimento de aplicações web. Correção de bugs.",
  },
  {
    tipo: "passada",
    cargo: "Freelancer Web Design",
    empresa: "Autônomo",
    periodo: "2021 - 2022",
    ano: 2021, // ← NOVO!
    descricao: "Criação de sites institucionais para pequenas empresas.",
  },
];
```

### Entendendo o `.sort()`

```javascript
/* ==========================================
   📊 O MÉTODO .sort()
   ========================================== */

/*
  .sort() ordena os elementos de um array.
  
  ATENÇÃO: Ele MODIFICA o array original!
  
  Sintaxe:
  array.sort((a, b) => {
    return numero;
  });
  
  A função recebe dois elementos (a, b) e deve retornar:
  - Número NEGATIVO: 'a' vem antes de 'b'
  - ZERO: mantém ordem original
  - Número POSITIVO: 'b' vem antes de 'a'
*/

// Exemplo com números:
const numeros = [3, 1, 4, 1, 5, 9, 2, 6];

// Ordem crescente:
numeros.sort((a, b) => a - b);
console.log(numeros); // [1, 1, 2, 3, 4, 5, 6, 9]

// Ordem decrescente:
numeros.sort((a, b) => b - a);
console.log(numeros); // [9, 6, 5, 4, 3, 2, 1, 1]

/*
  ENTENDENDO a - b:
  
  Se a = 5 e b = 3:
    a - b = 5 - 3 = 2 (positivo) → b vem antes de a
  
  Se a = 3 e b = 5:
    a - b = 3 - 5 = -2 (negativo) → a vem antes de b
  
  Resultado: ordem crescente!
*/
```

### Aplicando ao Nosso Projeto

```javascript
// Antes de transformar em HTML, vamos ordenar:
const experienciasOrdenadas = experiencias.sort((a, b) => {
  return b.ano - a.ano; // Mais recente primeiro (decrescente)
});

// Agora usamos o array ordenado:
const cardsHTML = experienciasOrdenadas.map((exp) => {
  return `
    <div class="card-experiencia">
      <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
      <h3>${exp.cargo}</h3>
      <p class="empresa">${exp.empresa}</p>
      <p class="periodo">${exp.periodo}</p>
      <p class="descricao">${exp.descricao}</p>
    </div>
  `;
});
```

### 💡 Encadeamento de Métodos

Podemos escrever de forma mais concisa:

```javascript
const cardsHTML = experiencias
  .sort((a, b) => b.ano - a.ano) // Primeiro ordena
  .map((exp) => {
    // Depois transforma
    return `<div class="card-experiencia">...</div>`;
  });

/*
  Isso é chamado de "method chaining" (encadeamento de métodos).
  Cada método retorna um array, então podemos chamar outro método logo em seguida!
*/
```

---

## 4.2 - Filtro com `.filter()`

> **Pergunta**: E se você quisesse mostrar apenas experiências atuais? Ou apenas passadas?

### Entendendo o `.filter()`

```javascript
/* ==========================================
   🔍 O MÉTODO .filter()
   ========================================== */

/*
  .filter() cria um NOVO array apenas com elementos que passam em um teste.
  
  Sintaxe:
  array.filter((item) => {
    return true ou false;
  });
  
  - Se retornar true: item é INCLUÍDO no novo array
  - Se retornar false: item é DESCARTADO
*/

// Exemplo:
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const pares = numeros.filter((num) => {
  return num % 2 === 0; // % é o operador módulo (resto da divisão)
});

console.log(pares); // [2, 4, 6, 8, 10]

/*
  EXPLICAÇÃO:
  
  - num % 2 === 0 significa "o resto da divisão por 2 é zero?"
  - Se sim, é par (true), então entra no novo array
  - Se não, é ímpar (false), então é descartado
*/
```

### Aplicando ao Nosso Projeto

```javascript
// Filtrar apenas experiências atuais:
const experienciasAtuais = experiencias.filter((exp) => {
  return exp.tipo === "atual";
});

// Filtrar apenas experiências passadas:
const experienciasPassadas = experiencias.filter((exp) => {
  return exp.tipo === "passada";
});

// Podemos encadear filter + sort + map!
const cardsHTML = experiencias
  .filter((exp) => exp.tipo === "passada") // Só passadas
  .sort((a, b) => b.ano - a.ano) // Ordenar
  .map((exp) => {
    // Transformar em HTML
    return `<div class="card-experiencia">...</div>`;
  });
```

### 🎯 Desafio Prático

Adicione dois botões no HTML:

```html
<div class="filtros">
  <button onclick="mostrarTodas()">Todas</button>
  <button onclick="mostrarAtuais()">Apenas Atuais</button>
  <button onclick="mostrarPassadas()">Apenas Passadas</button>
</div>
```

E no JavaScript:

```javascript
// Função reutilizável para renderizar experiências
function renderizarExperiencias(lista) {
  const cardsHTML = lista
    .sort((a, b) => b.ano - a.ano)
    .map((exp) => {
      return `
        <div class="card-experiencia">
          <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
          <h3>${exp.cargo}</h3>
          <p class="empresa">${exp.empresa}</p>
          <p class="periodo">${exp.periodo}</p>
          <p class="descricao">${exp.descricao}</p>
        </div>
      `;
    });

  containerExperiencias.innerHTML = cardsHTML.join("");
}

// Funções de filtro
function mostrarTodas() {
  renderizarExperiencias(experiencias);
}

function mostrarAtuais() {
  const atuais = experiencias.filter((exp) => exp.tipo === "atual");
  renderizarExperiencias(atuais);
}

function mostrarPassadas() {
  const passadas = experiencias.filter((exp) => exp.tipo === "passada");
  renderizarExperiencias(passadas);
}

// Renderizar todas ao carregar a página
mostrarTodas();
```

---

## 4.3 - Transformação Condicional

Vamos deixar os badges mais dinâmicos com ícones!

```javascript
const cardsHTML = experiencias
  .sort((a, b) => b.ano - a.ano)
  .map((exp) => {
    // Escolher ícone baseado no tipo
    const icone = exp.tipo === "atual" ? "🚀" : "📜";

    // Escolher cor da borda baseado no tipo
    const corBorda =
      exp.tipo === "atual" ? "var(--cor-secundaria)" : "var(--cor-primaria)";

    return `
      <div class="card-experiencia" style="border-left-color: ${corBorda}">
        <span class="badge ${exp.tipo}">${icone} ${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
        <h3>${exp.cargo}</h3>
        <p class="empresa">${exp.empresa}</p>
        <p class="periodo">${exp.periodo}</p>
        <p class="descricao">${exp.descricao}</p>
      </div>
    `;
  });
```

---

## 4.4 - Usando o Índice no `.map()`

> **Pergunta**: E se você quiser numerar as experiências automaticamente?

```javascript
/* ==========================================
   🔢 SEGUNDO PARÂMETRO DO .map(): O ÍNDICE
   ========================================== */

/*
  .map() pode receber até 3 parâmetros:
  
  .map((item, index, array) => { ... })
  
  - item: O elemento atual
  - index: A posição (começa em 0)
  - array: O array completo (raramente usado)
*/

// Exemplo:
const frutas = ["maçã", "banana", "laranja"];

const frutasNumeradas = frutas.map((fruta, i) => {
  return `${i + 1}. ${fruta}`; // +1 porque índice começa em 0
});

console.log(frutasNumeradas);
// ['1. maçã', '2. banana', '3. laranja']
```

### Aplicando ao Projeto

```javascript
const cardsHTML = experiencias
  .sort((a, b) => b.ano - a.ano)
  .map((exp, index) => {
    // ← Adicionamos 'index'
    const numero = index + 1;

    return `
      <div class="card-experiencia">
        <div class="card-header">
          <span class="numero-experiencia">#${numero}</span>
          <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
        </div>
        <h3>${exp.cargo}</h3>
        <p class="empresa">${exp.empresa}</p>
        <p class="periodo">${exp.periodo}</p>
        <p class="descricao">${exp.descricao}</p>
      </div>
    `;
  });
```

Adicione ao CSS:

```css
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.numero-experiencia {
  font-weight: bold;
  font-size: 1.2rem;
  color: var(--cor-primaria);
}
```

---

# 🎯 FASE 5: Aplicando em Skills e Projetos

Agora é sua vez de praticar! Vamos transformar Skills e Projetos em conteúdo dinâmico.

## 5.1 - Skills Dinâmicas

**Desafio**: Transforme a seção de skills para usar JavaScript.

### Dados

```javascript
const skills = [
  "HTML5",
  "CSS3",
  "JavaScript ES6+",
  "Git & GitHub",
  "Responsive Design",
  "Flexbox & Grid",
  "API REST",
  "Node.js",
];
```

### HTML

Substitua o conteúdo da seção:

```html
<section class="skills" id="skills">
  <div class="container">
    <h2>Habilidades</h2>
    <div class="skills-container" id="container-skills"></div>
  </div>
</section>
```

### JavaScript

```javascript
const containerSkills = document.getElementById("container-skills");

const skillsHTML = skills.map((skill) => {
  return `<span class="skill-tag">${skill}</span>`;
});

containerSkills.innerHTML = skillsHTML.join("");
```

### 🎯 Desafio Extra

Ordene as skills alfabeticamente antes de exibir:

```javascript
const skillsHTML = skills
  .sort() // Ordem alfabética (padrão do .sort() para strings)
  .map((skill) => {
    return `<span class="skill-tag">${skill}</span>`;
  });
```

---

## 5.2 - Projetos Dinâmicos

### Dados

```javascript
const projetos = [
  {
    nome: "Calculadora JavaScript",
    descricao:
      "Calculadora funcional com operações básicas, construída com JS vanilla.",
    imagem: "imagens/projeto1.png",
    link: "https://github.com/seu-usuario/calculadora",
  },
  {
    nome: "Lista de Tarefas",
    descricao:
      "Aplicação de gerenciamento de tarefas com localStorage para persistência.",
    imagem: "imagens/projeto2.png",
    link: "https://github.com/seu-usuario/todo-list",
  },
  {
    nome: "Pokedex",
    descricao: "Consumo da PokeAPI para exibir informações de Pokémons.",
    imagem: "imagens/projeto3.png",
    link: "https://github.com/seu-usuario/pokedex",
  },
];
```

### HTML

```html
<section class="projetos" id="projetos">
  <div class="container">
    <h2>Projetos</h2>
    <div id="container-projetos"></div>
  </div>
</section>
```

### JavaScript

```javascript
const containerProjetos = document.getElementById("container-projetos");

const projetosHTML = projetos.map((projeto) => {
  return `
    <div class="card-projeto">
      <img src="${projeto.imagem}" alt="${projeto.nome}" class="projeto-img">
      <div class="projeto-info">
        <h3>${projeto.nome}</h3>
        <p>${projeto.descricao}</p>
        <a href="${projeto.link}" target="_blank" class="btn">Ver no GitHub</a>
      </div>
    </div>
  `;
});

containerProjetos.innerHTML = projetosHTML.join("");
```

---

# 🎠 APÊNDICE A: Paginação com Navegação

Vamos criar um sistema de navegação tipo carrossel para as experiências!

## Conceito

Em vez de mostrar TODAS as experiências de uma vez, vamos mostrar apenas UMA por vez, com botões "Anterior" e "Próximo".

## A.1 - HTML

Substitua a seção de experiências por:

```html
<section class="experiencias" id="experiencias">
  <div class="container">
    <h2>Experiências Profissionais</h2>

    <!-- Container para UMA experiência -->
    <div id="experiencia-atual"></div>

    <!-- Navegação -->
    <div class="navegacao">
      <button id="btn-anterior" class="btn-nav">← Anterior</button>
      <span id="contador">1 / 3</span>
      <button id="btn-proximo" class="btn-nav">Próximo →</button>
    </div>
  </div>
</section>
```

## A.2 - CSS

Adicione ao `style.css`:

```css
.navegacao {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  margin-top: 30px;
}

.btn-nav {
  padding: 10px 20px;
  background: var(--cor-primaria);
  color: var(--cor-branco);
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.btn-nav:hover:not(:disabled) {
  background: var(--cor-secundaria);
  transform: translateY(-2px);
}

.btn-nav:disabled {
  background: var(--cor-texto-claro);
  cursor: not-allowed;
  opacity: 0.5;
}

#contador {
  font-weight: bold;
  font-size: 1.1rem;
  color: var(--cor-primaria);
}
```

## A.3 - JavaScript

```javascript
/* ==========================================
   🎠 SISTEMA DE PAGINAÇÃO
   ========================================== */

// Variável de estado - controla qual experiência está sendo exibida
let indiceAtual = 0;

/*
  CONCEITO: Estado
  
  'indiceAtual' é uma variável de ESTADO - ela guarda informação
  sobre o "estado atual" da aplicação.
  
  Quando mudamos ela, a interface precisa ser atualizada para refletir isso.
*/

// Elementos do DOM
const experienciaAtualDiv = document.getElementById("experiencia-atual");
const btnAnterior = document.getElementById("btn-anterior");
const btnProximo = document.getElementById("btn-proximo");
const contador = document.getElementById("contador");

// Função para exibir uma experiência específica
function exibirExperiencia(indice) {
  const exp = experiencias[indice];

  // Gerar HTML da experiência
  experienciaAtualDiv.innerHTML = `
    <div class="card-experiencia">
      <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
      <h3>${exp.cargo}</h3>
      <p class="empresa">${exp.empresa}</p>
      <p class="periodo">${exp.periodo}</p>
      <p class="descricao">${exp.descricao}</p>
    </div>
  `;

  // Atualizar contador
  contador.textContent = `${indice + 1} / ${experiencias.length}`;

  // Atualizar estado dos botões
  btnAnterior.disabled = indice === 0;
  btnProximo.disabled = indice === experiencias.length - 1;

  /*
    EXPLICAÇÃO DOS BOTÕES:
    
    - Se estamos no índice 0 (primeira experiência), desabilita botão "Anterior"
    - Se estamos no último índice, desabilita botão "Próximo"
    
    .disabled = true → Botão fica desabilitado (cinza, não clicável)
  */
}

/* ==========================================
   🖱️ EVENT LISTENERS
   ========================================== */

/*
  addEventListener: Registra uma função para ser executada quando um evento acontece.
  
  Sintaxe: elemento.addEventListener('tipo-do-evento', funcao);
  
  Eventos comuns:
  - 'click': Quando o elemento é clicado
  - 'mouseover': Quando o mouse passa por cima
  - 'keypress': Quando uma tecla é pressionada
*/

btnAnterior.addEventListener("click", () => {
  /*
    Arrow function sem parâmetros: () => { ... }
  */

  if (indiceAtual > 0) {
    indiceAtual--; // Diminui 1 (volta)
    exibirExperiencia(indiceAtual);
  }
});

btnProximo.addEventListener("click", () => {
  if (indiceAtual < experiencias.length - 1) {
    indiceAtual++; // Aumenta 1 (avança)
    exibirExperiencia(indiceAtual);
  }
});

// Exibir a primeira experiência ao carregar a página
exibirExperiencia(0);
```

### 🤔 Perguntas para Reflexão

1. **O que acontece se você clicar no botão "Próximo" 5 vezes seguidas?**
   <details>
   <summary>Resposta</summary>

   O índice aumenta até chegar no último (length - 1), depois o botão fica desabilitado e não permite mais cliques. A condição `if (indiceAtual < experiencias.length - 1)` impede de ultrapassar.
   </details>

2. **Como você adicionaria navegação por teclado (setas do teclado)?**
   <details>
   <summary>Resposta</summary>

   ```javascript
   document.addEventListener("keydown", (evento) => {
     if (evento.key === "ArrowLeft") {
       // Seta esquerda = anterior
       btnAnterior.click();
     } else if (evento.key === "ArrowRight") {
       // Seta direita = próximo
       btnProximo.click();
     }
   });
   ```

   </details>

---

# 🚀 APÊNDICE B: Deploy no GitHub Pages

Agora vamos colocar seu portfólio online, de graça!

## B.1 - Criando uma Conta no GitHub

1. Acesse [github.com](https://github.com)
2. Clique em "Sign up" (Cadastrar-se)
3. Preencha:
   - Email
   - Senha (crie uma forte!)
   - Username (será sua URL: `username.github.io`)
4. Verifique seu email
5. Pronto! Você tem uma conta GitHub.

---

## B.2 - Criando o Repositório

1. No GitHub, clique no botão **"New"** (ou ícone **+** → "New repository")

2. **Configure o repositório**:
   - **Nome**: Existem 2 opções:
     - `meu-portfolio` → Ficará em `username.github.io/meu-portfolio`
     - `username.github.io` → Ficará em `username.github.io` (site principal)
   - **Descrição** (opcional): "Meu portfólio pessoal"
   - **Visibilidade**: Marque **Public** (público)
   - **Inicializar**: Marque "Add a README file"

3. Clique em **"Create repository"**

---

## B.3 - Fazendo Upload dos Arquivos via Git

```bash
# Abra o terminal na pasta do seu projeto

# 1. Inicializar repositório Git local
git init

# 2. Adicionar todos os arquivos ao "stage" (área de preparação)
git add .

# 3. Fazer commit (salvar snapshot)
git commit -m "Adicionar portfólio completo"

# 4. Conectar ao repositório remoto (substitua 'username')
git remote add origin https://github.com/username/meu-portfolio.git

# 5. Enviar para GitHub
git branch -M main
git push -u origin main
```

**Explicação dos comandos**:

- `git init`: Cria um repositório Git na pasta
- `git add .`: Adiciona todos os arquivos para serem "commitados"
- `git commit -m "mensagem"`: Salva um ponto na história do projeto
- `git remote add origin URL`: Conecta seu repositório local ao GitHub
- `git push`: Envia os commits para o GitHub

---

## B.4 - Ativando o GitHub Pages

1. No seu repositório, vá em **"Settings"** (Configurações) - ícone de engrenagem

2. No menu lateral esquerdo, clique em **"Pages"**

3. Em **"Source"** (Fonte):
   - **Branch**: Selecione `main`
   - **Folder**: Deixe `/ (root)`

4. Clique em **"Save"**

5. **Aguarde 1-5 minutos**

6. Atualize a página. Você verá uma mensagem:

   > ✅ Your site is published at `https://username.github.io/meu-portfolio`

7. **Clique no link** e veja seu portfólio ONLINE! 🎉

---

## B.5 - Domínio Customizado (Opcional)

Quer um domínio próprio tipo `www.meunome.com.br`?

### Passo 1: Registrar um Domínio

Você precisa **comprar** um domínio. Opções populares:

- [Registro.br](https://registro.br) - Domínios `.br` (mais barato no Brasil)
- [Hostinger](https://hostinger.com.br)
- [GoDaddy](https://godaddy.com)

**Preço**: Geralmente R$ 40-80 por ano.

### Passo 2: Configurar DNS

No painel do seu provedor de domínio:

1. Acesse **"Gerenciar DNS"** ou **"DNS Settings"**

2. Adicione um registro **CNAME**:
   - **Tipo**: CNAME
   - **Host/Nome**: `www`
   - **Valor/Aponta para**: `username.github.io`
   - **TTL**: 3600 (ou deixe padrão)

3. **Salve** as configurações

### Passo 3: Configurar no GitHub Pages

1. Volte nas **Settings** → **Pages** do seu repositório

2. Em **"Custom domain"**, digite: `www.meunome.com.br`

3. Clique em **"Save"**

4. Aguarde alguns minutos. O GitHub vai verificar o DNS.

5. Quando aparecer ✅, marque **"Enforce HTTPS"** (força conexão segura)

6. **Pronto!** Seu site agora está em `www.meunome.com.br` 🚀

**Tempo de propagação DNS**: Pode levar de minutos até 48 horas (geralmente é rápido).

---

## B.6 - GitHub Actions (Deploy Automático)

GitHub Actions são "robôs" que executam tarefas automaticamente quando você faz mudanças no código.

### Caso de Uso

Toda vez que você fizer `git push`, o GitHub pode:

- ✅ Validar seu HTML
- ✅ Verificar erros no JavaScript
- ✅ Fazer deploy automático

### Criando um Workflow Simples

1. No seu repositório, crie a pasta `.github/workflows/`

2. Dentro dela, crie um arquivo `deploy.yml`:

```yaml
name: Deploy Portfolio

# Quando executar: a cada push na branch main
on:
  push:
    branches: [main]

# Tarefas a executar
jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      # 1. Fazer checkout do código
      - name: Checkout código
        uses: actions/checkout@v3

      # 2. Validar HTML (exemplo)
      - name: Validar HTML
        run: |
          echo "✅ Validando HTML..."
          # Aqui você pode adicionar validadores reais

      # 3. Mensagem de sucesso
      - name: Deploy concluído
        run: echo "🚀 Deploy automático via GitHub Pages"
```

3. **Commit e push** deste arquivo

4. Vá em **"Actions"** no GitHub e veja seu workflow rodando!

### Entendendo o YAML

```yaml
name: Nome do workflow

on:
  push: # Evento que dispara
    branches: [main] # Apenas na branch main

jobs: # Tarefas
  deploy: # Nome do job
    runs-on: ubuntu-latest # Sistema operacional

    steps: # Passos do job
      - name: Passo 1
        uses: acao@versao # Usa uma "action" pronta

      - name: Passo 2
        run: comando # Executa um comando
```

---

## B.7 - Atualizando seu Site

Sempre que quiser atualizar o portfólio:

### Via Interface Web:

1. No GitHub, clique no arquivo (ex: `index.html`)
2. Clique no ícone de lápis (Edit)
3. Faça suas mudanças
4. Clique em "Commit changes"
5. Aguarde ~1 minuto → site atualizado!

### Via Git Local:

```bash
# 1. Faça as mudanças nos arquivos localmente

# 2. Adicione ao stage
git add .

# 3. Commit
git commit -m "Atualizar seção de projetos"

# 4. Push para GitHub
git push

# 5. Aguarde ~1 minuto → site atualizado!
```

---

# 🎉 Conclusão

**Parabéns!** 🎊 Você construiu um portfólio completo do zero e aprendeu:

✅ **HTML5 Semântico** - Estrutura organizada e acessível  
✅ **CSS Moderno** - Variáveis, Flexbox, animações  
✅ **JavaScript Vanilla** - Manipulação de DOM, arrays, métodos  
✅ **`.map()`, `.filter()`, `.sort()`** - Transformação de dados  
✅ **Event Listeners** - Interatividade  
✅ **Git & GitHub** - Controle de versão  
✅ **GitHub Pages** - Deploy gratuito

---

## 🚀 Próximos Passos

### Nível Intermediário:

- [ ] Adicionar **localStorage** para salvar preferências do usuário
- [ ] Criar um **tema escuro** (dark mode) com botão toggle
- [ ] Adicionar **animações** ao rolar a página (scroll animations)
- [ ] Consumir uma **API externa** (ex: GitHub API para mostrar seus repositórios reais)

### Nível Avançado:

- [ ] Aprender **React** ou **Vue.js** para projetos maiores
- [ ] Estudar **TypeScript** para código mais robusto
- [ ] Explorar **build tools** (Vite, Webpack)
- [ ] Implementar **testes automatizados**

---

# 🎯 Desafios de Extensão

Parabéns por completar o tutorial! Agora teste suas habilidades com estes desafios práticos:

---

## Desafio 1: Sistema de Busca ⭐

**Objetivo**: Adicionar uma barra de busca que filtra experiências em tempo real enquanto o usuário digita.

**Requisitos**:

- Input de texto acima da lista de experiências
- Filtrar por cargo, empresa ou descrição
- Atualizar a lista instantaneamente (sem botão "buscar")
- Mostrar mensagem "Nenhum resultado encontrado" quando apropriado

**Dicas para começar**:

<details>
<summary>Clique para ver as dicas</summary>

1. **HTML**: Adicione um `<input>` com id único
2. **JavaScript**: Use `addEventListener('input', ...)` para capturar cada tecla digitada
3. **Lógica**: Use `.filter()` para verificar se o texto buscado aparece em `cargo`, `empresa` ou `descricao`
4. **Case-insensitive**: Use `.toLowerCase()` no texto buscado e nos campos

**Estrutura básica**:

```javascript
const inputBusca = document.getElementById("busca-experiencias");

inputBusca.addEventListener("input", (evento) => {
  const termoBusca = evento.target.value.toLowerCase();

  const resultados = experiencias.filter((exp) => {
    // Verifica se o termo aparece em algum campo
    return (
      exp.cargo.toLowerCase().includes(termoBusca) ||
      exp.empresa.toLowerCase().includes(termoBusca) ||
      exp.descricao.toLowerCase().includes(termoBusca)
    );
  });

  // Re-renderizar com os resultados filtrados
  renderizarExperiencias(resultados);
});
```

</details>

<details>
<summary>Ver solução completa</summary>

**HTML**:

```html
<section class="experiencias" id="experiencias">
  <div class="container">
    <h2>Experiências Profissionais</h2>

    <!-- Barra de busca -->
    <div class="busca-container">
      <input
        type="text"
        id="busca-experiencias"
        placeholder="Buscar por cargo, empresa ou descrição..."
        class="input-busca"
      />
    </div>

    <!-- Container das experiências -->
    <div id="container-experiencias"></div>

    <!-- Mensagem quando não há resultados -->
    <p
      id="sem-resultados"
      style="display: none; text-align: center; color: #636e72;"
    >
      Nenhuma experiência encontrada.
    </p>
  </div>
</section>
```

**CSS**:

```css
.busca-container {
  margin-bottom: 30px;
}

.input-busca {
  width: 100%;
  padding: 15px 20px;
  font-size: 1rem;
  border: 2px solid var(--cor-primaria);
  border-radius: var(--border-radius);
  outline: none;
  transition: all 0.3s ease;
}

.input-busca:focus {
  box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.1);
}
```

**JavaScript**:

```javascript
// Função reutilizável para renderizar experiências
function renderizarExperiencias(lista) {
  const containerExperiencias = document.getElementById(
    "container-experiencias",
  );
  const semResultados = document.getElementById("sem-resultados");

  if (lista.length === 0) {
    containerExperiencias.innerHTML = "";
    semResultados.style.display = "block";
    return;
  }

  semResultados.style.display = "none";

  const cardsHTML = lista
    .sort((a, b) => b.ano - a.ano)
    .map((exp) => {
      return `
        <div class="card-experiencia">
          <span class="badge ${exp.tipo}">${exp.tipo === "atual" ? "ATUAL" : "PASSADA"}</span>
          <h3>${exp.cargo}</h3>
          <p class="empresa">${exp.empresa}</p>
          <p class="periodo">${exp.periodo}</p>
          <p class="descricao">${exp.descricao}</p>
        </div>
      `;
    });

  containerExperiencias.innerHTML = cardsHTML.join("");
}

// Sistema de busca
const inputBusca = document.getElementById("busca-experiencias");

inputBusca.addEventListener("input", (evento) => {
  const termoBusca = evento.target.value.toLowerCase().trim();

  // Se o campo está vazio, mostra todas
  if (termoBusca === "") {
    renderizarExperiencias(experiencias);
    return;
  }

  // Filtra experiências que contenham o termo
  const resultados = experiencias.filter((exp) => {
    return (
      exp.cargo.toLowerCase().includes(termoBusca) ||
      exp.empresa.toLowerCase().includes(termoBusca) ||
      exp.descricao.toLowerCase().includes(termoBusca)
    );
  });

  renderizarExperiencias(resultados);
});

// Renderizar todas ao carregar
renderizarExperiencias(experiencias);
```

**Melhorias possíveis**:

- Adicionar debounce (aguardar 300ms após parar de digitar antes de filtrar)
- Destacar o termo buscado nos resultados
- Adicionar ícone de lupa no input
- Mostrar contador de resultados encontrados

</details>

---

## Desafio 2: Contador de Visitas Local (Analytics mini-challenge) ⭐⭐

**Objetivo**: Implementar um contador simples que registra quantas vezes a página foi aberta no navegador do usuário (persistência via localStorage). É uma introdução leve a conceitos de analytics sem backend.

**Requisitos**:

- Incrementar um contador a cada visita/refresh
- Salvar o contador em localStorage
- Exibir um texto no header com o número de visitas (ex.: "Suas visitas: 12")

**Dicas**:

<details>
<summary>Clique para ver as dicas</summary>

1. Use uma chave previsível no localStorage, por exemplo `visitas_portfolio`.
2. Ao carregar a página, leia o valor, converta para número (ou 0) e incremente.
3. Atualize o DOM com o novo valor e salve novamente no localStorage.

```javascript
// Exemplo mínimo
const key = "visitas_portfolio";
const visitas = Number(localStorage.getItem(key) || "0") + 1;
localStorage.setItem(key, String(visitas));
document.getElementById("contador-visitas").textContent =
  `Suas visitas: ${visitas}`;
```

</details>

<details>
<summary>Ver solução sugerida</summary>

**HTML** (adicione no header):

```html
<div id="contador-visitas" class="contador-visitas">Suas visitas: 0</div>
```

**JavaScript (vanilla)**:

```javascript
// Contador de visitas local
const VISITAS_KEY = "visitas_portfolio";
function incrementarVisita() {
  const atual = Number(localStorage.getItem(VISITAS_KEY) || "0");
  const novo = atual + 1;
  localStorage.setItem(VISITAS_KEY, String(novo));
  const el = document.getElementById("contador-visitas");
  if (el) el.textContent = `Suas visitas: ${novo}`;
}

// Chamar ao carregar
incrementarVisita();
```

**Melhorias possíveis**:

- Mostrar última visita (timestamp)
- Reset manual do contador (botão de debug)
- Separar por seção (contar visitas por página)

</details>

---

## Desafio 3: Exportar Currículo/Portfólio em PDF ⭐⭐

**Objetivo**: Adicionar um botão que permita exportar (imprimir) uma versão do seu currículo/portfólio em PDF. Sugerimos começar com window.print() e, se quiser, experimentar bibliotecas como html2pdf ou jsPDF.

**Requisitos**:

- Botão "Exportar PDF" visível na página
- Versão imprimível via CSS (@media print) para esconder elementos desnecessários
- Acionar a função de impressão do navegador com window.print()

<details>
<summary>Dicas</summary>

1. Use uma folha de estilos para impressão: `@media print` para ajustar fontes, cores e esconder elementos (nav, botões).
2. `window.print()` abre o diálogo de impressão do navegador — o usuário pode salvar como PDF.
3. Para controle mais avançado (layout, margens), experimente html2pdf ou jsPDF.

</details>

<details>
<summary>Ver exemplo (vanilla)</summary>

**HTML** (botão):

```html
<button id="export-pdf" class="btn">Exportar PDF</button>
```

**CSS** (impressão):

```css
@media print {
  .btn,
  .navegacao,
  .filtros,
  .contato-links {
    display: none !important;
  }
  body {
    color: #000;
    background: #fff;
  }
  /* Ajustes adicionais: fontes, tamanhos e margens */
}
```

**JavaScript**:

```javascript
document.getElementById("export-pdf").addEventListener("click", () => {
  window.print();
});
```

**Alternativa com html2pdf (opcional)**:

```html
<!-- incluir via CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.9.2/html2pdf.bundle.min.js"></script>
```

```javascript
const el = document.getElementById("main-content");
html2pdf().from(el).save("meu-portfolio.pdf");
```

</details>

---

---

## Desafio 3: Animação ao Scroll ⭐⭐⭐

**Objetivo**: Cards aparecem com animação suave quando o usuário rola a página e eles entram na tela.

**Requisitos**:

- Cards invisíveis inicialmente
- Aparecem com fade-in + slide up quando visíveis
- Usar `Intersection Observer API` (não `scroll` event)

**Dicas**:

<details>
<summary>Clique para ver as dicas</summary>

**Intersection Observer**: API moderna que detecta quando um elemento entra/sai da viewport (área visível).

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      // Elemento está visível
      entry.target.classList.add("visivel");
    }
  });
});

// Observar um elemento
observer.observe(elemento);
```

**Estratégia**:

1. CSS: Cards começam com `opacity: 0` e `transform: translateY(50px)`
2. CSS: Classe `.visivel` anima para `opacity: 1` e `transform: translateY(0)`
3. JS: Use `IntersectionObserver` para adicionar `.visivel` quando card entra na tela

</details>

<details>
<summary>Ver solução completa</summary>

**CSS**:

```css
.card-experiencia {
  /* Estilos existentes... */

  /* Animação ao scroll */
  opacity: 0;
  transform: translateY(50px);
  transition:
    opacity 0.6s ease,
    transform 0.6s ease;
}

.card-experiencia.visivel {
  opacity: 1;
  transform: translateY(0);
}

/* Delay progressivo para efeito cascata */
.card-experiencia:nth-child(1) {
  transition-delay: 0s;
}
.card-experiencia:nth-child(2) {
  transition-delay: 0.1s;
}
.card-experiencia:nth-child(3) {
  transition-delay: 0.2s;
}
.card-experiencia:nth-child(4) {
  transition-delay: 0.3s;
}
```

**JavaScript**:

```javascript
// Função para configurar animações de scroll
function configurarAnimacoesScroll() {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          // Elemento entrou na tela
          entry.target.classList.add("visivel");

          // (Opcional) Para de observar após animar
          observer.unobserve(entry.target);
        }
      });
    },
    {
      // Configurações
      threshold: 0.1, // Quando 10% do elemento estiver visível
      rootMargin: "0px 0px -50px 0px", // Margem inferior para animar antes
    },
  );

  // Observar todos os cards
  const cards = document.querySelectorAll(".card-experiencia");
  cards.forEach((card) => observer.observe(card));
}

// Chamar após renderizar experiências
function renderizarExperiencias(lista) {
  // ... código de renderização existente ...

  containerExperiencias.innerHTML = cardsHTML.join("");

  // Configurar animações após renderizar
  setTimeout(() => {
    configurarAnimacoesScroll();
  }, 50); // Pequeno delay para garantir que DOM atualizou
}
```

**Nota**: Se você usar busca/filtros, chame `configurarAnimacoesScroll()` toda vez que re-renderizar!

</details>

---

## Desafio 4: Dark Mode ⭐⭐⭐

**Objetivo**: Implementar tema escuro com toggle e persistência no localStorage.

**Requisitos**:

- Botão para alternar entre claro/escuro
- Salvar preferência no localStorage
- Carregar tema salvo ao abrir a página
- (Opcional) Detectar preferência do sistema operacional

**Dicas**:

<details>
<summary>Clique para ver as dicas</summary>

**Estratégia**:

1. Crie variáveis CSS para tema escuro em `.dark-mode`
2. Use JavaScript para adicionar/remover classe `dark-mode` no `<body>`
3. Salve preferência no localStorage
4. Carregue ao iniciar a página

**Detectar preferência do SO**:

```javascript
const prefereDarkMode = window.matchMedia(
  "(prefers-color-scheme: dark)",
).matches;
```

</details>

<details>
<summary>Ver solução completa</summary>

**HTML** (adicione no header):

```html
<button id="toggle-tema" class="btn-tema" title="Alternar tema">🌙</button>
```

**CSS**:

```css
/* Variáveis para tema claro (padrão) */
:root {
  --cor-primaria: #6c5ce7;
  --cor-secundaria: #00b894;
  --cor-texto: #2d3436;
  --cor-texto-claro: #636e72;
  --cor-fundo: #f5f6fa;
  --cor-branco: #ffffff;
}

/* Variáveis para tema escuro */
body.dark-mode {
  --cor-texto: #f5f6fa;
  --cor-texto-claro: #b2bec3;
  --cor-fundo: #2d3436;
  --cor-branco: #34495e;
}

/* Botão de tema */
.btn-tema {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: none;
  background: var(--cor-primaria);
  color: var(--cor-branco);
  font-size: 1.5rem;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
  z-index: 1000;
}

.btn-tema:hover {
  transform: scale(1.1);
}

/* Transição suave ao trocar tema */
body {
  transition:
    background-color 0.3s ease,
    color 0.3s ease;
}
```

**JavaScript**:

```javascript
// ========== DARK MODE ==========

// Carregar tema salvo (ou detectar preferência do SO)
function carregarTema() {
  const temaSalvo = localStorage.getItem("tema");

  if (temaSalvo) {
    // Usar tema salvo
    if (temaSalvo === "dark") {
      document.body.classList.add("dark-mode");
      atualizarIconeTema();
    }
  } else {
    // Detectar preferência do sistema operacional
    const prefereDark = window.matchMedia(
      "(prefers-color-scheme: dark)",
    ).matches;
    if (prefereDark) {
      document.body.classList.add("dark-mode");
      atualizarIconeTema();
    }
  }
}

// Alternar tema
function toggleTema() {
  document.body.classList.toggle("dark-mode");

  // Salvar preferência
  const isDark = document.body.classList.contains("dark-mode");
  localStorage.setItem("tema", isDark ? "dark" : "light");

  atualizarIconeTema();
}

// Atualizar ícone do botão
function atualizarIconeTema() {
  const btnTema = document.getElementById("toggle-tema");
  const isDark = document.body.classList.contains("dark-mode");
  btnTema.textContent = isDark ? "☀️" : "🌙";
  btnTema.title = isDark ? "Tema claro" : "Tema escuro";
}

// Event listener
document.getElementById("toggle-tema").addEventListener("click", toggleTema);

// Carregar tema ao iniciar
carregarTema();
```

**Melhorias possíveis**:

- Animação de transição mais elaborada
- Mais variações de cores para tema escuro
- Botão com animação de rotação ao trocar
- Respeitar mudanças de preferência do SO em tempo real

</details>

---

## 🏆 Desafio Bônus: Combine Tudo! ⭐⭐⭐⭐

**Objetivo**: Crie um portfólio completo com TODOS os recursos acima:

- Busca em tempo real
- Favoritos persistentes
- Animações ao scroll
- Dark mode
- **MAIS**: Adicione seções de Projetos e Skills seguindo os mesmos padrões!

**Este é o desafio final.** Se você conseguir implementar tudo isso, você dominou JavaScript vanilla! 🎉

---

## 📚 Recursos Adicionais

### Documentação Oficial:

- [MDN Web Docs](https://developer.mozilla.org/) - A melhor referência web
- [JavaScript.info](https://javascript.info/) - Tutorial completo de JS

### Prática:

- [FreeCodeCamp](https://freecodecamp.org/) - Exercícios gratuitos
- [Frontend Mentor](https://frontendmentor.io/) - Desafios de UI

### Comunidades:

- [Stack Overflow](https://stackoverflow.com/) - Tirar dúvidas
- [Dev.to](https://dev.to/) - Artigos e discussões
- [GitHub](https://github.com/) - Explorar código open-source

---

## 📖 Glossário de Termos

### Conceitos Fundamentais

**DOM (Document Object Model)**  
Representação em árvore da estrutura HTML que o JavaScript pode manipular. Pense nele como uma "ponte" entre seu código JS e os elementos da página.

**Array**  
Lista ordenada de elementos. Ex: `[1, 2, 3]` ou `['HTML', 'CSS', 'JS']`  
Acessado por índice: `array[0]` retorna o primeiro elemento.

**Objeto**  
Estrutura de dados com pares chave-valor. Ex: `{ nome: 'João', idade: 25 }`  
Acessado por chave: `objeto.nome` retorna `'João'`.

**JSON (JavaScript Object Notation)**  
Formato de texto para representar dados estruturados. Muito usado em APIs.  
Ex: `{"nome": "João", "idade": 25}`

---

### JavaScript

**Template Literal**  
String delimitada por crases (\`) que permite interpolação de variáveis.  
Ex: `` `Olá, ${nome}!` `` — a variável `nome` é inserida na string.

**Arrow Function**  
Sintaxe moderna e concisa de função em JavaScript.  
Ex: `(x) => x * 2` é equivalente a `function(x) { return x * 2; }`

**Callback**  
Função passada como argumento para outra função.  
Ex: `array.map((item) => ...)` — a arrow function é o callback.

**Method Chaining**  
Encadeamento de métodos aplicados sequencialmente.  
Ex: `array.filter().map().join()` — resultado de um vira entrada do próximo.

**Event Listener**  
"Ouvinte" de eventos que executa código quando algo acontece (clique, tecla, scroll, etc.).  
Ex: `button.addEventListener('click', () => { ... })`

**Scope (Escopo)**  
Contexto onde variáveis são acessíveis. Variáveis declaradas dentro de funções são locais (não existem fora).

**Hoisting**  
Comportamento do JavaScript que "move" declarações para o topo do escopo. `var` sofre hoisting, `let` e `const` não.

**Destructuring (Desestruturação)**  
Sintaxe para extrair valores de arrays/objetos.  
Ex: `const { nome, idade } = pessoa;` pega as propriedades diretamente.

---

### Métodos de Array

**.map()**  
Transforma cada elemento do array e retorna um novo array.  
Ex: `[1, 2, 3].map(n => n * 2)` → `[2, 4, 6]`

**.filter()**  
Filtra elementos que passam em um teste, retorna novo array.  
Ex: `[1, 2, 3, 4].filter(n => n > 2)` → `[3, 4]`

**.sort()**  
Ordena os elementos do array (modifica o original!).  
Ex: `[3, 1, 2].sort((a, b) => a - b)` → `[1, 2, 3]`

**.reduce()**  
Reduz array a um único valor aplicando função acumuladora.  
Ex: `[1, 2, 3].reduce((acc, n) => acc + n, 0)` → `6` (soma)

**.join()**  
Junta elementos do array em uma string.  
Ex: `['a', 'b', 'c'].join('-')` → `"a-b-c"`

**.find()**  
Retorna o primeiro elemento que passa no teste (ou `undefined`).  
Ex: `[1, 2, 3].find(n => n > 1)` → `2`

**.includes()**  
Verifica se array contém um valor.  
Ex: `[1, 2, 3].includes(2)` → `true`

---

### CSS

**Flexbox**  
Sistema de layout CSS para organizar elementos de forma flexível em linhas ou colunas.  
Propriedades principais: `display: flex`, `justify-content`, `align-items`.

**CSS Variables (Custom Properties)**  
Variáveis reutilizáveis em CSS.  
Ex: `:root { --cor: #6c5ce7; }` depois `color: var(--cor);`

**Box Model**  
Modelo que define como tamanho de elementos é calculado: content + padding + border + margin.

**Pseudo-classe**  
Seletor CSS que aplica estilos em estados específicos.  
Ex: `:hover` (mouse em cima), `:focus` (elemento focado), `:nth-child()` (posição).

**Media Query**  
Regra CSS aplicada apenas em condições específicas (tamanho de tela, orientação, etc.).  
Ex: `@media (max-width: 768px) { ... }` — aplica apenas em telas pequenas.

**z-index**  
Propriedade que controla profundidade (qual elemento fica "na frente").  
Valores maiores ficam em cima. Só funciona com `position` diferente de `static`.

---

### Git & GitHub

**Git**  
Sistema de controle de versão distribuído que registra histórico de mudanças no código.

**Commit**  
"Snapshot" (foto) do código em um momento específico. Cada commit tem uma mensagem descritiva.

**Branch (Ramificação)**  
Linha independente de desenvolvimento. A branch `main` é geralmente a principal.

**Repository (Repositório)**  
Pasta que contém seu projeto + histórico Git (`.git`).

**Clone**  
Copiar um repositório remoto para sua máquina local.  
Ex: `git clone https://github.com/usuario/repo.git`

**Push**  
Enviar commits locais para um repositório remoto.  
Ex: `git push origin main`

**Pull**  
Baixar e integrar mudanças de um repositório remoto.  
Ex: `git pull origin main`

**Merge**  
Unir duas branches diferentes. Pode gerar conflitos se as mesmas linhas foram editadas.

**Pull Request (PR)**  
Proposta de mudança no GitHub. Permite code review antes de fazer merge.

---

### Desenvolvimento Web

**Deploy**  
Publicar/hospedar o site para ficar acessível online (ex: no GitHub Pages, Vercel, Netlify).

**Localhost**  
Servidor local na sua máquina. `http://localhost:3000` significa porta 3000 no seu computador.

**API (Application Programming Interface)**  
Interface que permite comunicação entre sistemas. Ex: API do GitHub fornece dados de repositórios.

**CORS (Cross-Origin Resource Sharing)**  
Política de segurança que controla quais sites podem acessar recursos de outro domínio.

**CDN (Content Delivery Network)**  
Rede de servidores distribuídos geograficamente que entregam conteúdo mais rápido.

**Responsivo**  
Design que se adapta a diferentes tamanhos de tela (desktop, tablet, celular).

**SEO (Search Engine Optimization)**  
Otimização para motores de busca (Google, Bing). HTML semântico melhora SEO.

**Bundle**  
Arquivo final gerado após empacotar/minificar código (JS, CSS). Menor = carrega mais rápido.

**Cache**  
Armazenamento temporário de dados para acesso mais rápido. Navegadores fazem cache de imagens, CSS, JS.

**localStorage**  
API do navegador que armazena dados localmente (não expira). Máximo ~5-10MB.  
Ex: `localStorage.setItem('chave', 'valor')`

**sessionStorage**  
Similar ao localStorage, mas dados expiram quando a aba é fechada.

**Cookies**  
Pequenos arquivos de texto armazenados pelo navegador. Enviados em cada requisição ao servidor.

---

### Ferramentas

**npm (Node Package Manager)**  
Gerenciador de pacotes do JavaScript. Instala bibliotecas de terceiros.  
Ex: `npm install biblioteca`

**package.json**  
Arquivo que lista dependências, scripts e metadados do projeto Node.js.

**DevTools**  
Ferramentas de desenvolvedor do navegador (F12). Console, Network, Elements, etc.

**Linter**  
Ferramenta que analisa código e aponta erros/más práticas. Ex: ESLint para JavaScript.

**Hot Reload**  
Atualização automática do navegador ao salvar arquivos (sem F5 manual).

**Minificação**  
Processo de remover espaços, comentários e encurtar nomes para reduzir tamanho do arquivo.

---

**Bons estudos e bons códigos!** 💻✨

Se tiver dúvidas, a comunidade de desenvolvimento é super acolhedora. Não tenha medo de perguntar!
