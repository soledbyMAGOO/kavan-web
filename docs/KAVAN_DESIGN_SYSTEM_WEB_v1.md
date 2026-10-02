# KAVAN — Design System Web v1.0

> Documento de referência para desenvolvimento do site institucional/comercial da KAVAN.
>
> As referências da Goomer devem ser usadas **somente como referência de arquitetura de informação, padrões de conversão e organização de conteúdo**. A interface final **não deve parecer uma cópia da Goomer**. A identidade visual deve ser integralmente KAVAN: escura, tecnológica, premium, cinematográfica, com metal/prata e iluminação de acento azul ou vermelha.
>
> As imagens fornecidas da KAVAN são a fonte principal deste Design System. Onde não existe evidência visual — principalmente mobile — as regras abaixo são uma extensão coerente da linguagem existente.

---

## 0. Direção geral

### Personalidade visual

A KAVAN deve transmitir:

- tecnologia para restaurantes;
- sofisticação;
- confiança operacional;
- agilidade;
- controle;
- produto premium;
- estética futurista sem aparência de “gaming”;
- ambiente escuro e elegante;
- foco no produto e na experiência do restaurante.

### Características observadas nas referências KAVAN

- fundos preto/grafite;
- superfícies em cinza muito escuro;
- logotipo metálico/branco;
- amplo uso de contraste;
- iluminação ambiente azul elétrico ou vermelha;
- elementos gráficos lineares;
- ícones outline;
- tablet/produto como protagonista;
- reflexos sutis e superfícies escuras;
- textura discreta em padrão geométrico;
- tipografia limpa, geométrica e com espaçamento amplo em títulos institucionais;
- cards com borda sutil e profundidade;
- interface de login com estética “dark premium”;
- CTA principal claro/metálico sobre fundo escuro.

### Princípio central

**Dark premium + tecnologia de restaurante + precisão operacional.**

A página deve parecer um software/produto tecnológico premium para restaurantes, e não um template SaaS genérico.

---

# 1. Cores

## 1.1 Paleta principal

Os valores abaixo foram aproximados a partir das imagens fornecidas e normalizados para uso consistente em interface.

| Token | HEX | Uso |
|---|---:|---|
| `brand-black` | `#050608` | Fundo institucional mais profundo |
| `bg-default` | `#07090C` | Background principal do site |
| `bg-subtle` | `#0B0E12` | Alternância de seções |
| `surface-1` | `#0D1014` | Cards e blocos principais |
| `surface-2` | `#14181E` | Superfícies elevadas |
| `surface-3` | `#1B2026` | Hover/elevated |
| `border-default` | `#2A3038` | Bordas discretas |
| `border-strong` | `#3A424D` | Bordas com maior ênfase |
| `text-primary` | `#F4F6F8` | Títulos e textos principais |
| `text-secondary` | `#A6ADB7` | Textos de apoio |
| `text-muted` | `#747C87` | Labels e metadados |
| `silver-100` | `#FFFFFF` | Brilho superior / CTA claro |
| `silver-200` | `#E6E9ED` | Prata clara |
| `silver-300` | `#C8CED6` | Prata média |
| `silver-400` | `#9EA6B1` | Prata escura |

## 1.2 Acento KAVAN Blue

A variante azul é a recomendada como **modo padrão do site**.

| Token | HEX | Uso |
|---|---:|---|
| `kavan-blue` | `#0893F0` | Accent principal |
| `kavan-blue-hover` | `#21A4FF` | Hover |
| `kavan-blue-active` | `#0076C8` | Active/pressed |
| `kavan-blue-soft` | `#082B45` | Background azul discreto |
| `kavan-blue-glow` | `rgba(8,147,240,.32)` | Glow e iluminação |

## 1.3 Acento KAVAN Red

A variante vermelha deve funcionar como **tema alternativo de campanha, seção ou produto**, não como segundo accent simultâneo.

| Token | HEX | Uso |
|---|---:|---|
| `kavan-red` | `#ED041D` | Accent alternativo |
| `kavan-red-hover` | `#FF2037` | Hover |
| `kavan-red-active` | `#C90018` | Active/pressed |
| `kavan-red-soft` | `#3A0B12` | Background vermelho discreto |
| `kavan-red-glow` | `rgba(237,4,29,.28)` | Glow e iluminação |

### Regra importante sobre azul e vermelho

Não usar azul e vermelho como dois CTAs concorrentes dentro do mesmo bloco.

Preferência:

```text
Site padrão → Azul
Campanha/variação específica → Vermelho
```

Uma seção deve declarar seu accent:

