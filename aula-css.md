# Aula Completa de CSS

## Introdução ao CSS

CSS (Cascading Style Sheets ou Folhas de Estilo em Cascata) é uma linguagem de estilização utilizada para definir a apresentação visual de documentos HTML. Se o HTML é responsável pela estrutura e conteúdo, o CSS é responsável pela aparência.

## Formas de Incluir CSS

Existem três maneiras de adicionar CSS a uma página HTML:

### 1. CSS Inline

O CSS inline é aplicado diretamente em elementos HTML usando o atributo `style`.

```html
<!-- CSS Inline -->
<p style="color: blue; font-size: 16px; margin-top: 10px;">
    Este é um parágrafo com estilo inline.
</p>
<!-- O estilo é aplicado diretamente no elemento usando o atributo style -->
```

### 2. CSS Interno (ou Incorporado)

O CSS interno é definido dentro da tag `<style>` no cabeçalho (`<head>`) do documento HTML.

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Interno</title>
    <!-- CSS Interno -->
    <style>
        /* Todo conteúdo aqui é CSS */
        body {
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
        }

## Frameworks CSS e Metodologias

Existem várias metodologias e frameworks que ajudam a organizar e padronizar seu CSS em projetos maiores.

### Metodologias CSS

#### BEM (Block Element Modifier)

BEM é uma metodologia de nomenclatura que ajuda a criar componentes reutilizáveis e código compartilhável.

```css
/* Bloco */
.card {
    background: white;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* Elemento (componente do bloco) */
.card__title {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 10px;
}

.card__image {
    width: 100%;
    border-radius: 4px 4px 0 0;
}

.card__content {
    padding: 15px;
}

/* Modificador (variação do bloco ou elemento) */
.card--featured {
    border: 2px solid gold;
}

.card__title--large {
    font-size: 24px;
}
```

HTML correspondente:
```html
<div class="card card--featured">
    <img class="card__image" src="imagem.jpg" alt="Descrição">
    <div class="card__content">
        <h2 class="card__title card__title--large">Título do Card</h2>
        <p class="card__text">Conteúdo do card...</p>
    </div>
</div>
```

#### SMACSS (Scalable and Modular Architecture for CSS)

SMACSS divide o CSS em cinco categorias:

1. Base - Estilos padrão (reset, elementos HTML)
2. Layout - Divisão da página em seções
3. Module - Componentes reutilizáveis 
4. State - Estados dos elementos (active, hidden)
5. Theme - Temas visuais

#### OOCSS (Object-Oriented CSS)

OOCSS foca em dois princípios principais:
1. Separar estrutura e aparência
2. Separar container e conteúdo

### Frameworks CSS Populares

#### Bootstrap

Bootstrap é um dos frameworks CSS mais populares, oferecendo um sistema de grid responsivo e componentes pré-estilizados.

```html
<div class="container">
    <div class="row">
        <div class="col-md-4">Coluna 1</div>
        <div class="col-md-4">Coluna 2</div>
        <div class="col-md-4">Coluna 3</div>
    </div>
</div>
```

#### Tailwind CSS

Tailwind CSS utiliza classes utilitárias para construir designs diretamente no HTML.

```html
<div class="bg-white rounded-lg shadow-md p-6 m-4">
    <h2 class="text-xl font-bold text-blue-600 mb-4">Título do Card</h2>
    <p class="text-gray-700">Conteúdo do card...</p>
    <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Saiba mais
    </button>
</div>
```

## Pré-processadores CSS

Os pré-processadores CSS estendem a funcionalidade do CSS com recursos como variáveis, aninhamento, mixins, funções e mais.

### SASS/SCSS

SCSS é uma sintaxe do SASS (Syntactically Awesome Style Sheets) que adiciona recursos poderosos ao CSS.

```scss
// Variáveis
$cor-primaria: #3498db;
$cor-secundaria: #2ecc71;
$espacamento-padrao: 16px;

// Aninhamento
.card {
    background: white;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: $espacamento-padrao;
    
    // Elementos aninhados
    &__title {
        color: $cor-primaria;
        font-size: 18px;
        margin-bottom: $espacamento-padrao / 2;
    }
    
    &__content {
        padding: $espacamento-padrao;
    }
    
    // Pseudo-classes aninhadas
    &:hover {
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
    
    // Modificadores
    &--featured {
        border: 2px solid $cor-secundaria;
    }
}

// Mixins
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    @include flex-center;
    flex-direction: column;
}

// Extensão/Herança
.botao {
    padding: 10px 15px;
    border-radius: 4px;
    border: none;
    cursor: pointer;
}

.botao-primario {
    @extend .botao;
    background-color: $cor-primaria;
    color: white;
}

.botao-secundario {
    @extend .botao;
    background-color: $cor-secundaria;
    color: white;
}

// Funções e operações
$largura-padrao: 1200px;

.container {
    max-width: $largura-padrao;
    padding: 0 $espacamento-padrao * 2;
}

// Condicionais
@mixin tema($modo) {
    @if $modo == 'claro' {
        background-color: white;
        color: #333;
    } @else {
        background-color: #333;
        color: white;
    }
}

.tema-claro {
    @include tema('claro');
}

.tema-escuro {
    @include tema('escuro');
}

// Loops
@for $i from 1 through 6 {
    .text-#{$i} {
        font-size: 10px + (2px * $i);
    }
}
```

