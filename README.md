# 👟 SyntaxWear - Tênis & Sneakers Online

Seja muito bem-vindo(a) ao repositório do **SyntaxWear**! Este é um projeto moderno de e-commerce focado na venda de calçados (tênis e sneakers) com um design limpo, minimalista e totalmente responsivo.

Este projeto foi construído utilizando apenas **HTML5 e CSS3 puros** (sem frameworks ou bibliotecas adicionais), o que o torna um excelente material de estudo para quem está iniciando no mundo do desenvolvimento web front-end!

---

## 🚀 Sobre o Projeto

O **SyntaxWear** é uma interface de e-commerce moderna que simula uma loja de calçados premium. Ele conta com:
- **Cabeçalho Fixo (Header) e Responsivo:** Acompanha a navegação do usuário e se adapta para dispositivos móveis com um menu hamburguer interativo.
- **Seção Hero Impressionante:** Banner de destaque com chamada para ação (Call to Action) e botões estilizados.
- **Cards de Categorias:** Seção com 4 categorias principais (Casual, Esporte, Moderno e Futurista) usando efeitos de overlay e imagens de fundo.
- **Grade de Destaques (Grid Section):** Um layout avançado com CSS Grid estruturado em áreas que destaca o produto principal e os secundários de forma muito elegante.
- **Newsletter e Rodapé (Footer):** Espaço para captura de e-mails, links rápidos de navegação e ícones de redes sociais.

---

## 📁 Estrutura de Pastas e Arquivos

Entender a organização de um projeto é o primeiro passo para dominá-lo. Veja como o SyntaxWear foi estruturado:

```text
ecommerce-syntaxwear/
├── index.html                  # O arquivo HTML principal (a estrutura do site)
├── README.md                   # Este arquivo de documentação que você está lendo
├── css/                        # Pasta que contém todos os estilos do site
│   ├── reset.css               # "Limpa" os estilos padrões que os navegadores aplicam por padrão
│   ├── variables.css           # Onde declaramos as fontes (Google Fonts - Ubuntu)
│   ├── base.css                # Estilos gerais do corpo (body), área principal e botões gerais
│   └── components/             # Estilos de partes específicas (componentes) do site:
│       ├── header.css          # Estilos do cabeçalho e menu de navegação
│       ├── hero.css            # Estilos do banner principal de destaque
│       ├── product-category.css# Estilos dos cards de categorias de calçados
│       ├── product-grid.css    # Estilos do grid mosaico de produtos
│       └── footer.css          # Estilos do rodapé e formulário de e-mail
└── images/                     # Pasta com todas as imagens e ícones do projeto
    ├── banners/                # Imagens grandes usadas como plano de fundo
    ├── icons/                  # Ícones em formato SVG (usuário, carrinho, redes sociais, etc.)
    ├── logo/                   # Logotipo oficial da SyntaxWear
    └── products/               # Imagens de tênis e modelos expostos no site
```

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi desenvolvido com tecnologias nativas da web, perfeitas para quem está aprendendo a base do front-end:

*   **HTML5:** Estrutura semântica (tags corretas como `<header>`, `<nav>`, `<main>`, `<section>` e `<footer>`) que melhoram a acessibilidade e o SEO (mecanismos de busca).
*   **CSS3:**
    *   **CSS Custom Properties (Variáveis CSS):** Facilita a manutenção do projeto (por exemplo, definindo fontes centralizadas no `variables.css`).
    *   **Flexbox:** Utilizado para alinhar itens de forma flexível e unidimensional (como no cabeçalho, no rodapé e na seção de categorias).
    *   **CSS Grid (com `grid-template-areas`):** Usado na seção de produtos para criar um layout em mosaico complexo que se rearranja lindamente dependendo do tamanho da tela.
    *   **Media Queries (Design Responsivo):** Folhas de estilo adaptáveis que fazem o site ficar bonito em celulares, tablets e computadores.
    *   **Google Fonts:** Importação direta da fonte **Ubuntu**, trazendo mais sofisticação para a tipografia do site.

---

## 💎 Conceitos Interessantes Aplicados (Para você estudar!)

Se você está começando a programar, dê uma olhada especial nestes dois pontos no código:

