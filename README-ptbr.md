<div align="center">

<img src="assets/favicon/favicon.svg" width="130" height="130" alt="AXIS symbol"/>

# AXIS

**A modern Sass architecture and starter foundation for scalable, maintainable web projects**

*Structure your frontend. Focus on building, not configuring*

[![License](https://img.shields.io/badge/license-MIT-e8e4de?style=flat-square&labelColor=ef4444&color=1c1b2e)](https://github.com/lucas16716/axis/blob/main/LICENSE)&nbsp;
[![Version](https://img.shields.io/badge/version-1.0.0-e8e4de?style=flat-square&labelColor=10b981&color=1c1b2e)](https://github.com/lucas16716/axis/releases)&nbsp;
[![Template](https://img.shields.io/badge/template-ready-e8e4de?style=flat-square&labelColor=3437e6&color=1c1b2e)](https://github.com/lucas16716/axis/generate)&nbsp;
![GitHub Repo stars](https://img.shields.io/github/stars/lucas16716/axis?style=social)

🇺🇸 [Read in English](./README.md)

</div>

## O que é o AXIS?

O AXIS é uma arquitetura moderna baseada em Sass, projetada para estruturar projetos frontend de forma clara, escalável, previsível e de fácil manutenção.

É uma fundação de partida que assume um desenvolvimento tradicional — **sem Node, sem bundler, sem dependências** — apenas HTML, Sass e JavaScript puros. Você clona, define seus tokens semânticos e já começa a desenvolver com uma base sólida: reset normalizado, tipografia configurada, sistema de layout funcional e de fácil edição, componentes neutros prontos para receber sua identidade visual e utilitários que agilizam o desenvolvimento, permitindo que você foque no que realmente importa: construir a interface.

## Filosofia

O AXIS foi construído em torno de seis princípios fundamentais:

**Liberdade de desenvolvimento -**
Não impõe frameworks, bibliotecas ou dependências. É uma estrutura opinada com liberdade total ao dev, fornecendo uma base arquitetural sólida e permitindo que cada projeto evolua conforme suas necessidades.

**Simplicidade arquitetural -**
A estrutura de pastas é direta e previsível. Cada camada do projeto possui uma responsabilidade clara, facilitando navegação, manutenção e escalabilidade. Você sempre sabe onde procurar e onde colocar cada coisa.

**Arquitetura Sass modular -**
Cinco camadas bem separadas, cada uma com responsabilidade única, que se comunicam através de `@use` e `@forward`, criando uma hierarquia lógica de estilos: Abstracts → Base → Layout → Components → Sections.

**Token-driven design -**
Todos os valores visuais vêm de tokens. Tokens primitivos ficam centralizados em `abstracts/tokens/` e são acessíveis globalmente via `@use`. Tokens semânticos são definidos localmente na partial onde são consumidos — isso elimina navegação desnecessária entre arquivos, facilitando a manutenção e a leitura do código.

> Ex: tokens semânticos em `base/_typography.scss` para tipografia, em `abstracts/tokens/_spacing.scss` para configuração de layout, e dentro de cada componente para seus próprios valores de padding, transição e tamanho.

**Desktop-first workflow -**
A arquitetura parte do layout maior e adapta para telas menores via `@include respond()`. Possui suporte completo a `respond-up()` para progressive enhancement quando necessário.

**Performance-oriented development -**
O CSS é compilado e minificado automaticamente. O JS é minificado manualmente antes do deploy. Os assets seguem diretrizes de otimização documentadas em cada pasta. O `index.html` já vem com meta tags de SEO e Open Graph pré-configuradas. Cada pasta e arquivo do AXIS possuem documentação, dicas e comentários que guiam para as melhores práticas de desenvolvimento frontend.

## Stack

| Tecnologia | Uso |
|---|---|
| HTML5 | Template base com meta tags de SEO, OG e PWA |
| Sass (SCSS) | Arquitetura modular com design tokens |
| JavaScript | Livre — sem estrutura imposta |

## Estrutura do projeto

```
axis/
├── .gitignore
├── .vscode/
│   └── settings.json        → Configuração do Live Sass Compiler
├── assets/
│   ├── docs/                → Documentos para download
│   ├── favicon/             → Ícones e manifest.json
│   ├── media/
│   │   ├── img/             → Imagens raster (.webp, .jpg, .png)
│   │   └── video/           → Vídeos (.webm, .mp4)
│   └── svg/                 → Vetores, ícones e ilustrações
├── dist/
│   ├── main.min.css         → CSS minificado (gerado automaticamente)
│   └── script.min.js        → JS minificado (gerado manualmente)
├── src/
│   ├── css/
│   │   └── main.css         → CSS compilado para desenvolvimento
│   ├── js/
│   │   └── script.js        → JavaScript do projeto (vazio — pronto para seu projeto)
│   └── sass/
│       ├── abstracts/       → Tokens, funções e mixins
│       ├── base/            → Reset, tipografia, global e utilities
│       ├── layout/          → Container, flex e grid
│       ├── components/      → Button, card e badge
│       ├── sections/        → Header e footer (vazios — prontos para seu projeto)
│       └── main.scss        → Entry point único
├── index.html
├── LICENSE
├── README-ptbr.md
└── README.md
```

## Arquitetura Sass

O AXIS organiza o Sass em **cinco camadas** com responsabilidades claras, seguindo os princípios do ITCSS:

**1. Abstracts -**
Nada aqui gera CSS diretamente. É a base inteira do sistema.

- **`tokens/`** — 9 arquivos de design tokens com valores genéricos, padronizados e escaláveis: colors, spacing, typography, breakpoints, motion, elevation, layers, radius e opacity
- **`functions/`** — acesso tipado a tokens via `bp()` e `z()`, e helpers de cor com `color.scale()`
- **`mixins/`** — container, flex, grid, grid-auto, respond, respond-up, absolute-center, focus-ring, visually-hidden e truncate

**2. Base -**
Normalização e estilos globais sem classes.

- **`_reset.scss`** — box-sizing, reset de margin/padding, focus-ring acessível, text-size-adjust e scroll-behavior
- **`_typography.scss`** — fonte base com tokens semânticos, escala de headings em Major Third (1.25)
- **`_global.scss`** — imagens responsivas, herança de fonte, prefers-reduced-motion
- **`_utilities.scss`** — sr-only, display, visibility responsiva, position, alinhamento de texto, truncate e interação

**3. Layout -**
Sistema de layout estrutural sem opiniões visuais.

- **`_container.scss`** — `.container` e variantes `.container-{sm|md|lg|xl|xxl}`
- **`_flex.scss`** — `.flex` com modificadores de direção, justify e align
- **`_grid.scss`** — `.grid-{1-12}`, `.col-span-{1-12}`, `.grid-auto` e variantes responsivas

**4. Components -**
Componentes neutros e token-driven. Sem cores definidas — usam `currentColor` e herdam do contexto.

- **`_button.scss`** — tamanhos (sm/md/lg/xl), shapes (square/circle), variantes (pill/ghost), estado disabled
- **`_card.scss`** — estático e interativo, com estrutura `card__content` e modificadores de alinhamento de conteúdo
- **`_badge.scss`** — inline, pill, neutro

**5. Sections -**
Partials vazias para **header** e **footer**. Prontas para você estilizar de acordo com o projeto.

## Design Tokens

| Arquivo | O que define |
|---|---|
| `_colors.scss` | Escala de cinzas (white → black) + 4 cores funcionais (green, yellow, red, blue) |
| `_spacing.scss` | Escala macro 8pt (layout) + escala micro (UI controls) + tokens semânticos `$gutter` e `$section-pad` |
| `_typography.scss` | 18 tamanhos (Major Third + UI), pesos, line-heights e letter-spacings |
| `_breakpoints.scss` | 6 breakpoints desktop-first: xxl, xl, lg, md, sm, xs |
| `_motion.scss` | 5 durações + 4 curvas de easing (standard, in, out, back) |
| `_elevation.scss` | 5 níveis de sombra (none → lg) |
| `_layers.scss` | Z-index semântico: back, base, header, dropdown, overlay, modal, tooltip |
| `_radius.scss` | 6 raios: xs, sm, md, lg, xl, full |
| `_opacity.scss` | 6 níveis: 0, 20, 40, 60, 80, 100 |

## Sistema de Layout

### Container

```html
<div class="container">          <!-- max-width: 1200px (padrão via mixin) -->
<div class="container-sm">       <!-- max-width: 640px -->
<div class="container-md">       <!-- max-width: 768px -->
<div class="container-lg">       <!-- max-width: 1024px -->
<div class="container-xl">       <!-- max-width: 1200px -->
<div class="container-xxl">      <!-- max-width: 1280px -->
```

### Flex

```html
<div class="flex items-center justify-between">
<div class="flex flex-col items-start">
<div class="flex flex-wrap justify-center">
```

Modificadores disponíveis: `flex-col`, `flex-wrap`, `justify-start`, `justify-center`, `justify-between`, `justify-end`, `items-stretch`, `items-center`, `items-start`, `items-end`.

### Grid

```html
<div class="grid-3">             <!-- 3 colunas fixas -->
<div class="grid-3 grid-1-md">   <!-- 3 colunas → 1 coluna em md -->
<div class="grid-auto">          <!-- colunas responsivas automáticas -->

<div class="col-span-2">         <!-- item ocupa 2 colunas -->
<div class="col-span-2-md">      <!-- ocupa 2 colunas em md -->
```

> As variantes responsivas `.grid-{n}-{bp}` sobrescrevem apenas `grid-template-columns`. A classe base `.grid-{n}` deve estar sempre presente no elemento.

## Componentes

### Button

```html
<!-- Tamanhos -->
<button class="button size-sm">Small</button>
<button class="button size-md">Medium</button>
<button class="button size-lg">Large</button>
<button class="button size-xl">X-Large</button>

<!-- Variantes -->
<button class="button size-md is-pill">Pill</button>
<button class="button size-md is-ghost">Ghost</button>
<button class="button size-md" disabled>Disabled</button>

<!-- Shapes -->
<button class="button size-md shape-square">⊕</button>
<button class="button size-md shape-circle">→</button>
```

### Card

```html
<div class="card">
  <div class="card__content is-start">
    <h4>Título</h4>
    <p>Conteúdo do card.</p>
  </div>
</div>

<!-- Card interativo -->
<div class="card is-interactive">
  <div class="card__content is-center">
    ...
  </div>
</div>
```

Modificadores de alinhamento: `is-start`, `is-center`, `is-end`.

### Badge

```html
<span class="badge">Default</span>
```

O badge herda cor via `currentColor` — aplique a cor pelo elemento pai ou diretamente via `style` ou classe de cor do seu projeto.

## Mixins

Use os mixins diretamente nas suas partials de seção ou componente:

```scss
@use "../abstracts/mixins" as mix;
@use "../abstracts/tokens" as token;

.meu-componente {
  @include mix.flex($justify: center, $align: center);
}

.meu-overlay {
  @include mix.absolute-center;
}

.meu-input:focus-visible {
  @include mix.focus-ring(token.$blue-500, 3px);
}

@include mix.respond(md) {
  // estilos para md e abaixo
}
```

## Como usar o AXIS?

### 1. Clone o repositório

```bash
git clone https://github.com/lucas16716/axis.git nome-do-seu-projeto
cd nome-do-seu-projeto
```

### 2. Instale o Live Sass Compiler

No VS Code, instale a extensão **Live Sass Compiler** de Glenn Marks.

O arquivo `.vscode/settings.json` já está configurado — ao ativar o Watch Sass, o compilador irá gerar automaticamente:

- `src/css/main.css` → CSS expandido para desenvolvimento
- `dist/main.min.css` → CSS minificado para produção

### 3. Ative o Watch Sass

Clique em **Watch Sass** na barra inferior do VS Code.

A partir daí, qualquer alteração nos arquivos `.scss` compila os dois outputs automaticamente.

### 4. Atualize o index.html

Por padrão o `index.html` aponta para o CSS de desenvolvimento. Para produção, troque os links comentados:

```html
<!-- Desenvolvimento -->
<link rel="stylesheet" href="/src/css/main.css" />

<!-- Produção — descomente e comente o de cima -->
<!-- <link rel="stylesheet" href="/dist/main.min.css" /> -->
```

### 5. Comece a construir

Adicione suas seções em `src/sass/sections/` e registre-as no `sections/_index.scss`. Defina seus tokens semânticos nas partials onde forem usados e utilize as classes de layout e componentes do AXIS como base.

## Começando um novo projeto com o AXIS

Ao clonar o AXIS para um novo projeto, o fluxo recomendado é:

1. **Atualize o `index.html`** — substitua os placeholders de SEO, OG e Twitter Card com os dados reais do projeto
2. **Defina sua identidade visual** — atualize o `manifest.json` com nome, cor de tema e ícones do projeto
3. **Configure seus tokens semânticos** — adicione as variáveis de cor semânticas em `_colors.scss` e ajuste os valores de tipografia em `_typography.scss` conforme a fonte escolhida
4. **Estilize header e footer** — as partials `sections/_header.scss` e `sections/_footer.scss` estão vazias e prontas para o seu projeto
5. **Crie suas seções** — adicione novas partials em `sections/` e registre-as no `sections/_index.scss`

## Otimização para produção

O AXIS gera o CSS minificado automaticamente via Live Sass Compiler. Para projetos onde o tamanho final do bundle é crítico, considere usar o **PurgeCSS** para remover classes CSS não utilizadas do build de produção.

→ [purgecss.com](https://purgecss.com)

O JavaScript (`src/js/script.js`) pode ser minificado manualmente antes do deploy. Ferramentas recomendadas: [Terser](https://terser.org) ou [Toptal JS Minifier](https://www.toptal.com/developers/javascript-minifier).

## Contribuindo

Contribuições são bem-vindas. Veja [CONTRIBUTING.md](./CONTRIBUTING.md) para saber como abrir issues e propor melhorias.

Se o AXIS foi útil no seu projeto, considere apoiar o desenvolvimento:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)

## Licença

MIT License — © 2026 · Lucas Couto

Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.


## Autor

Desenvolvido com muito código e café por [Lucas Couto](https://linkedin.com/in/lucas-coutoti).

Conheça meu trabalho ou entre em contato pelo site [Lucas Code](https://bio.site/lucascode).