```html
<section data-accent="blue">...</section>
<section data-accent="red">...</section>
```

O alias `--accent` muda conforme o contexto.

Isso mantém a identidade KAVAN sem transformar o layout em estética gamer/cyberpunk.

---

## 1.4 Estados semânticos

| Estado | HEX | Uso |
|---|---:|---|
| `success` | `#83D3AF` | Online, sucesso, disponível |
| `warning` | `#FFB84D` | Atenção |
| `danger` | `#FF5C67` | Erro/destrutivo |
| `info` | `#53B7FF` | Informação |

O vermelho institucional KAVAN não deve substituir automaticamente `danger`.

---

## 1.5 Gradientes

### CTA metálico

```css
background:
  linear-gradient(
    180deg,
    #FFFFFF 0%,
    #E8EBEF 48%,
    #C8CED6 100%
  );
```

### Superfície dark

```css
background:
  linear-gradient(
    180deg,
    rgba(255,255,255,.035) 0%,
    rgba(255,255,255,.012) 100%
  ),
  #0D1014;
```

### Glow azul

```css
background:
  radial-gradient(
    circle,
    rgba(8,147,240,.22) 0%,
    rgba(8,147,240,0) 68%
  );
```

### Glow vermelho

```css
background:
  radial-gradient(
    circle,
    rgba(237,4,29,.20) 0%,
    rgba(237,4,29,0) 68%
  );
```

---

# 2. Tipografia

## 2.1 Logotipo

O lettering `KAVAN` é um elemento de marca e deve ser utilizado como **asset SVG/PNG**, nunca recriado com uma fonte do sistema.

Não utilizar `KAVAN` digitado em uma fonte aproximada no lugar do logotipo oficial.

## 2.2 Fonte de interface

As imagens não permitem identificar com segurança a família tipográfica original.

Para implementação web, utilizar:

```css
font-family:
  "Inter",
  "Helvetica Neue",
  Arial,
  sans-serif;
```

`Inter` é a fonte funcional recomendada para UI, mantendo o logotipo como ativo separado.

## 2.3 Escala tipográfica

| Token | Desktop | Line-height | Weight | Tracking |
|---|---:|---:|---:|---:|
| `display-xl` | 64px | 68px | 700 | -0.03em |
| `display-lg` | 56px | 62px | 700 | -0.025em |
| `h1` | 48px | 56px | 700 | -0.02em |
| `h2` | 40px | 48px | 700 | -0.015em |
| `h3` | 30px | 38px | 650/700 | -0.01em |
| `h4` | 24px | 32px | 650 | -0.005em |
| `body-lg` | 18px | 29px | 400 | 0 |
| `body-md` | 16px | 25px | 400 | 0 |
| `body-sm` | 14px | 21px | 400 | 0 |
| `label` | 14px | 18px | 600 | 0 |
| `caption` | 12px | 17px | 500 | 0.01em |
| `eyebrow` | 12px | 18px | 600 | 0.18em |

## 2.4 Títulos institucionais

Para blocos de marca:

```css
text-transform: uppercase;
letter-spacing: 0.14em;
font-weight: 500;
```

Usar esse tratamento de forma pontual para:

- eyebrow;
- subtítulos institucionais;
- labels de produto;
- pequenas chamadas;
- elementos próximos ao logotipo.

Não usar tracking largo em parágrafos.

---

# 3. Tokens CSS

