# Aula: Criando uma Página de Filmes com Dark Mode

Nesta aula, vamos criar uma página simples que exibe 3 filmes atuais e implementa um modo escuro (dark mode) da forma mais simples possível usando HTML5 e CSS3.

## Objetivos

1. Criar uma estrutura HTML5 semântica
2. Estilizar a página com CSS3
3. Implementar um botão de alternância para dark mode
4. Aplicar conceitos de design responsivo

## Estrutura HTML

Vamos começar criando o arquivo HTML com uma estrutura semântica:

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Filmes Atuais</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Cabeçalho da página -->
    <header>
        <h1>Filmes em Destaque</h1>
        <!-- Botão para alternar entre modo claro e escuro -->
        <button id="toggle-mode">Modo Escuro</button>
    </header>
    
    <!-- Conteúdo principal -->
    <main>
        <section class="filmes-container">
            <!-- Filme 1 -->
            <article class="card-filme">
                <img src="https://via.placeholder.com/300x450" alt="Duna: Parte 2">
                <div class="info-filme">
                    <h2>Duna: Parte 2</h2>
                    <p class="diretor">Diretor: Denis Villeneuve</p>
                    <p class="sinopse">Paul Atreides se une a Chani e aos Fremen enquanto busca vingança contra os conspiradores que destruíram sua família.</p>
                    <div class="avaliacao">⭐⭐⭐⭐☆</div>
                </div>
            </article>
            
            <!-- Filme 2 -->
            <article class="card-filme">
                <img src="https://via.placeholder.com/300x450" alt="Deadpool & Wolverine">
                <div class="info-filme">
                    <h2>Deadpool & Wolverine</h2>
                    <p class="diretor">Diretor: Shawn Levy</p>
                    <p class="sinopse">Wade Wilson precisa convencer um Logan relutante a ajudá-lo a salvar o multiverso.</p>
                    <div class="avaliacao">⭐⭐⭐⭐⭐</div>
                </div>
            </article>
            
            <!-- Filme 3 -->
            <article class="card-filme">
                <img src="https://via.placeholder.com/300x450" alt="Furiosa: Uma Saga Mad Max">
                <div class="info-filme">
                    <h2>Furiosa: Uma Saga Mad Max</h2>
                    <p class="diretor">Diretor: George Miller</p>
                    <p class="sinopse">A história de origem da guerreira Furiosa antes de seu encontro com Max Rockatansky no deserto pós-apocalíptico.</p>
                    <div class="avaliacao">⭐⭐⭐⭐☆</div>
                </div>
            </article>
        </section>
    </main>
    
    <!-- Rodapé da página -->
    <footer>
        <p>&copy; 2025 - Página de Filmes</p>
    </footer>
    
    <script src="script.js"></script>
</body>
</html>
```

## Estilos CSS

Agora vamos criar o arquivo `style.css` com os estilos básicos e a implementação do dark mode:

```css
/* Variáveis para as cores (para facilitar a implementação do dark mode) */
:root {
    /* Cores para o modo claro (padrão) */
    --cor-fundo: #f5f5f5;
    --cor-texto: #333;
    --cor-cartao: #fff;
    --cor-cabecalho: #1a1a2e;
    --cor-cabecalho-texto: #fff;
    --cor-borda: #ddd;
    --cor-sombra: rgba(0, 0, 0, 0.1);
}

/* Classe para o modo escuro */
.dark-mode {
    --cor-fundo: #121212;
    --cor-texto: #f5f5f5;
    --cor-cartao: #1e1e1e;
    --cor-cabecalho: #000;
    --cor-cabecalho-texto: #f5f5f5;
    --cor-borda: #444;
    --cor-sombra: rgba(255, 255, 255, 0.05);
}

/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Estilos gerais */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--cor-fundo);
    color: var(--cor-texto);
    line-height: 1.6;
    transition: background-color 0.3s, color 0.3s;
}

/* Cabeçalho */
header {
    background-color: var(--cor-cabecalho);
    color: var(--cor-cabecalho-texto);
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

header h1 {
    font-size: 1.8rem;
}

/* Botão de alternar modo */
#toggle-mode {
    padding: 8px 16px;
    background-color: transparent;
    color: var(--cor-cabecalho-texto);
    border: 2px solid var(--cor-cabecalho-texto);
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
    transition: all 0.3s;
}

#toggle-mode:hover {
    background-color: var(--cor-cabecalho-texto);
    color: var(--cor-cabecalho);
}

/* Conteúdo principal */
main {
    max-width: 1200px;
    margin: 20px auto;
    padding: 0 20px;
}

/* Container de filmes */
.filmes-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

