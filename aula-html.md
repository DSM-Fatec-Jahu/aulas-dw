# Aula Completa de HTML

## Introdução ao HTML

HTML (HyperText Markup Language) é a linguagem padrão para criar páginas da web. Ela descreve a estrutura de uma página web através de elementos que são representados por tags. Estes elementos informam ao navegador como exibir o conteúdo.

## Estrutura Básica de um Documento HTML

Todo documento HTML começa com uma estrutura básica:

```html
<!DOCTYPE html>
<!-- Declaração do tipo de documento -->

<html lang="pt-br">
<!-- Tag de abertura do elemento HTML com atributo de idioma -->

<head>
    <!-- Cabeçalho do documento - contém metadados -->
    <meta charset="UTF-8">
    <!-- Define o conjunto de caracteres como UTF-8 -->
    
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Configuração para responsividade -->
    
    <title>Minha Primeira Página</title>
    <!-- Título da página que aparece na aba do navegador -->
</head>

<body>
    <!-- Corpo do documento - contém todo conteúdo visível -->
    <h1>Olá, Mundo!</h1>
    <!-- Título de nível 1 -->
    
    <p>Este é meu primeiro documento HTML.</p>
    <!-- Parágrafo -->
</body>

</html>
<!-- Tag de fechamento do elemento HTML -->
```

## Elementos de Texto

### Títulos

HTML oferece seis níveis de títulos, de `<h1>` (mais importante) até `<h6>` (menos importante):

```html
<h1>Título de Nível 1</h1>
<!-- Usado geralmente como título principal da página -->

<h2>Título de Nível 2</h2>
<!-- Subtítulo ou título de seção -->

<h3>Título de Nível 3</h3>
<!-- Título de subseção -->

<h4>Título de Nível 4</h4>
<!-- Raramente usado em páginas comuns -->

<h5>Título de Nível 5</h5>
<!-- Raramente usado em páginas comuns -->

<h6>Título de Nível 6</h6>
<!-- Raramente usado em páginas comuns -->
```

### Parágrafos e Formatação de Texto

```html
<p>Este é um parágrafo simples.</p>
<!-- Elemento de parágrafo -->

<p>Este é outro parágrafo com <strong>texto em negrito</strong> e <em>texto em itálico</em>.</p>
<!-- strong: texto importante (negrito) -->
<!-- em: texto enfatizado (itálico) -->

<p>Também podemos usar <b>negrito</b> e <i>itálico</i> com as tags b e i.</p>
<!-- b: texto em negrito sem ênfase semântica -->
<!-- i: texto em itálico sem ênfase semântica -->

<p>Para mostrar código, usamos <code>elementos code</code>.</p>
<!-- code: para exibir código -->

<p>Texto <mark>destacado</mark> com marca.</p>
<!-- mark: texto destacado/marcado -->

<p>Texto <del>riscado</del> para indicar remoção.</p>
<!-- del: texto deletado -->

<p>Texto <ins>sublinhado</ins> para indicar inserção.</p>
<!-- ins: texto inserido -->

<p>Fórmulas como H<sub>2</sub>O usam subscrito.</p>
<!-- sub: texto subscrito (abaixo da linha) -->

<p>Expressões como 10<sup>2</sup> usam sobrescrito.</p>
<!-- sup: texto sobrescrito (acima da linha) -->
```

### Quebras de linha e Separadores

```html
<p>Este texto terá<br>uma quebra de linha aqui.</p>
<!-- br: quebra de linha -->

<hr>
<!-- hr: linha horizontal para separar conteúdos -->

<p>Este texto vem após uma linha separadora.</p>
```

## Listas

### Lista Não Ordenada

```html
<ul>
    <!-- Lista não ordenada (com marcadores) -->
    <li>Item 1</li>
    <!-- Elemento de lista -->
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
</ul>
```

### Lista Ordenada