```css
:root {
  /* =========================================================
     BRAND / BASE
  ========================================================= */
  --color-brand-black: #050608;

  --color-bg-default: #07090C;
  --color-bg-subtle: #0B0E12;

  --color-surface-1: #0D1014;
  --color-surface-2: #14181E;
  --color-surface-3: #1B2026;

  --color-border-default: #2A3038;
  --color-border-strong: #3A424D;

  --color-text-primary: #F4F6F8;
  --color-text-secondary: #A6ADB7;
  --color-text-muted: #747C87;

  --color-silver-100: #FFFFFF;
  --color-silver-200: #E6E9ED;
  --color-silver-300: #C8CED6;
  --color-silver-400: #9EA6B1;

  /* =========================================================
     KAVAN BLUE
  ========================================================= */
  --color-kavan-blue: #0893F0;
  --color-kavan-blue-hover: #21A4FF;
  --color-kavan-blue-active: #0076C8;
  --color-kavan-blue-soft: #082B45;
  --color-kavan-blue-glow: rgba(8, 147, 240, 0.32);

  /* =========================================================
     KAVAN RED
  ========================================================= */
  --color-kavan-red: #ED041D;
  --color-kavan-red-hover: #FF2037;
  --color-kavan-red-active: #C90018;
  --color-kavan-red-soft: #3A0B12;
  --color-kavan-red-glow: rgba(237, 4, 29, 0.28);

  /* Default accent */
  --accent: var(--color-kavan-blue);
  --accent-hover: var(--color-kavan-blue-hover);
  --accent-active: var(--color-kavan-blue-active);
  --accent-soft: var(--color-kavan-blue-soft);
  --accent-glow: var(--color-kavan-blue-glow);

  /* =========================================================
     SEMANTIC
  ========================================================= */
  --color-success: #83D3AF;
  --color-warning: #FFB84D;
  --color-danger: #FF5C67;
  --color-info: #53B7FF;

  /* =========================================================
     TYPOGRAPHY
  ========================================================= */
  --font-sans: "Inter", "Helvetica Neue", Arial, sans-serif;

  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-md: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.5rem;
  --font-size-2xl: 1.875rem;
  --font-size-3xl: 2.5rem;
  --font-size-4xl: 3rem;
  --font-size-5xl: 3.5rem;
  --font-size-6xl: 4rem;

  --line-height-tight: 1.08;
  --line-height-heading: 1.16;
  --line-height-body: 1.55;

  --font-weight-regular: 400;
  --font-weight-medium: 500;
  --font-weight-semibold: 600;
  --font-weight-bold: 700;
  --font-weight-extrabold: 800;

  /* =========================================================
     SPACING — 4px BASE
  ========================================================= */
  --space-0: 0;
  --space-1: 0.25rem;  /* 4 */
  --space-2: 0.5rem;   /* 8 */
  --space-3: 0.75rem;  /* 12 */
  --space-4: 1rem;     /* 16 */
  --space-5: 1.25rem;  /* 20 */
  --space-6: 1.5rem;   /* 24 */
  --space-8: 2rem;     /* 32 */
  --space-10: 2.5rem;  /* 40 */
  --space-12: 3rem;    /* 48 */
  --space-16: 4rem;    /* 64 */
  --space-20: 5rem;    /* 80 */
  --space-24: 6rem;    /* 96 */
  --space-30: 7.5rem;  /* 120 */
  --space-36: 9rem;    /* 144 */

  /* =========================================================
     RADIUS
  ========================================================= */
  --radius-xs: 6px;
  --radius-sm: 10px;
  --radius-md: 14px;
  --radius-lg: 20px;
  --radius-xl: 26px;
  --radius-pill: 999px;

  /* =========================================================
     SHADOW
  ========================================================= */
  --shadow-sm:
    0 8px 24px rgba(0, 0, 0, 0.22);

  --shadow-md:
    0 18px 50px rgba(0, 0, 0, 0.34);

  --shadow-lg:
    0 32px 90px rgba(0, 0, 0, 0.48);

  --shadow-accent:
    0 0 0 1px color-mix(in srgb, var(--accent) 28%, transparent),
    0 18px 70px color-mix(in srgb, var(--accent) 18%, transparent);

  /* =========================================================
     MOTION
  ========================================================= */
  --duration-fast: 140ms;
  --duration-base: 220ms;
  --duration-slow: 360ms;

  --ease-standard: cubic-bezier(.2, .8, .2, 1);
  --ease-enter: cubic-bezier(.16, 1, .3, 1);

  /* =========================================================
     LAYOUT
  ========================================================= */
  --container-max: 1200px;
  --container-wide: 1360px;
  --page-gutter: 24px;
  --header-height: 76px;

  /* =========================================================
     Z INDEX
  ========================================================= */
  --z-base: 0;
  --z-sticky: 20;
  --z-overlay: 80;
  --z-modal: 100;
  --z-toast: 120;
}

[data-accent="blue"] {
  --accent: var(--color-kavan-blue);
  --accent-hover: var(--color-kavan-blue-hover);
  --accent-active: var(--color-kavan-blue-active);
  --accent-soft: var(--color-kavan-blue-soft);
  --accent-glow: var(--color-kavan-blue-glow);
}

[data-accent="red"] {
  --accent: var(--color-kavan-red);
  --accent-hover: var(--color-kavan-red-hover);
  --accent-active: var(--color-kavan-red-active);
  --accent-soft: var(--color-kavan-red-soft);
  --accent-glow: var(--color-kavan-red-glow);
}
```

---

# 4. Layout

## 4.1 Container

```css
.container {
  width: min(
    calc(100% - (var(--page-gutter) * 2)),
    var(--container-max)
  );
  margin-inline: auto;
}
```