/* Cartão de filme */
.card-filme {
    background-color: var(--cor-cartao);
    border-radius: 8px;
    box-shadow: 0 4px 8px var(--cor-sombra);
    overflow: hidden;
    width: 300px;
    transition: transform 0.3s, box-shadow 0.3s, background-color 0.3s;
    border: 1px solid var(--cor-borda);
}

.card-filme:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px var(--cor-sombra);
}

.card-filme img {
    width: 100%;
    height: 450px;
    object-fit: cover;
}

.info-filme {
    padding: 15px;
}

.info-filme h2 {
    font-size: 1.5rem;
    margin-bottom: 10px;
}

.diretor {
    color: #666;
    font-style: italic;
    margin-bottom: 10px;
}

.dark-mode .diretor {
    color: #aaa;
}

.sinopse {
    margin-bottom: 15px;
}

.avaliacao {
    font-size: 1.2rem;
    color: gold;
}

/* Rodapé */
footer {
    text-align: center;
    padding: 20px;
    margin-top: 40px;
    background-color: var(--cor-cabecalho);
    color: var(--cor-cabecalho-texto);
}

/* Media queries para responsividade */
@media (max-width: 768px) {
    header {
        flex-direction: column;
        gap: 10px;
    }
    
    .card-filme {
        width: 100%;
    }
}
```

## JavaScript para o Dark Mode

Por fim, vamos adicionar o JavaScript para implementar a funcionalidade de alternância entre modos claro e escuro:

```javascript
// script.js
document.addEventListener('DOMContentLoaded', function() {
    const toggleButton = document.getElementById('toggle-mode');
    
    // Verifica se há preferência salva no localStorage
    if (localStorage.getItem('darkMode') === 'enabled') {
        document.body.classList.add('dark-mode');
        toggleButton.textContent = 'Modo Claro';
    }
    
    // Função para alternar o modo
    toggleButton.addEventListener('click', function() {
        // Alterna a classe 'dark-mode' no body
        document.body.classList.toggle('dark-mode');
        
        // Verifica se o modo escuro está ativo para atualizar o botão e salvar a preferência
        if (document.body.classList.contains('dark-mode')) {
            toggleButton.textContent = 'Modo Claro';
            localStorage.setItem('darkMode', 'enabled');
        } else {
            toggleButton.textContent = 'Modo Escuro';
            localStorage.setItem('darkMode', 'disabled');
        }
    });
});
```

## Explicação do Código

### HTML

- Utilizamos tags semânticas como `<header>`, `<main>`, `<section>`, `<article>` e `<footer>`.
- Cada filme é representado dentro de um `<article>` com uma imagem, título, diretor, sinopse e avaliação.
- Adicionamos um botão para alternar entre o modo claro e escuro.

### CSS

- Definimos variáveis CSS (Custom Properties) para as cores no `:root`.
- Criamos uma classe `.dark-mode` que redefine essas variáveis com cores escuras.
- Aplicamos `transition` para suavizar a mudança entre os modos.
- Usamos `display: flex` para criar um layout responsivo para os cartões de filme.
- Adicionamos efeitos hover nos cartões para melhorar a interatividade.
- Implementamos media queries para garantir que a página seja responsiva.

### JavaScript

- Adicionamos a funcionalidade para alternar a classe `dark-mode` no `<body>`.
- Salvamos a preferência do usuário no `localStorage` para persistir entre sessões.
- Atualizamos o texto do botão de acordo com o modo atual.

## Implementações Adicionais (Opcionais)

1. **Modo automático baseado na preferência do sistema**:
   ```javascript
   // Verificar preferência do sistema
   const prefersColorScheme = window.matchMedia('(prefers-color-scheme: dark)');
   
   // Aplicar modo escuro se o sistema preferir
   if (prefersColorScheme.matches) {
       document.body.classList.add('dark-mode');
       toggleButton.textContent = 'Modo Claro';
   }
   ```

2. **Adicionar transições mais elaboradas**:
   ```css
   .card-filme {
       transition: transform 0.3s ease-in-out, 
                   box-shadow 0.3s ease-in-out, 
                   background-color 0.3s ease;
   }
   ```

## Conclusão

Este exemplo demonstra uma implementação simples e eficaz de uma página de filmes com dark mode usando HTML5 e CSS3. Utilizamos:

- **Semântica HTML5** para estruturar o conteúdo
- **CSS3 moderno** com variáveis CSS para facilitar a troca de temas
- **JavaScript básico** para adicionar interatividade
- **Design responsivo** para adaptar a página a diferentes dispositivos

A implementação do dark mode é feita de forma eficiente usando variáveis CSS, o que torna o código limpo e fácil de manter. As transições suaves entre os modos melhoram a experiência do usuário.

Para um projeto real, você poderia substituir os placeholders por imagens reais dos filmes e expandir o conteúdo com mais informações como data de lançamento, gênero, elenco, etc.