```html
<ol>
    <!-- Lista ordenada (numerada) -->
    <li>Primeiro passo</li>
    <li>Segundo passo</li>
    <li>Terceiro passo</li>
    <li>Quarto passo</li>
</ol>

<ol type="A">
    <!-- Lista ordenada com letras maiúsculas -->
    <li>Item A</li>
    <li>Item B</li>
    <li>Item C</li>
</ol>

<ol type="a">
    <!-- Lista ordenada com letras minúsculas -->
    <li>Item a</li>
    <li>Item b</li>
    <li>Item c</li>
</ol>

<ol type="I">
    <!-- Lista ordenada com algarismos romanos maiúsculos -->
    <li>Item I</li>
    <li>Item II</li>
    <li>Item III</li>
</ol>

<ol type="i">
    <!-- Lista ordenada com algarismos romanos minúsculos -->
    <li>Item i</li>
    <li>Item ii</li>
    <li>Item iii</li>
</ol>
```

### Lista de Definição

```html
<dl>
    <!-- Lista de definição -->
    <dt>HTML</dt>
    <!-- Termo a ser definido -->
    <dd>Linguagem de marcação para páginas web</dd>
    <!-- Definição do termo -->
    
    <dt>CSS</dt>
    <dd>Linguagem para estilizar páginas HTML</dd>
    
    <dt>JavaScript</dt>
    <dd>Linguagem de programação para web</dd>
</dl>
```

## Links

```html
<a href="https://www.exemplo.com">Visite nosso site</a>
<!-- Link para um URL externo -->

<a href="pagina2.html">Ir para a Página 2</a>
<!-- Link para um arquivo na mesma pasta -->

<a href="pasta/pagina.html">Link para arquivo em subpasta</a>
<!-- Link para arquivo em uma subpasta -->

<a href="../index.html">Voltar para início</a>
<!-- Link para arquivo em pasta anterior -->

<a href="#secao1">Ir para Seção 1</a>
<!-- Link para âncora na mesma página -->

<h2 id="secao1">Seção 1</h2>
<!-- Elemento com ID para servir como âncora -->

<a href="mailto:contato@exemplo.com">Enviar e-mail</a>
<!-- Link para abrir cliente de e-mail -->

<a href="tel:+5511987654321">Ligar: (11) 98765-4321</a>
<!-- Link para fazer ligação (útil em dispositivos móveis) -->

<a href="documento.pdf" download>Baixar PDF</a>
<!-- Link para download de arquivo -->

<a href="https://www.exemplo.com" target="_blank">Abrir em nova aba</a>
<!-- Link que abre em nova aba ou janela -->
```

## Imagens

```html
<img src="imagem.jpg" alt="Descrição da imagem">
<!-- Imagem básica com texto alternativo -->

<img src="imagem.jpg" alt="Descrição da imagem" width="300" height="200">
<!-- Imagem com dimensões especificadas -->

<figure>
    <!-- Elemento para agrupar uma imagem com sua legenda -->
    <img src="grafico.jpg" alt="Gráfico de vendas 2023">
    <figcaption>Gráfico de vendas do ano de 2023</figcaption>
    <!-- Legenda da imagem -->
</figure>

<a href="pagina.html">
    <!-- Link com imagem -->
    <img src="botao.jpg" alt="Clique para continuar">
</a>
```

## Tabelas

```html
<table border="1">
    <!-- Tabela com borda (atributo obsoleto, usado apenas para exemplo) -->
    
    <caption>Produtos em Estoque</caption>
    <!-- Título da tabela -->
    
    <thead>
        <!-- Cabeçalho da tabela -->
        <tr>
            <!-- Linha da tabela -->
            <th>Produto</th>
            <!-- Célula de cabeçalho -->
            <th>Quantidade</th>
            <th>Preço</th>
        </tr>
    </thead>
    
    <tbody>
        <!-- Corpo da tabela -->
        <tr>
            <td>Notebook</td>
            <!-- Célula de dados -->
            <td>5</td>
            <td>R$ 3.500,00</td>
        </tr>
        <tr>
            <td>Smartphone</td>
            <td>15</td>
            <td>R$ 1.800,00</td>
        </tr>
        <tr>
            <td>Monitor</td>
            <td>8</td>
            <td>R$ 950,00</td>
        </tr>
    </tbody>
    
    <tfoot>
        <!-- Rodapé da tabela -->
        <tr>
            <td>Total</td>
            <td>28</td>
            <td>R$ 6.250,00</td>
        </tr>
    </tfoot>
</table>
```