### Valores

| Contexto | Largura |
|---|---:|
| Conteúdo padrão | `1200px` |
| Hero/visual amplo | `1360px` |
| Texto longo / FAQ | `880–960px` |
| Modal grande | `720px` |
| Modal padrão | `520px` |

## 4.2 Grid

### Desktop

- 12 colunas;
- gap: `24px`;
- margens externas: `24–40px`;
- conteúdo centralizado.

### Tablet

- 8 colunas;
- gap: `20px`.

### Mobile

- 4 colunas;
- gap: `16px`.

## 4.3 Espaçamento de seções

```text
Desktop: 96–120px
Tablet: 72–80px
Mobile: 48–64px
```

Seções hero podem usar até `144px` no desktop.

---

# 5. Breakpoints e responsividade

As referências enviadas são majoritariamente desktop. Portanto, o comportamento mobile abaixo é uma extensão de produto, não uma cópia observada.

```css
/* Mobile first */

@media (min-width: 640px)  { /* sm */ }
@media (min-width: 768px)  { /* md */ }
@media (min-width: 1024px) { /* lg */ }
@media (min-width: 1280px) { /* xl */ }
@media (min-width: 1536px) { /* 2xl */ }
```

## Mobile `< 768px`

- header compacto;
- menu em drawer;
- hero em uma coluna;
- texto antes do produto;
- CTA principal full-width;
- cards em uma coluna;
- planos empilhados;
- FAQ full-width;
- imagens com `border-radius: 16px`;
- reduzir glows em ~40%;
- não usar parallax;
- sem textos menores que `14px` para conteúdo importante.

## Tablet `768–1023px`

- hero pode continuar 1 coluna;
- grids de cards em 2 colunas;
- pricing 2x2;
- navegação simplificada.

## Desktop `>= 1024px`

- hero 2 colunas;
- grids 2–4 colunas conforme o componente;
- header completo;
- mockups maiores;
- efeitos de iluminação mais visíveis.

---

# 6. Estrutura recomendada do site

A Goomer mostra padrões úteis de conversão — produtos, preços, FAQ e CTA — mas a estrutura visual da KAVAN deve ser própria.

## 6.1 Header

```text
[KAVAN logo]
Soluções
Como funciona
Planos
Sobre
FAQ

[Entrar]
[Falar com especialista / Solicitar demonstração]
```

### Comportamento

- sticky;
- fundo `rgba(7,9,12,.82)`;
- `backdrop-filter: blur(14px)`;
- border-bottom sutil;
- altura desktop: `76px`;
- logo entre `116–140px`;
- CTA principal compacto.

---

## 6.2 Hero

### Estrutura

Esquerda:

- eyebrow;
- H1;
- texto curto;
- dois CTAs;
- pequenos indicadores/benefícios.

Direita:

- tablet/interface KAVAN;
- ambiente dark;
- iluminação de accent;
- glow controlado.

### Direção de copy

Manter a frase já presente na identidade visual:

**“Tecnologia que simplifica. Mais tempo para o que importa.”**

Ela pode funcionar como headline, subheadline ou frase institucional.

### CTA

Principal:

**Solicitar demonstração**

Secundário:

**Conhecer soluções**

---

## 6.3 Benefícios rápidos

Usar 4 benefícios já visíveis no material da marca:

- Cardápio digital na mesa;
- Pedidos direto para a cozinha;
- Mais agilidade e aumento no ticket médio;
- Suporte especializado.

Não adicionar números, percentuais ou promessas quantitativas sem dados reais.

---

## 6.4 Soluções

Cards de solução inspirados na clareza da referência de mercado, porém em estética KAVAN.

Estrutura:

```text
[visual / mockup]
[eyebrow]
[Título]
[descrição]
[link + seta]
```

Exemplos de categorias somente quando confirmadas pelo produto:

- Cardápio digital;
- Autoatendimento;
- Pedidos;
- Gestão de atendimento;
- Integrações;
- Operação de cozinha.

Se alguma solução ainda não existir, não inventar.

---

## 6.5 “Como funciona”

3 ou 4 etapas:

```text
01 Configuração
02 Cardápio e operação
03 Pedido
04 Gestão / acompanhamento
```

Usar linha progressiva fina e accent.

---

## 6.6 Demonstração do produto

Seção mais visual:

- fundo preto;
- screenshot real;
- tablet/notebook;
- callouts pequenos;
- glow azul;
- pouca copy.

Evitar mockups genéricos caso existam telas reais.

---

## 6.7 Planos

Componente inspirado na legibilidade da referência enviada, mas visualmente KAVAN.

