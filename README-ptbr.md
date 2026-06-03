<div align="center">

<img src="public/assets/favicon/favicon.svg" width="130" height="130" alt="AXIS symbol"/>

# AXIS

**Uma fundação frontend moderna construída para projetos web escaláveis, organizados e de fácil manutenção**

_Estruture seu frontend. Foque em construir, não em configurar_

[![Version](https://img.shields.io/badge/version-2.0.0-e8e4de?style=flat-square&labelColor=10b981&color=1c1b2e)](https://github.com/lucas16716/axis/releases)&nbsp; [![Template](https://img.shields.io/badge/template-ready-e8e4de?style=flat-square&labelColor=3437e6&color=1c1b2e)](https://github.com/lucas16716/axis/generate)&nbsp; [![License](https://img.shields.io/badge/license-MIT-e8e4de?style=flat-square&labelColor=ef4444&color=1c1b2e)](https://github.com/lucas16716/axis/blob/main/LICENSE)&nbsp; ![GitHub Repo stars](https://img.shields.io/github/stars/lucas16716/axis?style=social)

🇺🇸 [Read in English](./README.md)

</div>

## O que é o AXIS?

O AXIS é uma fundação frontend modular impulsionada pelo Vite, Sass e JavaScript moderno.

Foi projetado para ajudar desenvolvedores a iniciar projetos mais rapidamente com uma estrutura limpa, escalável e pronta para produção — sem impor decisões visuais ou padrões específicos de frameworks.

O AXIS não é um framework.

É um ponto de partida arquitetural flexível focado em:

- organização
- facilidade de manutenção
- escalabilidade
- experiência do desenvolvedor (DX)

Clone o projeto, defina seus design tokens, estruture suas seções e comece a desenvolver imediatamente.

## Recursos

- Arquitetura Sass modular
- Sistema de design tokens
- Workflow automatizado via Vite
- Estrutura nativa baseada em ES Modules
- Componentes neutros e reutilizáveis
- Utilitários de layout responsivo
- Template inicial com SEO & Open Graph
- Pipeline de build pronto para produção
- Organização de pastas escalável
- Estrutura preparada para animações (motion)
- Fundação totalmente personalizável

## Filosofia

O AXIS foi construído em torno de um princípio simples:

> fundações frontend devem acelerar o desenvolvimento — não ditar o design.

O projeto foca em fornecer:

- estrutura em vez de interfaces opinativas
- organização em vez de excesso de abstrações
- flexibilidade em vez de sistemas rígidos

Cada camada tem uma responsabilidade clara. Cada arquivo existe para simplificar a escalabilidade e a manutenção a longo prazo.

## Stack

| Tecnologia  | Uso                                                   |
| ----------- | ----------------------------------------------------- |
| Vite        | Servidor local (HMR) e build de produção automatizado |
| HTML5       | Template base com meta tags de SEO, OG e PWA          |
| Sass (SCSS) | Arquitetura de estilização modular                    |
| JavaScript  | Lógica frontend modular                               |

## Estrutura do Projeto

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
│   ├── manifest.json            → Configurações de PWA e ícones para o navegador
│   └── README-manifest.md       → Documentação e guia de configuração do PWA Manifest
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

**1. Abstracts** — Nada aqui gera CSS diretamente. É a fundação inteira do sistema.

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
| `_colors.scss`      | Escala de cinza (branco → preto) + 4 cores funcionais (verde, amarelo, vermelho, azul)                |
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

Modificadores disponíveis: `flex-col`, `flex-wrap`, `justify-start`, `justify-center`, `justify-between`, `justify-end`, `items-stretch`, `items-center`, `items-start`, `items-end`,`items-baseline`.

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

### 1. Crie seu repositório a partir do Template

O AXIS é um repositório modelo. No GitHub, clique no botão verde **Use this template > Create a new repository** para gerar um novo projeto limpo. Em seguida, clone o seu novo repositório:

```bash
git clone https://github.com/SEU-USUARIO/nome-do-seu-projeto.git
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

### 4. Comece a desenvolver

Aplique as configurações iniciais do seu projeto, adicione suas seções em `src/sass/sections/` e registre-as no `sections/_index.scss`. Defina seus tokens semânticos nos partials onde eles serão consumidos e utilize as classes utilitárias e os componentes base do AXIS como fundação do layout.

### 5. Faça o build de produção

```bash
npm run build
```

O Vite compila, prefixa e minifica todo o CSS e JavaScript automaticamente. O resultado otimizado fica na pasta `dist/`, pronto para o deploy.

## Iniciando um novo projeto com o AXIS

Ao utilizar o AXIS como ponto de partida para um novo projeto, siga este fluxo de trabalho para configurar sua base de forma limpa e organizada:

1. **Atualize as Configurações e Metadados**

   Antes de codificar, ajuste a identidade do novo projeto nos arquivos do ecossistema:

- `package.json`: Altere todos os campos até "homepage" com as informações específicas do seu projeto.
- `index.html`: Atualize todos os dados da tag `<head>` com as metatags corretas.
- `public/manifest.json`: Ajuste as chaves `name`, `short_name`, `theme_color`, `background_color` e os caminhos dos ícones para o PWA.

2. **Configure a identidade visual (Design Tokens)**

   Vá até a camada de fundação do SASS e configure as diretrizes visuais:

- Paleta de Cores: Defina os tokens de cores primárias, secundárias e os tons complementares.
- Tipografia: Importe as fontes necessárias e ajuste as variáveis de escala, pesos e famílias tipográficas.
- Grid e Espaçamentos: Ajuste as funções de dimensionamento e as variáveis de container caso o novo design exija.

3. **Personalize o Layout e Estrutura de Seções**

- Layout Global: Atualize as marcações e estilos do `header` e do `footer` globais.
- Componentes Reutilizáveis: Crie ou adapte blocos atômicos dentro de `src/sass/components/`.
- Seções Isoladas: Construa os blocos únicos da página em `src/sass/sections/` e registre-os explicitamente no `sections/_index.scss`.

4. **Codifique com Confiança**

   Com as dependências limpas, variáveis injetadas e o servidor do Vite rodando redondo em segundo plano, sua fundação técnica está blindada para iniciar o desenvolvimento.

## Otimização para produção

Rodar `npm run build` aciona o pipeline completo de produção do Vite — CSS e JavaScript são automaticamente compilados, prefixados e minificados. Nenhum passo manual necessário.

Para projetos onde o tamanho final do bundle é crítico, considere usar o **PurgeCSS** para remover classes CSS não utilizadas do build de produção.

→ [purgecss.com](https://purgecss.com)

## Contribuindo

Contribuições são bem-vindas. Veja [CONTRIBUTING.md](./CONTRIBUTING.md) para saber como abrir issues e propor melhorias.

Se o AXIS ajudou você ou acelerou o seu projeto, considere apoiar seu desenvolvimento:

☕ [Buy Me a Coffee](https://buymeacoffee.com/lucascode)

## Licença

MIT License — © 2026 Lucas Couto

Consulte o arquivo [LICENSE](./LICENSE) para mais detalhes.

## Autor

Desenvolvido com muito código e café por [Lucas Couto](https://linkedin.com/in/lucas-coutoti).

Conheça meu trabalho ou entre em contato pelo site [Lucas Code](https://bio.site/lucascode).