### LESS

LESS é outro pré-processador popular com recursos semelhantes ao SASS.

```less
// Variáveis
@cor-primaria: #3498db;
@cor-secundaria: #2ecc71;
@espacamento-padrao: 16px;

// Aninhamento
.card {
    background: white;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    
    // Elementos aninhados
    .card-title {
        color: @cor-primaria;
        font-size: 18px;
    }
    
    // Pseudo-classes
    &:hover {
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    }
}

// Mixins
.border-radius(@radius) {
    border-radius: @radius;
    -webkit-border-radius: @radius;
    -moz-border-radius: @radius;
}

.button {
    .border-radius(4px);
    background-color: @cor-primaria;
}

// Operações
.container {
    width: 100%;
    max-width: 1200px - 40px;
    padding: @espacamento-padrao * 2;
}
```

## CSS Moderno - Propriedades Avançadas

### Box Model Alternativo

```css
.box {
    /* Altera como o box-model é calculado */
    box-sizing: border-box; /* Incluir padding e border na largura/altura */
}

/* Aplicar border-box a todos os elementos */
*, *::before, *::after {
    box-sizing: border-box;
}
```

### Colunas Múltiplas

```css
.texto-colunas {
    /* Divide o texto em múltiplas colunas */
    column-count: 3;             /* Número de colunas */
    column-gap: 30px;            /* Espaço entre colunas */
    column-rule: 1px solid #ccc; /* Linha separadora */
    
    /* Impedindo quebra de elementos específicos */
    h2 {
        column-span: all;        /* Título ocupa todas as colunas */
    }
}
```

### Máscaras CSS

```css
.elemento-mascarado {
    /* Mascara o elemento com uma imagem */
    mask-image: url('mascara.svg');
    mask-size: cover;
    mask-position: center;
    mask-repeat: no-repeat;
    
    /* Gradiente como máscara */
    mask-image: linear-gradient(to right, transparent, black);
}
```

### Filtros CSS

```css
.imagem-filtrada {
    /* Filtros individuais */
    filter: grayscale(100%);     /* Escala de cinza */
    filter: blur(5px);           /* Desfoque */
    filter: brightness(150%);    /* Brilho */
    filter: contrast(200%);      /* Contraste */
    filter: hue-rotate(90deg);   /* Rotação de matiz */
    filter: invert(100%);        /* Inversão de cores */
    filter: opacity(50%);        /* Opacidade */
    filter: saturate(200%);      /* Saturação */
    filter: sepia(100%);         /* Sépia */
    filter: drop-shadow(5px 5px 5px black); /* Sombra */
    
    /* Combinando filtros */
    filter: contrast(150%) brightness(120%) grayscale(50%);
}
```

### Shapes e Clips

```css
.texto-em-forma {
    /* Fluxo de texto em torno de uma forma */
    shape-outside: circle(50%);  /* Círculo */
    shape-outside: polygon(0 0, 100% 0, 50% 100%); /* Polígono personalizado */
    float: left;
    width: 200px;
    height: 200px;
}

.elemento-recortado {
    /* Recorta o elemento em uma forma específica */
    clip-path: circle(50% at 50% 50%); /* Círculo */
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%); /* Losango */
    clip-path: inset(10% 20% 10% 20%); /* Retângulo interno */
    clip-path: ellipse(25% 40% at 50% 50%); /* Elipse */
}
```

### Scroll Snap

```css
.container-scroll {
    /* Configura o container para "encaixar" o scroll */
    scroll-snap-type: y mandatory; /* y = vertical, x = horizontal */
    overflow-y: scroll;
    height: 100vh;
}

.item-scroll {
    /* Define onde o item deve "encaixar" */
    scroll-snap-align: start; /* start, center, end */
    height: 100vh;
}
```

## Boas Práticas de CSS

### 1. Organização e Estrutura

- Use uma metodologia de nomenclatura consistente (BEM, SMACSS, OOCSS)
- Organize seu CSS em arquivos separados por funcionalidade
- Crie um arquivo de reset ou normalize para consistência entre navegadores
- Mantenha uma ordem consistente nas declarações de propriedades
- Agrupe propriedades relacionadas (dimensões, tipografia, cores, etc.)