Preferência:

- 3 planos por linha;
- máximo 4;
- plano recomendado com borda/glow;
- preços grandes;
- lista objetiva;
- CTA claro;
- sem cor laranja ou estética copiada da Goomer.

Se os preços não estiverem definidos, usar conteúdo parametrizado e não inventar valores.

---

## 6.8 FAQ

Accordion com:

- superfície dark;
- 1px de borda;
- pergunta forte;
- botão redondo de `+`;
- estado aberto com `−`;
- resposta em texto secundário.

---

## 6.9 CTA final

Painel grande, imersivo:

```text
Pronto para simplificar a operação do seu restaurante?

[Solicitar demonstração]
[Falar com a KAVAN]
```

Fundo dark com glow azul ou vermelho.

---

## 6.10 Footer

Colunas:

```text
KAVAN
Soluções
Empresa
Suporte
Legal
Redes sociais
```

Rodapé quase preto.

---

# 7. Componentes

## 7.1 Botões

### Primary — Silver

É o CTA premium principal da identidade.

```css
.button-primary {
  min-height: 48px;
  padding: 0 22px;

  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;

  border: 0;
  border-radius: 10px;

  color: #090A0C;
  background:
    linear-gradient(
      180deg,
      #FFFFFF 0%,
      #E8EBEF 48%,
      #C8CED6 100%
    );

  font-weight: 700;

  box-shadow:
    inset 0 1px 0 rgba(255,255,255,.9),
    0 10px 30px rgba(0,0,0,.3);

  transition:
    transform var(--duration-fast) var(--ease-standard),
    box-shadow var(--duration-base) var(--ease-standard),
    filter var(--duration-base) var(--ease-standard);
}

.button-primary:hover {
  transform: translateY(-1px);
  filter: brightness(1.04);
  box-shadow:
    inset 0 1px 0 rgba(255,255,255,.95),
    0 14px 38px rgba(0,0,0,.4);
}

.button-primary:active {
  transform: translateY(0);
}
```

### Accent

```css
.button-accent {
  min-height: 48px;
  padding: 0 22px;

  color: #FFFFFF;
  background: var(--accent);

  border: 1px solid
    color-mix(in srgb, var(--accent) 75%, white 25%);

  border-radius: 10px;

  font-weight: 650;

  box-shadow:
    0 10px 34px
    color-mix(in srgb, var(--accent) 25%, transparent);
}

.button-accent:hover {
  background: var(--accent-hover);
}
```

### Outline

```css
.button-outline {
  min-height: 48px;
  padding: 0 22px;

  color: var(--color-text-primary);
  background: rgba(255,255,255,.02);

  border: 1px solid var(--color-border-strong);
  border-radius: 10px;
}

.button-outline:hover {
  background: rgba(255,255,255,.05);
  border-color: #59616C;
}
```

### Tamanhos

| Size | Height | Padding X |
|---|---:|---:|
| `sm` | 40px | 16px |
| `md` | 48px | 22px |
| `lg` | 56px | 28px |

---

## 7.2 Inputs

A tela de login indica:

- dark;
- border clara;
- ícone à esquerda;
- estados de focus nítidos;
- altura generosa.

```css
.input {
  width: 100%;
  min-height: 52px;

  padding: 0 16px;

  color: var(--color-text-primary);
  background: #0B0E12;

  border: 1px solid #3A424D;
  border-radius: 12px;

  outline: none;

  transition:
    border-color var(--duration-fast),
    box-shadow var(--duration-fast),
    background var(--duration-fast);
}

.input::placeholder {
  color: #6E7681;
}

.input:hover {
  border-color: #515B67;
}

.input:focus-visible {
  border-color: var(--accent);
  box-shadow:
    0 0 0 3px
    color-mix(in srgb, var(--accent) 22%, transparent);
}

.input[aria-invalid="true"] {
  border-color: var(--color-danger);
}
```

---

## 7.3 Cards

### Base

```css
.card {
  position: relative;
  overflow: hidden;

  background:
    linear-gradient(
      180deg,
      rgba(255,255,255,.035),
      rgba(255,255,255,.012)
    ),
    var(--color-surface-1);

  border: 1px solid var(--color-border-default);
  border-radius: var(--radius-lg);

  box-shadow: var(--shadow-sm);
}
```

### Hover

```css
.card-interactive {
  transition:
    transform var(--duration-base) var(--ease-standard),
    border-color var(--duration-base),
    box-shadow var(--duration-base);
}

.card-interactive:hover {
  transform: translateY(-4px);
  border-color:
    color-mix(in srgb, var(--accent) 35%, var(--color-border-default));

  box-shadow: var(--shadow-accent);
}
```