### Mesclando células

```html
<table border="1">
    <tr>
        <td>A1</td>
        <td>B1</td>
        <td>C1</td>
    </tr>
    <tr>
        <td colspan="2">A2 e B2 mesclados</td>
        <!-- Mescla duas colunas -->
        <td>C2</td>
    </tr>
    <tr>
        <td>A3</td>
        <td rowspan="2">B3 e B4 mesclados</td>
        <!-- Mescla duas linhas -->
        <td>C3</td>
    </tr>
    <tr>
        <td>A4</td>
        <td>C4</td>
    </tr>
</table>
```

## Formulários

```html
<form action="/processar.php" method="post">
    <!-- Formulário com URL de processamento e método de envio -->
    
    <fieldset>
        <!-- Agrupa elementos relacionados do formulário -->
        <legend>Dados Pessoais</legend>
        <!-- Título do grupo de campos -->
        
        <label for="nome">Nome:</label>
        <!-- Rótulo para o campo -->
        <input type="text" id="nome" name="nome" placeholder="Digite seu nome" required>
        <!-- Campo de texto com placeholder e validação -->
        <br><br>
        
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" placeholder="seu@email.com" required>
        <!-- Campo específico para e-mail com validação -->
        <br><br>
        
        <label for="senha">Senha:</label>
        <input type="password" id="senha" name="senha" minlength="6" required>
        <!-- Campo de senha com comprimento mínimo -->
        <br><br>
        
        <label for="nascimento">Data de Nascimento:</label>
        <input type="date" id="nascimento" name="nascimento">
        <!-- Campo de data -->
        <br><br>
        
        <label for="telefone">Telefone:</label>
        <input type="tel" id="telefone" name="telefone" pattern="[0-9]{10,11}">
        <!-- Campo de telefone com padrão -->
        <br><br>
    </fieldset>
    
    <fieldset>
        <legend>Preferências</legend>
        
        <p>Gênero:</p>
        <input type="radio" id="masculino" name="genero" value="masculino">
        <!-- Botão de opção (apenas uma escolha possível) -->
        <label for="masculino">Masculino</label>
        <br>
        
        <input type="radio" id="feminino" name="genero" value="feminino">
        <label for="feminino">Feminino</label>
        <br>
        
        <input type="radio" id="outro" name="genero" value="outro">
        <label for="outro">Outro</label>
        <br><br>
        
        <p>Interesses:</p>
        <input type="checkbox" id="tecnologia" name="interesses" value="tecnologia">
        <!-- Caixa de seleção (múltiplas escolhas possíveis) -->
        <label for="tecnologia">Tecnologia</label>
        <br>
        
        <input type="checkbox" id="esportes" name="interesses" value="esportes">
        <label for="esportes">Esportes</label>
        <br>
        
        <input type="checkbox" id="musica" name="interesses" value="musica">
        <label for="musica">Música</label>
        <br><br>
        
        <label for="pais">País:</label>
        <select id="pais" name="pais">
            <!-- Lista suspensa de seleção -->
            <option value="">Selecione um país</option>
            <option value="br">Brasil</option>
            <option value="pt">Portugal</option>
            <option value="us">Estados Unidos</option>
            <option value="es">Espanha</option>
        </select>
        <br><br>
        
        <label for="comentario">Comentários:</label><br>
        <textarea id="comentario" name="comentario" rows="4" cols="50" placeholder="Deixe seu comentário"></textarea>
        <!-- Área de texto para comentários longos -->
        <br><br>
        
        <label for="arquivo">Enviar arquivo:</label>
        <input type="file" id="arquivo" name="arquivo">
        <!-- Campo para upload de arquivo -->
        <br><br>
        
        <label for="cor">Cor favorita:</label>
        <input type="color" id="cor" name="cor">
        <!-- Seletor de cor -->
        <br><br>
        
        <label for="satisfacao">Nível de satisfação:</label>
        <input type="range" id="satisfacao" name="satisfacao" min="0" max="10" step="1">
        <!-- Controle deslizante (range) -->
        <br><br>
    </fieldset>
    
    <br>
    <input type="submit" value="Enviar">
    <!-- Botão para enviar o formulário -->
    
    <input type="reset" value="Limpar">
    <!-- Botão para limpar o formulário -->
</form>
```

