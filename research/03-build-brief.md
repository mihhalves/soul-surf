# 03 — Brief do Site
## Projeto Social Soul Surf — Site Premium

---

## Objetivo

Criar o site mais premium e impactante do nicho de surf social no Brasil. O novo site deve:
1. Comunicar emoção e propósito em menos de 5 segundos
2. Converter visitantes em doadores com CTA claro e urgente
3. Superar todos os concorrentes em design, performance e experiência

---

## Stack Técnica

| Elemento | Decisão | Motivo |
|---|---|---|
| Base | HTML5 semântico | Performance máxima, sem dependências pesadas |
| Estilo | CSS3 custom | Controle total sobre design, sem framework obeso |
| Animações | GSAP 3 + ScrollTrigger | Animações suaves e com performance nativa |
| Fontes | Google Fonts (Glegoo + Poppins) | Fidelidade total à marca |
| Ícones | SVG inline | Performance e escalabilidade |
| Deploy | Arquivo único auto-contido | Máxima portabilidade |

---

## Arquitetura de Informação

```
1. [ NAVBAR ]        — Sticky, transparente → sólido ao scroll
2. [ HERO ]          — 100vh, imagem mar, headline animada, 2 CTAs
3. [ STATS ]         — Números de impacto, counter animado, fundo escuro
4. [ SOBRE ]         — Quem somos, foto, quote, fundação 2021
5. [ PROJETOS ]      — 3 cards: Surf+Inclusão / Educação / Meio Ambiente
6. [ MISSÃO/V/V ]    — 3 cards: Missão, Visão, Valores
7. [ CAMPANHA ]      — Água / poço artesiano, fundo azul gradiente
8. [ VIDEO ]         — Vídeo institucional YouTube embeddado
9. [ CTA FINAL ]     — "Sua doação transforma vidas reais" — Doe Agora
10. [ FOOTER ]       — Links, social, transparência, copyright
```

---

## Design System

### Cores
```css
--blue:       #0073A8   /* primária — CTAs, destaques */
--blue-dark:  #005a84   /* hover estados */
--green:      #4D917B   /* accent — cards, tags */
--white:      #FFFFFF   /* fundo principal */
--text:       #333333   /* corpo de texto */
--text-light: #666666   /* texto secundário */
--bg-light:   #F7F9FB   /* seções alternadas */
--bg-dark:    #0a1628   /* hero overlay, stats */
--bg-navy:    #051223   /* footer, CTA final */
--gold:       #F5A623   /* valores/destaque especial */
```

### Tipografia
```css
Headings: 'Glegoo', serif
Body:     'Poppins', sans-serif

H1 hero:    clamp(52px, 8vw, 96px) — bold, letter-spacing -0.02em
H2 section: clamp(28px, 4vw, 48px)
H3 cards:   22–26px
Body:       15–17px, line-height 1.7–1.85
Labels:     11px, uppercase, letter-spacing 0.25em
```

### Espaçamento
```
Section padding:  100px 0 (desktop) / 64px 0 (mobile)
Container max:    1200px
Container gutter: 24px
Card radius:      24px
Button radius:    50px (pill)
Gap entre cards:  28px
```

### Componentes

**Botão Primário:** `#0073A8`, texto branco, pill shape, hover: `#005a84` + translateY(-2px) + shadow azul
**Botão Outline:** bordas e texto branco 60% opacidade, hover: bg rgba white 15%
**Botão Branco:** bg branco, texto azul, para seções coloridas
**Section Label:** 11px, uppercase, tracking 0.25em, azul primário
**Cards:** bg branco, border-radius 24px, shadow suave, hover translateY(-8px)
**Stats:** fundo dark, números 40–64px Glegoo, destaque em azul para sufixos

---

## Animações GSAP

### Entrada da Página (Timeline)
```
delay 0.3s → badge hero fade in →
title clip-path reveal (1.0s) →
subtitle fade up →
desc fade up →
CTAs fade up →
scroll indicator fade
```

### Parallax
```
Hero bg → yPercent 30 ao fazer scroll (scrub)
```

### Scroll Triggers
```
Stats items     → opacity + translateY, trigger 85% viewport
Sobre (left)    → opacity + translateX(-40px), trigger 85%
Sobre (right)   → opacity + translateX(40px), trigger 85%
Project cards   → stagger 0.12s, translateY, trigger 88%
MVV cards       → stagger 0.15s, translateY, trigger 88%
Water section   → left/right reveals
Video section   → scale reveal (back.out easing)
CTA section     → reveal geral
```