---

## 7.4 Solution Card

Estrutura:

```html
<article class="solution-card">
  <div class="solution-card__media"></div>
  <div class="solution-card__body">
    <span class="eyebrow">SOLUÇÃO</span>
    <h3>Cardápio digital</h3>
    <p>...</p>
    <a href="#">Conhecer solução →</a>
  </div>
</article>
```

### Regras

- imagem: 4:3 ou 16:10;
- body padding: `24–28px`;
- title máximo: 2 linhas;
- description: 2–4 linhas;
- accent em link/ícone;
- fundo da área visual pode ser um pouco mais escuro.

---

## 7.5 Pricing Card

```text
[badge opcional]
[NOME DO PLANO]
[descrição]
[preço]
[periodicidade]
[CTA]
[divisor]
[lista de recursos]
```

### Default

- `surface-1`;
- border `#2A3038`;
- raio `20px`;
- padding `28px`.

### Highlight

```css
.pricing-card--featured {
  border-color:
    color-mix(in srgb, var(--accent) 55%, #2A3038);

  box-shadow:
    0 0 0 1px
    color-mix(in srgb, var(--accent) 18%, transparent),
    0 26px 70px
    color-mix(in srgb, var(--accent) 12%, transparent);
}
```

---

## 7.6 Badge

```css
.badge {
  display: inline-flex;
  align-items: center;
  min-height: 28px;

  padding: 0 10px;

  border-radius: var(--radius-pill);

  font-size: 12px;
  font-weight: 650;

  color: var(--accent);
  background:
    color-mix(in srgb, var(--accent) 12%, transparent);

  border: 1px solid
    color-mix(in srgb, var(--accent) 28%, transparent);
}
```

---

## 7.7 Accordion / FAQ

Closed:

```text
┌──────────────────────────────────────────────┐
│ Pergunta                                 (+) │
└──────────────────────────────────────────────┘
```

Open:

```text
┌──────────────────────────────────────────────┐
│ Pergunta                                 (−) │
│                                              │
│ Resposta em texto secundário.                │
└──────────────────────────────────────────────┘
```

### Specs

- min-height fechado: `68px`;
- padding: `20–24px`;
- radius: `14px`;
- border: `1px solid #2A3038`;
- gap: `12px`;
- ícone: círculo `28–32px`.

---

## 7.8 Modal

- overlay `rgba(0,0,0,.72)`;
- backdrop blur `8px`;
- modal surface `#10141A`;
- radius `20px`;
- border `#2D343E`;
- max-width default `520px`;
- padding `28–32px`.

Entrada:

```css
opacity: 0;
transform: translateY(8px) scale(.985);
```

Final:

```css
opacity: 1;
transform: translateY(0) scale(1);
```

---

## 7.9 Navegação

### Desktop

- labels 14–15px;
- peso 500;
- gap 28–32px;
- estado hover em `text-primary`;
- estado normal em `text-secondary`;
- underline opcional de 2px em accent.

### Mobile

- drawer full-height;
- itens de 48–52px;
- CTA full-width ao final.

---

## 7.10 Status / disponibilidade

Inspirado no indicador de servidor presente na tela de login.

```css
.status-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: var(--color-success);
  box-shadow: 0 0 14px rgba(131,211,175,.45);
}
```

---

# 8. Fundo, textura e profundidade

A textura usada na tela de login é importante, mas deve ser discreta.

## Regras

- contraste baixo;
- nunca competir com texto;
- opacidade visual equivalente a `4–9%`;
- usar apenas em grandes áreas;
- aplicar vinheta nas bordas;
- reforçar centro visual com radial gradient.

Exemplo:

```css
.hero {
  background:
    radial-gradient(
      circle at 65% 45%,
      color-mix(in srgb, var(--accent) 12%, transparent),
      transparent 38%
    ),
    linear-gradient(
      180deg,
      rgba(255,255,255,.015),
      rgba(255,255,255,0)
    ),
    #07090C;
}
```

Evitar:

- grids neon fortes;
- scanlines;
- glitch;
- excesso de glow;
- partículas;
- animações futuristas chamativas.

A KAVAN deve parecer premium, não “cyberpunk”.

---

# 9. Direção de imagens

## 9.1 Fotografia

A linguagem observada nas imagens da KAVAN é:

- ambiente escuro;
- restaurantes modernos;
- luz azul ou vermelha;
- contraste forte;
- preto profundo;
- reflexos controlados;
- aspecto cinematográfico;
- dispositivo em destaque.