## Elementos Semânticos do HTML5

```html
<header>
    <!-- Cabeçalho da página ou seção -->
    <h1>Meu Site</h1>
    <p>Bem-vindo ao meu site sobre HTML</p>
</header>

<nav>
    <!-- Navegação principal -->
    <ul>
        <li><a href="#inicio">Início</a></li>
        <li><a href="#sobre">Sobre</a></li>
        <li><a href="#servicos">Serviços</a></li>
        <li><a href="#contato">Contato</a></li>
    </ul>
</nav>

<main>
    <!-- Conteúdo principal da página -->
    <section id="inicio">
        <!-- Seção da página -->
        <h2>Página Inicial</h2>
        <p>Bem-vindo ao nosso site!</p>
    </section>
    
    <section id="sobre">
        <h2>Sobre Nós</h2>
        <p>Somos uma empresa especializada em desenvolvimento web.</p>
    </section>
    
    <article>
        <!-- Conteúdo autônomo, que faz sentido por si só -->
        <h2>O que é HTML?</h2>
        <p>HTML é uma linguagem de marcação utilizada para criar páginas web.</p>
        
        <aside>
            <!-- Conteúdo relacionado indiretamente com o conteúdo principal -->
            <h3>Curiosidade</h3>
            <p>HTML foi criado em 1991 por Tim Berners-Lee.</p>
        </aside>
    </article>
    
    <section id="servicos">
        <h2>Nossos Serviços</h2>
        <div>
            <!-- Contêiner genérico sem valor semântico -->
            <h3>Desenvolvimento Web</h3>
            <p>Criamos sites modernos e responsivos.</p>
        </div>
        
        <div>
            <h3>Design Gráfico</h3>
            <p>Elaboramos identidade visual para sua marca.</p>
        </div>
    </section>
</main>

<footer>
    <!-- Rodapé da página -->
    <p>&copy; 2025 Meu Site - Todos os direitos reservados</p>
    <address>
        <!-- Informações de contato -->
        Contato: <a href="mailto:info@meusite.com">info@meusite.com</a><br>
        Rua Exemplo, 123 - Cidade - Estado
    </address>
</footer>
```

## Incorporando Áudio e Vídeo

```html
<!-- Áudio -->
<audio controls>
    <!-- Elemento de áudio com controles de reprodução -->
    <source src="musica.mp3" type="audio/mpeg">
    <!-- Fonte do áudio com tipo especificado -->
    <source src="musica.ogg" type="audio/ogg">
    <!-- Fonte alternativa para compatibilidade -->
    Seu navegador não suporta o elemento de áudio.
    <!-- Mensagem para navegadores que não suportam -->
</audio>

<!-- Vídeo -->
<video width="320" height="240" controls>
    <!-- Elemento de vídeo com dimensões e controles -->
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    Seu navegador não suporta o elemento de vídeo.
</video>

<!-- Incorporando vídeo do YouTube -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" frameborder="0" allowfullscreen></iframe>
<!-- iframe: incorpora conteúdo de outra página -->
```

## Caracteres Especiais e Entidades HTML

```html
<p>O símbolo de copyright é &copy;</p>
<!-- &copy; exibe © -->

<p>O símbolo de marca registrada é &reg;</p>
<!-- &reg; exibe ® -->

<p>O símbolo de marca comercial é &trade;</p>
<!-- &trade; exibe ™ -->

<p>Símbolos matemáticos: &lt; &gt; &le; &ge; &ne;</p>
<!-- &lt; exibe < -->
<!-- &gt; exibe > -->
<!-- &le; exibe ≤ -->
<!-- &ge; exibe ≥ -->
<!-- &ne; exibe ≠ -->

<p>Para mostrar tags HTML como texto: &lt;p&gt;Texto&lt;/p&gt;</p>
<!-- Exibe <p>Texto</p> como texto, não como elemento -->

<p>O caractere e comercial é &amp;</p>
<!-- &amp; exibe & -->

<p>Aspas: &quot;citação&quot;</p>
<!-- &quot; exibe " -->

<p>Espaço não quebrável: texto&nbsp;conectado</p>
<!-- &nbsp; insere um espaço que não quebra linha -->
```