### 1. Menu Hamburguer Sem JavaScript (CSS Checkbox Hack)
No arquivo `index.html` e `css/components/header.css`, você verá que o menu móvel abre e fecha sem precisar de uma única linha de JavaScript! Como isso foi feito?
*   Um elemento `<input type="checkbox" class="menu-toggle">` oculto é associado a uma etiqueta `<label for="menu-toggle" class="menu-icon">` que exibe o ícone de hamburguer.
*   No CSS, usamos o seletor irmão `~` combinado com a pseudoclasse `:checked`:
    ```css
    .menu-toggle:checked ~ .nav-container {
        right: 0; /* Traz o menu para a tela quando a caixinha é marcada! */
    }
    ```
    Isso mostra o poder dos seletores avançados e de estados do CSS!

### 2. Layout Mosaico com `grid-template-areas`
Na seção de produtos (`css/components/product-grid.css`), em vez de calcular tamanhos manuais complexos para cada caixa, usamos áreas nomeadas. É como desenhar um mapa ou planta de um local:
```css
.grid-section {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 300px);
    grid-template-areas:
        "top1 top1 top2 top2"
        "top1 top1 midL midR"
        "bottomL bottomL midL bottomR";
    gap: 30px;
}
```
E quando a tela diminui para celulares (menos de 768px), nós simplesmente mudamos o desenho desse mapa de forma mágica através de Media Queries:
```css
@media (max-width: 768px) {
    .grid-section {
        grid-template-columns: 1fr 1fr;
        grid-template-rows: repeat(5, auto);
        grid-template-areas:
            "top1 top1"
            "bottomL bottomL"
            "midL midR"
            "midL bottomR"
            "top2 top2";
    }
}
```

---

## 💻 Como Executar o Projeto Localmente

Como este é um projeto estático (HTML e CSS puros), executá-lo é super simples:

### Método 1: Direto no navegador
1. Baixe os arquivos do projeto para o seu computador.
2. Navegue até a pasta do projeto.
3. Dê um duplo clique no arquivo `index.html`.
4. Pronto! O site será aberto no seu navegador padrão.

### Método 2: Usando o VS Code e Live Server (Recomendado)
Se você usa o **VS Code**, esta é a melhor forma para ver alterações em tempo real enquanto estuda o código:
1. Abra o VS Code e vá em **File > Open Folder...** (Arquivo > Abrir Pasta) e escolha a pasta do projeto.
2. Instale a extensão **Live Server** (ela tem o ícone de uma antena de transmissão de rádio).
3. Abra o arquivo `index.html`.
4. Clique no botão **"Go Live"** localizado na barra inferior direita do seu VS Code.
5. O navegador abrirá automaticamente e se atualizará sempre que você salvar um arquivo!

---

## 💡 Ideias de Próximos Passos (Para você evoluir seu aprendizado)

Quer colocar a mão na massa e praticar ainda mais? Aqui estão algumas sugestões do que você pode tentar adicionar a este projeto:

1.  **Adicionar Interatividade com JavaScript:**
    *   Fazer um botão que "adiciona" o tênis ao carrinho e mostra uma notificação ou popup na tela.
    *   Criar um contador numérico em cima do ícone da bolsa/sacola no cabeçalho para exibir a quantidade de itens.
2.  **Formulário de Newsletter Real:**
    *   Adicionar uma validação no campo de e-mail do rodapé usando HTML5 ou JS, impedindo o envio caso o e-mail esteja vazio ou incompleto.
3.  **Criar Páginas Secundárias:**
    *   Copiar a estrutura do cabeçalho e rodapé e criar uma página `sobre.html` ou `contato.html` para simular a navegação completa pelas opções do menu.
4.  **Efeitos de Transição (Hover):**
    *   Personalizar ainda mais os efeitos de hover (quando o mouse passa por cima) dos cards de categoria e imagens do grid de produtos, como dar um leve zoom (`transform: scale(1.05)`) na imagem.

---

## 📝 Licença

Este projeto é de uso livre para fins de estudo e aprendizado. Sinta-se à vontade para clonar, modificar, experimentar e criar sua própria versão do SyntaxWear!

Feito com 💜 para te ajudar na sua jornada como desenvolvedor(a) web!