### 2. Otimização de Performance

- Combine arquivos CSS para reduzir requisições HTTP
- Minimize seu CSS para produção (remover espaços, comentários)
- Use compressão GZIP em seus servidores
- Evite seletores excessivamente aninhados
- Prefira classes ao invés de seletores de ID ou de elemento
- Evite o uso de `!important` (exceto em casos específicos)
- Utilize técnicas de carregamento crítico de CSS

### 3. Manutenção

- Documente seu código com comentários explicativos
- Use variáveis para valores recorrentes (cores, tamanhos, etc.)
- Evite repetição desnecessária de código (DRY - Don't Repeat Yourself)
- Mantenha a especificidade de seletores baixa e consistente
- Revise e refatore seu CSS regularmente

### 4. Compatibilidade

- Teste em diferentes navegadores e dispositivos
- Use prefixos de fornecedor para propriedades experimentais
- Implemente fallbacks para recursos não suportados
- Consulte tabelas de compatibilidade como o "Can I Use" (caniuse.com)

## Exercícios Práticos

### Exercício 1: Cartão de Produto

Crie um cartão de produto para uma loja online com:
- Imagem do produto
- Título
- Preço
- Descrição curta
- Botão "Adicionar ao Carrinho"
- Estilização com sombras, bordas arredondadas
- Efeito hover que destaca o cartão

### Exercício 2: Navbar Responsiva

Crie uma barra de navegação responsiva que:
- Em dispositivos desktop: mostre itens de menu horizontalmente
- Em dispositivos móveis: transforme em menu hambúrguer
- Inclua logo, links de navegação e botão de busca
- Aplique transições suaves ao alternar entre os estados

### Exercício 3: Layout Flexbox

Crie uma galeria de imagens usando Flexbox com:
- Layout responsivo que se adapta a diferentes tamanhos de tela
- Espaçamento uniforme entre os itens
- Quebra de linha quando necessário
- Centralização das imagens

### Exercício 4: Layout Grid

Crie um layout de página completo usando Grid com:
- Cabeçalho
- Menu lateral
- Conteúdo principal (dividido em seções)
- Barra lateral
- Rodapé
- Layout responsivo que se adapta a diferentes dispositivos

## Conclusão

CSS é uma linguagem poderosa que continua evoluindo com novos recursos. Dominar CSS permite criar interfaces visuais atraentes e funcionais para a web. As técnicas e conceitos abordados nesta aula formam a base para o desenvolvimento de sites modernos e responsivos.

Para continuar aprendendo, experimente:
- Praticar criando projetos reais
- Analisar o código de sites que você admira
- Acompanhar as novidades do CSS através de sites como CSS-Tricks, MDN Web Docs e Smashing Magazine
- Explorar frameworks e ferramentas como Sass, Bootstrap, Tailwind CSS

## Recursos Adicionais

- [MDN Web Docs - CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Jogo para aprender Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Jogo para aprender Grid
- [CSS Diner](https://flukeout.github.io/) - Jogo para aprender seletores CSS
        
        h1 {
            color: navy;
            text-align: center;
        }
        
        p {
            color: #333333;
            line-height: 1.5;
            margin-bottom: 20px;
        }
    </style>
    <!-- Fim do CSS Interno -->
</head>
<body>
    <h1>Título da Página</h1>
    <p>Este é um parágrafo estilizado pelo CSS interno.</p>
</body>
</html>
```

### 3. CSS Externo (Recomendado)

O CSS externo é definido em um arquivo separado com extensão `.css` e vinculado ao documento HTML usando a tag `<link>`.

**Arquivo HTML (index.html):**
```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Externo</title>
    <!-- Link para o arquivo CSS externo -->
    <link rel="stylesheet" href="estilos.css">
    <!-- O atributo rel define o tipo de relação e href aponta para o arquivo CSS -->
</head>
<body>
    <h1>Título da Página</h1>
    <p>Este é um parágrafo estilizado pelo CSS externo.</p>
</body>
</html>
```

**Arquivo CSS (estilos.css):**
```css
/* Todo o conteúdo deste arquivo é CSS */
body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

h1 {
    color: navy;
    text-align: center;
}

p {
    color: #333333;
    line-height: 1.5;
    margin-bottom: 20px;
}
```

## Sintaxe do CSS

A sintaxe do CSS consiste em um seletor e um bloco de declaração:

```css
seletor {
    propriedade: valor;
    outra-propriedade: outro-valor;
}
```

- **Seletor**: Aponta para o elemento HTML que você deseja estilizar
- **Bloco de Declaração**: Contém uma ou mais declarações separadas por ponto e vírgula
- **Declaração**: Consiste em uma propriedade e um valor, separados por dois pontos

## Seletores CSS

Os seletores determinam quais elementos serão afetados pelas regras CSS.

### Seletor de Elemento

Seleciona todos os elementos com o nome especificado.

```css
p {
    color: blue;
}
/* Aplica estilo a TODOS os elementos <p> */
```

### Seletor de ID

Seleciona um elemento com um ID específico (deve ser único na página).

```css
#cabecalho {
    background-color: black;
    color: white;
}
/* Aplica estilo ao elemento com id="cabecalho" */
```

### Seletor de Classe

Seleciona todos os elementos com uma classe específica.

```css
.destaque {
    background-color: yellow;
    font-weight: bold;
}
/* Aplica estilo a TODOS os elementos com class="destaque" */
```

### Seletor Universal

Seleciona todos os elementos do documento.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
/* Aplica estilo a TODOS os elementos */
```

### Seletor de Atributo

Seleciona elementos baseados em um atributo.

```css
input[type="text"] {
    border: 1px solid #ccc;
    padding: 5px;
}
/* Aplica estilo a todos os inputs do tipo text */

a[href^="https"] {
    color: green;
}
/* Aplica estilo a links que começam com https */

img[alt$="logo"] {
    border: none;
}
/* Aplica estilo a imagens cujo alt termina com "logo" */
```

### Seletores Combinados

#### Descendente (espaço)

```css
article p {
    text-indent: 20px;
}
/* Seleciona todos os <p> que estão dentro de <article>, independente do nível de aninhamento */
```

#### Filho Direto (>)

```css
nav > ul {
    list-style: none;
}
/* Seleciona apenas <ul> que são filhos diretos de <nav> */
```

#### Adjacente (+)

```css
h2 + p {
    font-weight: bold;
}
/* Seleciona <p> que vem imediatamente após um <h2> */
```

#### Irmãos (~)

```css
h2 ~ p {
    color: gray;
}
/* Seleciona todos os <p> que são irmãos de <h2> (vêm depois) */
```

### Pseudoclasses

Seletores especiais que selecionam elementos em estados específicos.

```css
/* Estado de elementos */
a:link {
    color: blue;
}
/* Links não visitados */

a:visited {
    color: purple;
}
/* Links visitados */

a:hover {
    text-decoration: underline;
}
/* Mouse sobre o link */

a:active {
    color: red;
}
/* Link sendo clicado */

/* Posição estrutural */
li:first-child {
    font-weight: bold;
}
/* Primeiro item de uma lista */

li:last-child {
    margin-bottom: 0;
}
/* Último item de uma lista */

p:nth-child(odd) {
    background-color: #f0f0f0;
}
/* Parágrafos em posições ímpares */

/* Estados de formulário */
input:focus {
    border-color: blue;
    outline: none;
}
/* Campo com foco */

input:disabled {
    background-color: #dddddd;
}
/* Campo desabilitado */

input:checked {
    margin-left: 25px;
}
/* Checkbox ou radio button marcado */
```

### Pseudoelementos

Permitem estilizar partes específicas de um elemento.

```css
p::first-letter {
    font-size: 2em;
    font-weight: bold;
}
/* Primeira letra de cada parágrafo */

p::first-line {
    font-variant: small-caps;
}
/* Primeira linha de cada parágrafo */

h2::before {
    content: "➤ ";
    color: blue;
}
/* Adiciona conteúdo antes do elemento */

h2::after {
    content: " ✓";
    color: green;
}
/* Adiciona conteúdo depois do elemento */

::selection {
    background-color: yellow;
    color: black;
}
/* Estiliza o texto quando selecionado pelo usuário */
```

## Propriedades CSS Fundamentais

### Cores

```css
/* Diferentes formas de definir cores */
.elemento1 {
    color: red;                  /* Nome da cor */
    background-color: #00ff00;   /* Hexadecimal */
    border-color: rgb(0, 0, 255); /* RGB */
}

.elemento2 {
    color: rgba(255, 0, 0, 0.5);  /* RGBA (com transparência) */
    background-color: hsl(120, 100%, 50%); /* HSL (matiz, saturação, luminosidade) */
    border-color: hsla(240, 100%, 50%, 0.5); /* HSLA (com transparência) */
}
```

### Textos

```css
.estilo-texto {
    /* Propriedades de texto */
    color: #333333;                 /* Cor do texto */
    font-family: Arial, sans-serif; /* Família da fonte */
    font-size: 16px;                /* Tamanho da fonte */
    font-weight: bold;              /* Peso da fonte: normal, bold, 100-900 */
    font-style: italic;             /* Estilo da fonte: normal, italic, oblique */
    text-align: center;             /* Alinhamento: left, right, center, justify */
    text-decoration: underline;     /* Decoração: none, underline, line-through, overline */
    text-transform: uppercase;      /* Transformação: none, uppercase, lowercase, capitalize */
    line-height: 1.5;               /* Altura da linha */
    letter-spacing: 1px;            /* Espaçamento entre letras */
    word-spacing: 2px;              /* Espaçamento entre palavras */
    text-indent: 20px;              /* Recuo da primeira linha */
    text-shadow: 2px 2px 4px #000000; /* Sombra do texto: h-offset v-offset blur color */
}
```

### Fontes

```css
/* Fonte do Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');

body {
    font-family: 'Roboto', sans-serif;
}

/* Fonte local com @font-face */
@font-face {
    font-family: 'MinhaFonte';
    src: url('caminho/para/minhafonte.woff2') format('woff2'),
         url('caminho/para/minhafonte.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

h1 {
    font-family: 'MinhaFonte', Arial, sans-serif;
}
```

### Dimensões

```css
.caixa {
    /* Dimensões */
    width: 300px;               /* Largura */
    height: 200px;              /* Altura */
    min-width: 100px;           /* Largura mínima */
    max-width: 500px;           /* Largura máxima */
    min-height: 100px;          /* Altura mínima */
    max-height: 300px;          /* Altura máxima */
    
    /* Porcentagens */
    width: 50%;                 /* 50% da largura do elemento pai */
    height: 50%;                /* 50% da altura do elemento pai */
    
    /* Unidades de viewport */
    width: 50vw;                /* 50% da largura da viewport */
    height: 50vh;               /* 50% da altura da viewport */
}
```

### Margens e Preenchimento

```css
.elemento {
    /* Margens (espaço externo) */
    margin-top: 10px;           /* Margem superior */
    margin-right: 20px;         /* Margem direita */
    margin-bottom: 10px;        /* Margem inferior */
    margin-left: 20px;          /* Margem esquerda */
    
    /* Forma abreviada para margem */
    margin: 10px;               /* Aplica 10px em todos os lados */
    margin: 10px 20px;          /* 10px no topo/base, 20px na direita/esquerda */
    margin: 10px 20px 15px 25px; /* topo, direita, base, esquerda (sentido horário) */
    
    /* Centralizando horizontalmente */
    margin: 0 auto;             /* Centraliza um elemento de largura fixa */
    
    /* Preenchimento (espaço interno) */
    padding-top: 10px;          /* Preenchimento superior */
    padding-right: 20px;        /* Preenchimento direito */
    padding-bottom: 10px;       /* Preenchimento inferior */
    padding-left: 20px;         /* Preenchimento esquerdo */
    
    /* Forma abreviada para preenchimento */
    padding: 10px;              /* Aplica 10px em todos os lados */
    padding: 10px 20px;         /* 10px no topo/base, 20px na direita/esquerda */
    padding: 10px 20px 15px 25px; /* topo, direita, base, esquerda (sentido horário) */
}
```

### Bordas

```css
.borda {
    /* Propriedades individuais */
    border-width: 2px;          /* Espessura da borda */
    border-style: solid;        /* Estilo: solid, dashed, dotted, double, etc. */
    border-color: #000000;      /* Cor da borda */
    
    /* Forma abreviada */
    border: 2px solid #000000;  /* Espessura, estilo e cor */
    
    /* Lados específicos */
    border-top: 1px dashed red;
    border-right: 2px solid blue;
    border-bottom: 3px dotted green;
    border-left: 4px double orange;
    
    /* Arredondamento */
    border-radius: 5px;         /* Arredonda todos os cantos igualmente */
    border-radius: 10px 5px;    /* superior-esquerdo/inferior-direito, superior-direito/inferior-esquerdo */
    border-radius: 10px 5px 8px 15px; /* superior-esquerdo, superior-direito, inferior-direito, inferior-esquerdo */
    
    /* Arredondamento específico */
    border-top-left-radius: 10px;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 8px;
    border-bottom-left-radius: 15px;
}
```

### Fundos (Background)

```css
.fundo {
    /* Cor de fundo */
    background-color: #f0f0f0;
    
    /* Imagem de fundo */
    background-image: url('imagem.jpg');
    
    /* Repetição */
    background-repeat: no-repeat; /* no-repeat, repeat, repeat-x, repeat-y */
    
    /* Posição */
    background-position: center center; /* left, center, right, top, bottom ou valores em px/% */
    
    /* Tamanho */
    background-size: cover;     /* cover, contain ou valores em px/% */
    
    /* Anexo (como se comporta na rolagem) */
    background-attachment: fixed; /* scroll, fixed, local */
    
    /* Origem */
    background-origin: padding-box; /* border-box, padding-box, content-box */
    
    /* Forma abreviada */
    background: #f0f0f0 url('imagem.jpg') no-repeat center center/cover fixed;
    
    /* Múltiplos fundos */
    background: 
        linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
        url('imagem.jpg') no-repeat center/cover;
    
    /* Gradientes */
    background: linear-gradient(to right, red, yellow); /* Gradiente linear */
    background: radial-gradient(circle, blue, green);   /* Gradiente radial */
}
```

### Display e Visibilidade

```css
.elemento {
    /* Tipos de display */
    display: block;             /* Elemento de bloco (ocupa toda a largura disponível) */
    display: inline;            /* Elemento em linha (ocupa apenas o espaço necessário) */
    display: inline-block;      /* Misto (em linha mas aceita dimensões) */
    display: flex;              /* Layout flexível */
    display: grid;              /* Layout em grade */
    display: none;              /* Remove o elemento do fluxo (não ocupa espaço) */
    
    /* Visibilidade */
    visibility: visible;        /* Elemento visível (padrão) */
    visibility: hidden;         /* Elemento invisível (ainda ocupa espaço) */
    
    /* Overflow (comportamento quando o conteúdo ultrapassa as dimensões) */
    overflow: visible;          /* Conteúdo visível fora dos limites (padrão) */
    overflow: hidden;           /* Conteúdo cortado */
    overflow: scroll;           /* Sempre mostra barras de rolagem */
    overflow: auto;             /* Mostra barras de rolagem apenas quando necessário */
    
    /* Overflow específico */
    overflow-x: auto;           /* Controla apenas o comportamento horizontal */
    overflow-y: auto;           /* Controla apenas o comportamento vertical */
}
```

### Posicionamento

```css
.posicionamento {
    /* Tipos de posicionamento */
    position: static;           /* Posicionamento normal (padrão) */
    position: relative;         /* Relativo à sua posição normal */
    position: absolute;         /* Relativo ao ancestral posicionado mais próximo */
    position: fixed;            /* Relativo à viewport (permanece fixo durante rolagem) */
    position: sticky;           /* Misto entre relative e fixed */
    
    /* Coordenadas (usadas com position diferente de static) */
    top: 10px;                  /* Distância do topo */
    right: 20px;                /* Distância da direita */
    bottom: 10px;               /* Distância da base */
    left: 20px;                 /* Distância da esquerda */
    
    /* Ordem de empilhamento */
    z-index: 10;                /* Valor maior fica acima no empilhamento */
}
```

### Flexbox

```css
.container-flex {
    display: flex;              /* Ativa o layout flexível */
    
    /* Direção dos itens */
    flex-direction: row;        /* row (padrão), row-reverse, column, column-reverse */
    
    /* Quebra de linha */
    flex-wrap: wrap;            /* nowrap (padrão), wrap, wrap-reverse */
    
    /* Forma abreviada para direction e wrap */
    flex-flow: row wrap;
    
    /* Alinhamento no eixo principal */
    justify-content: space-between; /* flex-start, flex-end, center, space-around, space-between, space-evenly */
    
    /* Alinhamento no eixo transversal */
    align-items: center;        /* flex-start, flex-end, center, stretch, baseline */
    
    /* Alinhamento das linhas (quando há quebra) */
    align-content: space-between; /* flex-start, flex-end, center, stretch, space-around, space-between */
    
    /* Espaço entre os itens */
    gap: 10px;                  /* Espaçamento uniforme entre itens */
    row-gap: 10px;              /* Espaçamento entre linhas */
    column-gap: 20px;           /* Espaçamento entre colunas */
}

.item-flex {
    /* Ordem do item */
    order: 2;                   /* Ordem de exibição (menor valor aparece primeiro) */
    
    /* Flexibilidade de crescimento */
    flex-grow: 1;               /* Quanto o item pode crescer (0 = não cresce) */
    
    /* Flexibilidade de encolhimento */
    flex-shrink: 1;             /* Quanto o item pode encolher (0 = não encolhe) */
    
    /* Tamanho base */
    flex-basis: 200px;          /* Tamanho inicial do item antes de crescer/encolher */
    
    /* Forma abreviada para grow, shrink e basis */
    flex: 1 1 200px;            /* grow shrink basis */
    
    /* Alinhamento individual (sobrescreve align-items do contêiner) */
    align-self: flex-end;       /* flex-start, flex-end, center, stretch, baseline */
}
```

### Grid Layout

```css
.container-grid {
    display: grid;              /* Ativa o layout em grade */
    
    /* Definição explícita de linhas e colunas */
    grid-template-columns: 100px 200px auto; /* 3 colunas com tamanhos diferentes */
    grid-template-rows: 50px 100px;          /* 2 linhas com tamanhos diferentes */
    
    /* Usando a unidade fr (fração) */
    grid-template-columns: 1fr 2fr 1fr;      /* Proporção 1:2:1 */
    
    /* Função repeat */
    grid-template-columns: repeat(3, 1fr);   /* 3 colunas iguais */
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* Colunas responsivas */
    
    /* Nomeando linhas */
    grid-template-columns: [inicio] 1fr [meio] 2fr [fim];
    
    /* Espaçamento entre células */
    grid-gap: 10px;             /* Espaçamento uniforme */
    grid-row-gap: 10px;         /* Espaçamento entre linhas */
    grid-column-gap: 20px;      /* Espaçamento entre colunas */
    
    /* Forma moderna e abreviada */
    gap: 10px;
    row-gap: 10px;
    column-gap: 20px;
    
    /* Áreas da grade (layout visual) */
    grid-template-areas:
        "header header header"
        "sidebar content content"
        "footer footer footer";
    
    /* Alinhamento dos itens horizontalmente */
    justify-items: center;      /* start, end, center, stretch */
    
    /* Alinhamento dos itens verticalmente */
    align-items: center;        /* start, end, center, stretch */
    
    /* Alinhamento da grade horizontalmente */
    justify-content: space-between; /* start, end, center, stretch, space-around, space-between, space-evenly */
    
    /* Alinhamento da grade verticalmente */
    align-content: space-between; /* start, end, center, stretch, space-around, space-between, space-evenly */
}

.item-grid {
    /* Posicionamento específico usando linhas */
    grid-row: 1 / 3;            /* Linha inicial / linha final */
    grid-column: 1 / 3;         /* Coluna inicial / coluna final */
    
    /* Forma abreviada */
    grid-area: 1 / 1 / 3 / 3;   /* row-start / column-start / row-end / column-end */
    
    /* Usando nomes de áreas */
    grid-area: header;          /* Nome definido em grid-template-areas */
    
    /* Alinhamento individual horizontal */
    justify-self: center;       /* start, end, center, stretch */
    
    /* Alinhamento individual vertical */
    align-self: center;         /* start, end, center, stretch */
}
```

## Transformações e Transições

### Transformações

```css
.transformacao {
    /* Tipos de transformação */
    transform: translate(50px, 20px);  /* Move horizontalmente e verticalmente */
    transform: translateX(50px);       /* Move apenas horizontalmente */
    transform: translateY(20px);       /* Move apenas verticalmente */
    
    transform: scale(1.5);             /* Aumenta em 150% em ambos os eixos */
    transform: scaleX(1.5);            /* Aumenta apenas horizontalmente */
    transform: scaleY(0.8);            /* Diminui apenas verticalmente */
    
    transform: rotate(45deg);          /* Rotaciona 45 graus no sentido horário */
    
    transform: skew(10deg, 20deg);     /* Inclina nos eixos X e Y */
    transform: skewX(10deg);           /* Inclina apenas no eixo X */
    transform: skewY(20deg);           /* Inclina apenas no eixo Y */
    
    /* Combinando transformações */
    transform: translate(50px, 20px) rotate(45deg) scale(1.5);
    
    /* Origem da transformação */
    transform-origin: center;          /* Define o ponto de origem (padrão: center) */
    transform-origin: top left;        /* Canto superior esquerdo */
    transform-origin: 50px 30px;       /* Coordenadas específicas */
}
```

### Transições

```css
.transicao {
    /* Propriedades da transição */
    transition-property: all;          /* Propriedade a ser animada (all, opacity, transform, etc.) */
    transition-duration: 0.5s;         /* Duração da transição */
    transition-timing-function: ease;  /* Função de temporização (ease, linear, ease-in, ease-out, etc.) */
    transition-delay: 0.2s;            /* Atraso antes de iniciar */
    
    /* Forma abreviada */
    transition: all 0.5s ease 0.2s;    /* propriedade duração timing-function delay */
    
    /* Múltiplas transições */
    transition: 
        opacity 0.3s ease,
        transform 0.5s ease-in-out 0.1s;
    
    /* Estado inicial */
    opacity: 1;
    transform: translateY(0);
}

/* Estado de destino */
.transicao:hover {
    opacity: 0.7;
    transform: translateY(-10px);
}
```

## Animações

```css
/* Definição da animação usando @keyframes */
@keyframes deslizar {
    /* Estado inicial (0%) */
    0% {
        opacity: 0;
        transform: translateX(-100px);
    }
    
    /* Estado intermediário */
    50% {
        opacity: 0.5;
        transform: translateX(10px);
    }
    
    /* Estado final (100%) */
    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

/* Forma simplificada para animações com apenas estados inicial e final */
@keyframes piscar {
    from {
        opacity: 1;
    }
    to {
        opacity: 0;
    }
}

.animacao {
    /* Propriedades da animação */
    animation-name: deslizar;          /* Nome da animação definida em @keyframes */
    animation-duration: 1s;            /* Duração da animação */
    animation-timing-function: ease;   /* Função de temporização */
    animation-delay: 0.5s;             /* Atraso antes de iniciar */
    animation-iteration-count: 3;      /* Número de repetições (3, infinite) */
    animation-direction: alternate;    /* Direção (normal, reverse, alternate, alternate-reverse) */
    animation-fill-mode: forwards;     /* Estilo após a animação (none, forwards, backwards, both) */
    animation-play-state: running;     /* Estado de reprodução (running, paused) */
    
    /* Forma abreviada */
    animation: deslizar 1s ease 0.5s 3 alternate forwards;
    
    /* Múltiplas animações */
    animation: 
        deslizar 1s ease 0.5s 3 alternate forwards,
        piscar 0.5s ease 0s infinite;
}

/* Controlando a animação com interação */
.animacao:hover {
    animation-play-state: paused;      /* Pausa a animação quando hover */
}
```

## Responsividade e Media Queries

A responsividade é a capacidade de um site se adaptar a diferentes tamanhos de tela e dispositivos. As media queries são uma ferramenta essencial para criar layouts responsivos, permitindo aplicar estilos diferentes com base em características do dispositivo.

```css
/* Estilos base para todos os dispositivos */
body {
    font-size: 16px;
    line-height: 1.5;
}

/* Media query para telas pequenas (smartphones) */
@media screen and (max-width: 576px) {
    body {
        font-size: 14px;
    }
    
    .container {
        padding: 10px;
    }
    
    .navegacao {
        display: none; /* Esconde a navegação em telas pequenas */
    }
}

/* Media query para tablets */
@media screen and (min-width: 577px) and (max-width: 992px) {
    .container {
        padding: 20px;
    }
    
    .coluna {
        width: 50%;
    }
}

/* Media query para desktops */
@media screen and (min-width: 993px) {
    .container {
        max-width: 1200px;
        margin: 0 auto;
    }
    
    .coluna {
        width: 33.33%;
    }
}

/* Media query baseada na orientação */
@media (orientation: landscape) {
    .banner {
        height: 200px;
    }
}

@media (orientation: portrait) {
    .banner {
        height: 300px;
    }
}

/* Media query para impressão */
@media print {
    body {
        font-size: 12pt;
        line-height: 1.2;
        color: black;
        background: white;
    }
    
    .menu, .footer, .ads {
        display: none; /* Esconde elementos desnecessários na impressão */
    }
    
    a::after {
        content: " (" attr(href) ")"; /* Mostra URLs dos links na impressão */
    }
}
```

## Variáveis CSS (Custom Properties)

```css
/* Definindo variáveis globais no :root */
:root {
    /* Cores principais */
    --cor-primaria: #3498db;
    --cor-secundaria: #2ecc71;
    --cor-destaque: #e74c3c;
    --cor-texto: #333333;
    --cor-fundo: #f5f5f5;
    
    /* Fontes */
    --fonte-principal: 'Roboto', sans-serif;
    --fonte-titulos: 'Montserrat', sans-serif;
    
    /* Espaçamentos */
    --espacamento-pequeno: 8px;
    --espacamento-medio: 16px;
    --espacamento-grande: 32px;
    
    /* Tamanhos de texto */
    --texto-pequeno: 14px;
    --texto-medio: 16px;
    --texto-grande: 20px;
    --texto-titulo: 28px;
    
    /* Bordas */
    --borda-padrao: 1px solid #ddd;
    --borda-raio: 4px;
    
    /* Sombras */
    --sombra-suave: 0 2px 4px rgba(0, 0, 0, 0.1);
    --sombra-media: 0 4px 8px rgba(0, 0, 0, 0.2);
}

/* Usando variáveis */
body {
    font-family: var(--fonte-principal);
    color: var(--cor-texto);
    background-color: var(--cor-fundo);
    margin: 0;
    padding: var(--espacamento-medio);
}

h1, h2, h3, h4, h5, h6 {
    font-family: var(--fonte-titulos);
    color: var(--cor-primaria);
}

.botao {
    background-color: var(--cor-primaria);
    color: white;
    padding: var(--espacamento-pequeno) var(--espacamento-medio);
    border-radius: var(--borda-raio);
    border: none;
    box-shadow: var(--sombra-suave);
}

.botao:hover {
    background-color: var(--cor-secundaria);
    box-shadow: var(--sombra-media);
}

/* Alterando variáveis em um escopo específico */
.tema-escuro {
    --cor-texto: #f5f5f5;
    --cor-fundo: #222222;
    --sombra-suave: 0 2px 4px rgba(255, 255, 255, 0.1);
}

/* Variáveis em media queries */
@media (max-width: 768px) {
    :root {
        --espacamento-medio: 12px;
        --espacamento-grande: 24px;
        --texto-grande: 18px;
        --texto-titulo: 24px;
    }
}