## Projeto Prático: Página Web Completa

Agora, vamos juntar tudo o que aprendemos em uma página web completa:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Site HTML</title>
</head>
<body>
    <!-- Cabeçalho da página -->
    <header>
        <h1>Aprenda HTML</h1>
        <p>Um guia completo para iniciantes</p>
    </header>
    
    <!-- Navegação principal -->
    <nav>
        <ul>
            <li><a href="#introducao">Introdução</a></li>
            <li><a href="#elementos">Elementos Básicos</a></li>
            <li><a href="#formulario">Formulário</a></li>
            <li><a href="#contato">Contato</a></li>
        </ul>
    </nav>
    
    <!-- Conteúdo principal -->
    <main>
        <!-- Seção de introdução -->
        <section id="introducao">
            <h2>Introdução ao HTML</h2>
            <p>HTML (HyperText Markup Language) é a linguagem padrão para criar páginas da web. Ela utiliza tags para definir a estrutura e o conteúdo de uma página.</p>
            
            <figure>
                <img src="html-logo.png" alt="Logo do HTML5" width="200">
                <figcaption>Logo oficial do HTML5</figcaption>
            </figure>
        </section>
        
        <!-- Seção de elementos básicos -->
        <section id="elementos">
            <h2>Elementos Básicos</h2>
            
            <article>
                <h3>Títulos e Parágrafos</h3>
                <p>HTML oferece seis níveis de títulos (h1-h6) e parágrafos para organizar o conteúdo.</p>
                <p>Exemplo: <code>&lt;h1&gt;Título Principal&lt;/h1&gt;</code></p>
            </article>
            
            <article>
                <h3>Listas</h3>
                <p>Existem três tipos principais de listas em HTML:</p>
                
                <h4>Lista Não Ordenada</h4>
                <ul>
                    <li>Item 1</li>
                    <li>Item 2</li>
                    <li>Item 3</li>
                </ul>
                
                <h4>Lista Ordenada</h4>
                <ol>
                    <li>Primeiro passo</li>
                    <li>Segundo passo</li>
                    <li>Terceiro passo</li>
                </ol>
                
                <h4>Lista de Definição</h4>
                <dl>
                    <dt>HTML</dt>
                    <dd>Linguagem de marcação para páginas web</dd>
                    <dt>CSS</dt>
                    <dd>Linguagem para estilizar páginas HTML</dd>
                </dl>
            </article>
            
            <article>
                <h3>Links e Imagens</h3>
                <p>Links são criados com a tag <code>&lt;a&gt;</code> e imagens com a tag <code>&lt;img&gt;</code>.</p>
                <p><a href="https://www.w3.org/html/" target="_blank">Visite o site oficial do HTML</a></p>
            </article>
            
            <article>
                <h3>Tabelas</h3>
                <p>Tabelas são usadas para apresentar dados em formato de grade.</p>
                
                <table border="1">
                    <caption>Tecnologias Web</caption>
                    <thead>
                        <tr>
                            <th>Tecnologia</th>
                            <th>Função</th>
                            <th>Versão Atual</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>HTML</td>
                            <td>Estrutura</td>
                            <td>HTML5</td>
                        </tr>
                        <tr>
                            <td>CSS</td>
                            <td>Estilo</td>
                            <td>CSS3</td>
                        </tr>
                        <tr>
                            <td>JavaScript</td>
                            <td>Comportamento</td>
                            <td>ECMAScript 2023</td>
                        </tr>
                    </tbody>
                </table>
            </article>
        </section>
        
        <!-- Seção de formulário -->
        <section id="formulario">
            <h2>Formulário de Inscrição</h2>
            
            <form action="/processar.php" method="post">
                <fieldset>
                    <legend>Dados Pessoais</legend>
                    
                    <label for="nome">Nome Completo:</label>
                    <input type="text" id="nome" name="nome" required><br><br>
                    
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" required><br><br>
                    
                    <label for="nascimento">Data de Nascimento:</label>
                    <input type="date" id="nascimento" name="nascimento"><br><br>
                </fieldset>
                
                <fieldset>
                    <legend>Preferências</legend>
                    
                    <p>Nível de conhecimento em HTML:</p>
                    <input type="radio" id="iniciante" name="nivel" value="iniciante">
                    <label for="iniciante">Iniciante</label><br>
                    
                    <input type="radio" id="intermediario" name="nivel" value="intermediario">
                    <label for="intermediario">Intermediário</label><br>
                    
                    <input type="radio" id="avancado" name="nivel" value="avancado">
                    <label for="avancado">Avançado</label><br><br>
                    
                    <p>Tecnologias que conhece:</p>
                    <input type="checkbox" id="html" name="tech" value="html">
                    <label for="html">HTML</label><br>
                    
                    <input type="checkbox" id="css" name="tech" value="css">
                    <label for="css">CSS</label><br>
                    
                    <input type="checkbox" id="js" name="tech" value="js">
                    <label for="js">JavaScript</label><br><br>
                    
                    <label for="interesses">Área de interesse:</label>
                    <select id="interesses" name="interesses">
                        <option value="">Selecione</option>
                        <option value="frontend">Desenvolvimento Front-end</option>
                        <option value="backend">Desenvolvimento Back-end</option>
                        <option value="fullstack">Desenvolvimento Full-stack</option>
                        <option value="design">Web Design</option>
                    </select><br><br>
                    
                    <label for="mensagem">Mensagem:</label><br>
                    <textarea id="mensagem" name="mensagem" rows="5" cols="40" placeholder="Por que você deseja aprender HTML?"></textarea>
                </fieldset>
                
                <br>
                <input type="submit" value="Enviar Inscrição">
                <input type="reset" value="Limpar Campos">
            </form>
        </section>
    </main>
    
    <!-- Barra lateral com informações adicionais -->
    <aside>
        <h2>Recursos Úteis</h2>
        <ul>
            <li><a href="#">Documentação HTML</a></li>
            <li><a href="#">Tutoriais em Vídeo</a></li>
            <li><a href="#">Livros Recomendados</a></li>
            <li><a href="#">Comunidade de Desenvolvedores</a></li>
        </ul>
        
        <h3>Você sabia?</h3>
        <p>O HTML5 foi finalizado e publicado em 28 de outubro de 2014 pelo W3C.</p>
    </aside>
    
    <!-- Seção de contato -->
    <section id="contato">
        <h2>Entre em Contato</h2>
        <address>
            Email: <a href="mailto:contato@exemplo.com">contato@exemplo.com</a><br>
            Telefone: <a href="tel:+5511987654321">(11) 98765-4321</a><br>
            Endereço: Av. da Web, 123 - São Paulo/SP
        </address>
    </section>
    
    <!-- Rodapé da página -->
    <footer>
        <p>&copy; 2025 Aprenda HTML - Todos os direitos reservados</p>
        <p>Última atualização: <time datetime="2025-03-12">12 de março de 2025</time></p>
    </footer>
</body>
</html>
```

## Conclusão

HTML é a base fundamental para o desenvolvimento web. Nesta aula, vimos os principais elementos que compõem um documento HTML, desde sua estrutura básica até elementos mais específicos como tabelas, formulários e recursos multimídia.

Para avançar em seus estudos, explore:
1. CSS para estilizar suas páginas HTML
2. JavaScript para adicionar interatividade
3. Frameworks e bibliotecas que facilitam o desenvolvimento web

Lembre-se de que a prática é essencial para o aprendizado. Experimente criar suas próprias páginas web e consulte a documentação oficial quando necessário.

## Recursos Adicionais

- [MDN Web Docs](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [W3Schools](https://www.w3schools.com/html/)
- [HTML5 Doctor](http://html5doctor.com/)
- [HTML Standard](https://html.spec.whatwg.org/)