## 9.2 Mockups de produto

Preferir:

- tablet em ângulo 3/4;
- bordas reais do dispositivo;
- tela KAVAN legível;
- iluminação lateral;
- reflexo leve;
- fundo de restaurante desfocado;
- superfície preta/grafite.

Evitar:

- floating devices sem contexto;
- sombras exageradas;
- telas falsas;
- mockups brancos;
- cenários de escritório genérico;
- banco de imagem com aparência artificial.

## 9.3 Proporções

| Uso | Ratio |
|---|---:|
| Hero desktop | `16:9` ou composição livre 2 colunas |
| Banner institucional | ~`3:1` |
| Solution card | `4:3` ou `16:10` |
| Screenshot software | `16:10` |
| Social/card | `1.91:1` |
| Mobile visual | `4:5` |

---

# 10. Iconografia

Estilo:

- outline;
- geométrico;
- consistente;
- cantos discretamente arredondados;
- stroke `1.75–2px`;
- tamanho padrão `20–24px`.

Cores:

```text
default → text-secondary
destaque → accent
sucesso → success
```

Evitar ícones multicoloridos.

Bibliotecas adequadas:

- Lucide;
- Phosphor.

Escolher uma só biblioteca e manter consistência.

---

# 11. Motion

## Princípios

- rápido;
- preciso;
- discreto;
- sem bounce;
- sem efeitos “gamer”.

### Hover

```text
140–220ms
```

### Entrada de seção

```text
opacity 0 → 1
translateY 12px → 0
duration 360ms
```

### Card hover

```text
translateY(0) → translateY(-4px)
```

### Glow

Pode crescer levemente no hover, sem pulsação contínua.

### Reduced motion

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

# 12. Usabilidade e acessibilidade

## Contraste

- `text-primary` sobre `bg-default` deve ser o padrão;
- texto secundário nunca usar cinza escuro demais;
- CTA deve manter WCAG AA;
- não depender apenas da cor para transmitir estado.

## Área de toque

Mínimo:

```text
44 × 44px
```

Preferido em mobile:

```text
48 × 48px
```

## Focus

Todo item interativo deve ter `:focus-visible`.

```css
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
}
```

## Formulários

- label sempre visível;
- placeholder não substitui label;
- erros textuais;
- `aria-invalid`;
- `aria-describedby`.

## Accordion

- botão real;
- `aria-expanded`;
- `aria-controls`;
- navegação por teclado.

## Modais

- focus trap;
- ESC fecha;
- título com `aria-labelledby`;
- retornar foco ao elemento de origem.

---

# 13. Voz e copy

## Tom

- direto;
- profissional;
- premium;
- simples;
- seguro;
- orientado a benefício real.

## Evitar

- excesso de jargão;
- promessas irreais;
- “revolucionário” sem contexto;
- frases longas;
- números sem fonte;
- superlativos vazios.

## Estrutura ideal

```text
Problema → solução → benefício → ação
```

Exemplo:

> Simplifique o atendimento do seu restaurante com uma operação mais conectada e ágil.

Não afirmar ganhos percentuais sem dados.

---

# 14. Convenções de implementação

## Classes

BEM ou CSS Modules.

Exemplo:

```text
.hero
.hero__content
.hero__media

.solution-card
.solution-card__media
.solution-card__body

.pricing-card
.pricing-card--featured
```

## React

Se o projeto for React/Next:

```text
components/
  Button/
  Card/
  Header/
  Hero/
  SolutionCard/
  PricingCard/
  Accordion/
  Modal/
  Footer/

sections/
  HeroSection/
  BenefitsSection/
  SolutionsSection/
  ProductDemoSection/
  PricingSection/
  FAQSection/
  FinalCTASection/
```

## Regras

- tokens antes de hardcoded values;
- não repetir hex em componentes;
- SVG para logos;
- `currentColor` em ícones;
- imagens em WebP/AVIF;
- lazy-load abaixo da dobra;
- preload do hero;
- `aspect-ratio` para evitar layout shift;
- `clamp()` para títulos responsivos;
- sem CSS inline salvo valores dinâmicos.

---

# 15. Tipografia responsiva com clamp

```css
.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  line-height: 1.06;
  letter-spacing: -0.03em;
}

.section-title {
  font-size: clamp(2rem, 3.2vw, 2.5rem);
  line-height: 1.16;
  letter-spacing: -0.02em;
}
```

---

# 16. Regras visuais críticas

## FAZER