### Contadores (Stats)
```
ScrollTrigger onEnter → gsap tween val: 0 → target, 2.2s, power2.out
Atualiza textContent em tempo real
```

### Navbar
```
Fade in ao load (from y:-20, opacity 0)
Classe .scrolled adiciona bg sólido após 50px de scroll
Hamburger → rotação das barras via GSAP
Mobile menu → slide + opacity toggle
```

---

## Conteúdo por Seção

### Hero
- Badge: "Esporte · Educação · Transformação Social"
- H1: "DO MAR PRA VIDA"
- H2: "Transformando vidas de crianças e adolescentes em situação de vulnerabilidade através do surf"
- Body: fundação 2021, Itanhaém/SP, inclusão social
- CTA 1: "♥ Doe Agora" → Benfeitoria
- CTA 2: "Conheça o Projeto" → âncora #about

### Stats (números de impacto)
- 200+ Jovens Impactados
- 4 Anos de Projeto
- 3 Frentes de Atuação
- 100% Impacto Social Real

### Sobre
- Section label: "Uma Onda de Solidariedade"
- H2: "Esporte que acolhe, educa e transforma"
- Quote: Mahatma Gandhi
- 2 parágrafos sobre fundação e foco
- Imagem à direita com badge "2021 / Fundado em Itanhaém/SP"

### Projetos (3 cards)
1. Surf e Inclusão — tag "Esporte"
2. Educação e Futuro — tag "Educação"
3. Cultura e Meio Ambiente — tag "Meio Ambiente"

### Missão/Visão/Valores (3 cards com top border colorida)
- Missão (azul) — 🎯
- Visão (verde) — 🌊
- Valores (dourado) — ⭐

### Campanha da Água
- Badge urgente: "💧 Campanha Urgente"
- H2: "Precisamos de água doce também"
- Body: poço artesiano, banho digno
- CTA: "♥ Quero Ajudar" → Benfeitoria

### Vídeo
- Section label: "Conheça o Projeto"
- H2: "Veja a transformação acontecer"
- Embed YouTube responsivo (aspect-ratio 16:9)

### CTA Final
- H2: "Sua doação transforma **vidas reais**" (em em azul)
- Body: cada contribuição garantindo mais aulas
- 2 CTAs: Doe Agora + Visitar Site Oficial

---

## SEO On-Page

```html
<title>Projeto Soul Surf — Do Mar Pra Vida</title>
<meta name="description" content="Projeto Social Soul Surf — Transformando vidas de crianças e adolescentes em vulnerabilidade social através do surf em Itanhaém/SP.">
<meta name="keywords" content="projeto social surf, soul surf, itanhaém, inclusão social, surf crianças, ONG surf">
<meta property="og:title" content="Projeto Soul Surf — Do Mar Pra Vida">
<meta property="og:description" content="Usando o surf como ferramenta de inclusão social e transformação de vidas desde 2021.">
lang="pt-BR"
```

Semântica: `<nav>`, `<main>`, `<section>`, `<footer>`, `<article>` corretamente utilizados.
Imagens com `alt` texts descritivos.
Links externos com `rel="noopener noreferrer"`.

---

## Performance

- **Sem WordPress** — HTML puro → < 2s load time
- **Fontes:** preconnect + display=swap
- **Imagens:** `loading="lazy"` em todas as imgs abaixo da dobra
- **GSAP:** CDN com cache; apenas plugins necessários (ScrollTrigger, TextPlugin)
- **CSS:** inline no `<head>`, crítico carregado imediatamente

---

## Responsividade

| Breakpoint | Layout |
|---|---|
| > 1024px | Desktop: grids 2–4 colunas, about lado a lado |
| 768–1024px | Tablet: stats 2 col, about empilhado, footer 2 col |
| < 768px | Mobile: tudo 1 coluna, hamburger menu, CTAs full-width |
| < 480px | Stats 1 coluna, simplificado |

---

## Acessibilidade

- `aria-label` em todos os botões sem texto visível
- Contraste de cores ≥ 4.5:1 (WCAG AA)
- `alt` em todas as imagens
- Menu keyboard-navigable
- `lang="pt-BR"` no html
- Foco visível nos elementos interativos

---

## Entregável

Arquivo: `site/index.html` — auto-contido, sem dependências locais.
Pode ser aberto diretamente no browser ou servido por qualquer servidor estático.
