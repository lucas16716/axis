<div align="center">

<img src="public/assets/favicon/favicon.svg" width="130" height="130" alt="AXIS symbol"/>

# AXIS

**A modern Sass architecture and starter foundation for scalable, maintainable web projects**

_Structure your frontend. Focus on building, not configuring_

[![Version](https://img.shields.io/badge/version-2.0.0-e8e4de?style=flat-square&labelColor=10b981&color=1c1b2e)](https://github.com/lucas16716/axis/releases)&nbsp; [![Template](https://img.shields.io/badge/template-ready-e8e4de?style=flat-square&labelColor=3437e6&color=1c1b2e)](https://github.com/lucas16716/axis/generate)&nbsp; [![License](https://img.shields.io/badge/license-MIT-e8e4de?style=flat-square&labelColor=ef4444&color=1c1b2e)](https://github.com/lucas16716/axis/blob/main/LICENSE)&nbsp; ![GitHub Repo stars](https://img.shields.io/github/stars/lucas16716/axis?style=social)

🇺🇸 [Read in English](./README.md)

</div>

## O que é o AXIS?

O AXIS é uma arquitetura moderna baseada em Sass e impulsionada pelo Vite, projetada para estruturar projetos frontend de forma clara, escalável e com altíssima performance.

Une a simplicidade do desenvolvimento tradicional (HTML, Sass e JavaScript) com o poder das ferramentas modernas de automação. O Vite entrega um servidor de desenvolvimento com atualização instantânea (HMR) e um processo de build que compila, prefixa e minifica tudo automaticamente para produção. Clone, instale as dependências, defina seus tokens e comece a desenvolver com uma base sólida: reset normalizado, tipografia configurada, sistema de layout funcional e de fácil edição, componentes neutros prontos para receber sua identidade visual, utilitários que agilizam o desenvolvimento e um sistema modular pronto para qualquer escala.

## Filosofia

O AXIS foi construído em torno de seis princípios fundamentais:

**Desenvolvimento moderno e ágil** — O Vite conduz toda a experiência de desenvolvimento, eliminando configurações complexas e focando em velocidade. A presença do Node.js e do NPM torna o projeto escalável e permite a integração profissional de bibliotecas externas.

**Simplicidade arquitetural** — A estrutura de pastas é direta e previsível. Cada camada — tanto no Sass quanto no JavaScript — possui uma responsabilidade clara. O JS segue o padrão de ES Modules, mantendo a lógica organizada em arquivos isolados e limpos.

**Arquitetura Sass modular** — Cinco camadas bem separadas que se comunicam através de `@use` e `@forward`, criando uma hierarquia lógica de estilos: Abstracts → Base → Layout → Components → Sections. Tudo é processado em memória durante o desenvolvimento para garantir performance máxima.

**Token-driven design** — Todos os valores visuais vêm de tokens. Tokens primitivos ficam centralizados em `abstracts/tokens/` e são acessíveis globalmente via `@use`. Tokens semânticos são definidos localmente na partial onde são consumidos — eliminando navegação desnecessária entre arquivos e mantendo os valores próximos de onde são usados.

> Ex: tokens semânticos em `base/_typography.scss` para tipografia, em `abstracts/tokens/_spacing.scss` para configuração de layout, e dentro de cada componente para seus próprios valores de padding, transição e tamanho.

**Desktop-first workflow** — A arquitetura parte do layout maior e adapta para telas menores via `@include respond()`. Possui suporte completo a `respond-up()` para estratégias de progressive enhancement.

**Automação e performance** — Todo o processo de compilação, prefixação e minificação (CSS e JS) é automatizado pelo Vite. Não há necessidade de extensões de terceiros ou minificação manual. O `index.html` já vem com meta tags de SEO e Open Graph pré-configuradas, e uma estratégia eficiente de favicons (`.ico` na raiz para compatibilidade com crawlers, formatos modernos em `public/assets/favicon/`). Cada pasta e arquivo do AXIS possui documentação, dicas e comentários que guiam para as melhores práticas de desenvolvimento frontend.

## Stack

| Tecnologia  | Uso                                                         |
| ----------- | ----------------------------------------------------------- |
| Vite        | Servidor de desenvolvimento (HMR) e bundling de produção    |
| HTML5       | Template base com meta tags de SEO, OG e PWA                |
| Sass (SCSS) | Arquitetura modular com design tokens                       |
| JavaScript  | Arquitetura modular baseada em módulos nativos (ES Modules) |

## Estrutura do projeto

```
axis/
├── public/
│   ├── assets/
│   │   ├── docs/                → Documentos para download
│   │   ├── favicon/             → Ícones modernos (.svg, .png)
│   │   ├── media/
│   │   │   ├── img/             → Imagens raster (.webp, .jpg, .png)
│   │   │   └── video/           → Vídeos (.webm, .mp4)
│   │   └── svg/                 → Vetores, ícones e ilustrações
│   ├── favicon.ico              → Ícone legacy (na raiz para melhor compatibilidade)
│   └── manifest.json            → Configurações de PWA e ícones para o navegador
├── src/
│   ├── js/
│   │   ├── base/                → Scripts globais e funções utilitárias
│   │   ├── components/          → Lógica isolada de componentes (menu, modal)
│   │   ├── vendor/              → Configurações de libs externas (Swiper, GSAP)
│   │   └── script.js            → Entry point principal — importa módulos JS e o Sass
│   └── sass/
│       ├── abstracts/           → Tokens, funções e mixins
│       ├── base/                → Reset, tipografia e estilos globais
│       ├── layout/              → Container, flex e grid
│       ├── components/          → Estilos de componentes neutros
│       ├── sections/            → Estilos de seções do projeto
│       └── main.scss            → Entry point do Sass (importado via script.js)
├── .gitignore                   → Arquivos ignorados pelo Git (node_modules, dist)
├── CHANGELOG.md                 → Registro de versão do projeto
├── CONTRIBUTING.md              → Guia de como contribuir com o projeto
├── index.html                   → Template principal do projeto
├── LICENSE                      → Licença do projeto (MIT)
├── package.json                 → Gerenciamento de dependências e scripts do NPM
├── README.md                    → Documentação em Inglês
├── README-ptbr.md               → Documentação em Português
└── vite.config.js               → Configuração do Vite (servidor, build e paths)
```

## Arquitetura Sass

O AXIS organiza o Sass em **cinco camadas** com responsabilidades claras, seguindo os princípios do ITCSS:

**1. Abstracts** — Nada aqui gera CSS diretamente. É a base inteira do sistema.

- **`tokens/`** — 9 arquivos de design tokens com valores genéricos, padronizados e escaláveis: colors, spacing, typography, breakpoints, motion, elevation, layers, radius e opacity
- **`functions/`** — acesso tipado a tokens via `bp()` e `z()`, e helpers de cor com `color.scale()`
- **`mixins/`** — container, flex, grid, grid-auto, respond, respond-up, absolute-center, focus-ring, visually-hidden e truncate

**2. Base** — Normalização e estilos globais sem classes.

- **`_reset.scss`** — box-sizing, reset de margin/padding, focus-ring acessível, text-size-adjust e scroll-behavior
- **`_typography.scss`** — fonte base com tokens semânticos, escala de headings em Major Third (1.25)
- **`_global.scss`** — imagens responsivas, herança de fonte, prefers-reduced-motion
- **`_utilities.scss`** — sr-only, display, visibility responsiva, position, alinhamento de texto, truncate e interação

**3. Layout** — Sistema de layout estrutural sem opiniões visuais.

- **`_container.scss`** — `.container` e variantes `.container-{sm|md|lg|xl|xxl}`
- **`_flex.scss`** — `.flex` com modificadores de direção, justify e align
- **`_grid.scss`** — `.grid-{1-12}`, `.col-span-{1-12}`, `.grid-auto` e variantes responsivas

**4. Components** — Componentes neutros e token-driven. Sem cores definidas — usam `currentColor` e herdam do contexto.

- **`_button.scss`** — tamanhos (sm/md/lg/xl), shapes (square/circle), variantes (pill/ghost), estado disabled
- **`_card.scss`** — estático e interativo, com estrutura `card__content` e modificadores de alinhamento de conteúdo
- **`_badge.scss`** — inline, pill, neutro

**5. Sections** — Partials vazias para **header** e **footer**. Prontas para você estilizar de acordo com o projeto.

## Design Tokens

| Arquivo             | O que define                                                                                          |
| ------------------- | ----------------------------------------------------------------------------------------------------- |
| `_colors.scss`      | Escala de cinzas (white → black) + 4 cores funcionais (green, yellow, red, blue)                      |
| `_spacing.scss`     | Escala macro 8pt (layout) + escala micro (UI controls) + tokens semânticos `$gutter` e `$section-pad` |
| `_typography.scss`  | 18 tamanhos (Major Third + UI), pesos, line-heights e letter-spacings                                 |
| `_breakpoints.scss` | 7 breakpoints desktop-first: xxl, xl, lg, md, sm, xs, xxs                                             |
| `_motion.scss`      | 5 durações + 4 curvas de easing (standard, in, out, back)                                             |
| `_elevation.scss`   | 5 níveis de sombra (none → lg)                                                                        |
| `_layers.scss`      | Z-index semântico: back, base, sticky, header, dropdown, overlay, modal, tooltip                      |
| `_radius.scss`      | 6 raios: xs, sm, md, lg, xl, full                                                                     |
| `_opacity.scss`     | 6 níveis: 0, 20, 40, 60, 80, 100                                                                      |

## Sistema de Layout

### Container

```html
<div class="container">
  <!-- max-width: 1200px (padrão via mixin) -->
  <div class="container-sm"><!-- max-width: 640px --></div>
  <div class="container-md"><!-- max-width: 768px --></div>
  <div class="container-lg"><!-- max-width: 1024px --></div>
  <div class="container-xl"><!-- max-width: 1200px --></div>
  <div class="container-xxl"><!-- max-width: 1280px --></div>
</div>
```

### Flex

```html
<div class="flex items-center justify-between">
  <div class="flex flex-col items-start">
    <div class="flex flex-wrap justify-center"></div>
  </div>
</div>
```

Modificadores disponíveis: `flex-col`, `flex-wrap`, `justify-start`, `justify-center`, `justify-between`, `justify-end`, `items-stretch`, `items-center`, `items-start`, `items-end`.

### Grid

```html
<div class="grid-3">
  <!-- 3 colunas fixas -->
</div>

<div class="grid-3 grid-1-md">
  <!-- 3 colunas → 1 coluna em md -->
</div>

<div class="grid-auto">
  <!-- colunas responsivas automáticas -->
  <div class="col-span-2"><!-- item ocupa 2 colunas --></div>
</div>
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
  <div class="card__content is-center">...</div>
</div>
```

Modificadores de alinhamento: `is-start`, `is-center`, `is-end`.

### Badge

```html
<span class="badge">Default</span>
```

O badge herda cor via `currentColor` — aplique a cor pelo elemento pai, diretamente via `style` ou por uma classe de cor do seu projeto.

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

### 2. Instale as dependências

```bash
npm install
```

### 3. Inicie o servidor de desenvolvimento

```bash
npm run dev
```

O Vite inicia um servidor local com HMR. Qualquer alteração em arquivos `.scss` ou `.js` é refletida instantaneamente no browser — sem compilação manual necessária.

### 4. Comece a construir

Adicione suas seções em `src/sass/sections/` e registre-as no `sections/_index.scss`. Defina seus tokens semânticos nas partials onde forem usados e utilize as classes de layout e componentes do AXIS como base.

### 5. Gere o build de produção

```bash
npm run build
```

O Vite compila, prefixa e minifica todo o CSS e JavaScript automaticamente. O resultado otimizado fica na pasta `dist/`, pronto para o deploy.

## Começando um novo projeto com o AXIS

Ao clonar o AXIS para um novo projeto, o fluxo recomendado é:

1. **Atualize o `index.html`** — substitua os placeholders de SEO, OG e Twitter Card com os dados reais do projeto
2. **Defina sua identidade visual** — atualize o `public/manifest.json` com nome, cor de tema e ícones do projeto
3. **Configure seus tokens semânticos** — adicione as variáveis de cor semânticas em `_colors.scss` e ajuste os valores de tipografia em `_typography.scss` conforme a fonte escolhida
4. **Estilize header e footer** — as partials `sections/_header.scss` e `sections/_footer.scss` estão vazias e prontas para o seu projeto
5. **Crie suas seções** — adicione novas partials em `sections/` e registre-as no `sections/_index.scss`

## Otimização para produção

Rodar `npm run build` aciona o pipeline completo de produção do Vite — CSS e JavaScript são automaticamente compilados, prefixados e minificados. Nenhum passo manual necessário.

Para projetos onde o tamanho final do bundle é crítico, considere usar o **PurgeCSS** para remover classes CSS não utilizadas do build de produção.

→ [purgecss.com](https://purgecss.com)

## Contribuindo

Contribuições são bem-vindas. Veja [CONTRIBUTING.md](./CONTRIBUTING.md) para saber como abrir issues e propor melhorias.

Se o AXIS foi útil no seu projeto, considere apoiar o desenvolvimento:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)

## Licença

MIT License — © 2026 Lucas Couto

Veja o arquivo [LICENSE](./LICENSE) para mais detalhes.

## Autor

Desenvolvido com muito código e café por [Lucas Couto](https://linkedin.com/in/lucas-coutoti).

Conheça meu trabalho ou entre em contato pelo site [Lucas Code](https://bio.site/lucascode).