- fundo escuro como base;
- grande contraste;
- CTA branco/prata;
- accent azul como padrão;
- accent vermelho como variação controlada;
- produto real em destaque;
- fotografia de restaurante escura;
- bordas discretas;
- espaços generosos;
- layout limpo;
- ícones lineares;
- glow mínimo;
- microinterações rápidas;
- textura sutil;
- logo com bastante respiro.

## NÃO FAZER

- não copiar a paleta azul/branca da Goomer;
- não criar página predominantemente branca;
- não usar laranja para “plano destaque”;
- não usar azul e vermelho simultaneamente em excesso;
- não transformar o site em estética gamer;
- não exagerar em neon;
- não usar gradientes arco-íris;
- não usar glassmorphism forte;
- não usar cards coloridos aleatórios;
- não usar border-radius excessivo;
- não usar fonte futurista em parágrafos;
- não recriar o logo KAVAN com texto comum;
- não inventar funcionalidades;
- não inventar preços;
- não inventar depoimentos;
- não inventar métricas de negócio.

---

# 17. Hierarquia de CTA

Em cada seção:

```text
1 CTA principal
+
0 ou 1 CTA secundário
```

Nunca 3 botões com a mesma força visual.

### Hierarquia

1. `Primary Silver`
2. `Accent`
3. `Outline`
4. `Ghost/Text`

Exemplo hero:

```text
[Solicitar demonstração] ← Primary Silver
[Conhecer soluções]      ← Outline
```

---

# 18. Padrão visual de seção

```html
<section class="section" data-accent="blue">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">SOLUÇÕES KAVAN</span>
      <h2>Tecnologia para simplificar sua operação.</h2>
      <p>...</p>
    </div>

    <div class="section-content">
      ...
    </div>
  </div>
</section>
```

### Section heading

- largura máxima de copy: `680px`;
- eyebrow acima;
- título;
- 12–16px entre título e descrição;
- 40–56px até o conteúdo.

---

# 19. Skeleton de página

```text
01 Header
02 Hero
03 Benefícios rápidos
04 Soluções
05 Como funciona
06 Demonstração do produto
07 Benefícios operacionais
08 Integrações / ecossistema (se existir)
09 Planos
10 FAQ
11 CTA final
12 Footer
```

---

# 20. Checklist para o Claude

Antes de considerar a página pronta, validar:

- [ ] a página parece KAVAN e não Goomer;
- [ ] fundo principal é dark;
- [ ] logo KAVAN não foi recriado com texto;
- [ ] azul é o accent padrão;
- [ ] vermelho é usado apenas como modo alternativo controlado;
- [ ] não existe excesso de glow;
- [ ] tipografia é simples e moderna;
- [ ] cards têm bordas discretas;
- [ ] CTA primário tem tratamento prata/claro;
- [ ] hero mostra o produto;
- [ ] produto está inserido em contexto de restaurante;
- [ ] header é responsivo;
- [ ] menu mobile funciona;
- [ ] todos os botões têm hover/focus/active;
- [ ] inputs têm labels e foco visível;
- [ ] pricing funciona em mobile;
- [ ] FAQ funciona por teclado;
- [ ] modais têm focus trap;
- [ ] contraste atende WCAG AA;
- [ ] nenhuma feature foi inventada;
- [ ] nenhum preço foi inventado;
- [ ] imagens estão otimizadas;
- [ ] layout não possui CLS visível;
- [ ] `prefers-reduced-motion` está implementado;
- [ ] componentes usam tokens, não hex repetidos;
- [ ] o site funciona bem em 360px, 768px, 1024px, 1440px e 1920px.

---

# 21. Instrução final para implementação

Use este Design System como **fonte de verdade visual**.

A referência da Goomer serve apenas para entender:
- clareza na apresentação de soluções;
- card grid;
- planos;
- FAQ;
- navegação;
- CTAs;
- organização comercial do conteúdo.

Não copiar:
- identidade;
- cores;
- composição;
- componentes;
- tipografia;
- cards;
- ícones;
- preços;
- textos;
- imagens.

A interface deve ser construída do zero com identidade KAVAN.

## Prioridade de decisões

```text
1. Identidade visual KAVAN
2. Clareza e usabilidade
3. Conversão
4. Responsividade
5. Performance
6. Animações
```

Em caso de conflito, preservar os itens de maior prioridade.

---

# 22. Resumo visual em uma frase

> **KAVAN é um sistema para restaurantes com estética dark premium, base preta/grafite, metal/prata, tipografia limpa e iluminação tecnológica controlada em azul ou vermelho, com o produto real sempre como protagonista.**
