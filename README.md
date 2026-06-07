# ⚡ Turbinando Experts — Landing Page

> **Sistemas sob medida com IA para pequenas empresas.**
> Dashboards, CRM, automações e agentes de IA — comece com 1 módulo, escale depois.

[![Deploy](https://img.shields.io/badge/Cloudflare%20Pages-Live-F38020?logo=cloudflarepages&logoColor=white)](https://turbinando-experts.pages.dev/)
[![HTML](https://img.shields.io/badge/HTML5-Single%20Page-E34F26?logo=html5&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-Proprietary-333)](#licença)

🔗 **Live:** [turbinando-experts.pages.dev](https://turbinando-experts.pages.dev/)

---

## 📋 Sobre o Projeto

Landing page de alta conversão para a marca **Turbinando Experts** (Kiko Soares — Porto Alegre/RS).

O objetivo é captar leads qualificados via **WhatsApp** para uma call gratuita de 30 minutos, onde se apresenta a proposta de construção de sistemas sob medida com IA para o negócio do cliente.

### Proposta de valor

| Módulo | O que faz |
|--------|-----------|
| 🤖 **Agente IA** | Atendimento inteligente no WhatsApp 24/7 |
| 📊 **Dashboard** | Painel visual com métricas do negócio em tempo real |
| 📇 **CRM** | Gestão de leads e clientes integrada |
| ⚙️ **Automação** | Fluxos que eliminam tarefas repetitivas |

---

## 🎨 Design & Estética

- **Tema:** "Terminal Operacional" — cyberpunk-tech, verde neon sobre fundo escuro
- **Cor principal:** `#00E676` (verde neon) sobre `#050807`
- **Tipografia:**
  - Display: [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk)
  - Body: [Manrope](https://fonts.google.com/specimen/Manrope)
  - Mono/accents: [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
- **Animações:** scroll-reveal via IntersectionObserver, marquee infinito, shine effects, glassmorphism no header

---

## 🏗️ Estrutura da LP

```
1.  Top banner (shine animation)
2.  Header sticky (glassmorphism + nav + CTA WhatsApp)
3.  Hero — H1 + terminal mockup de briefing
4.  Marquee — 8 segmentos atendidos (loop infinito)
5.  Dor — 4 pain cards
6.  Solução — Timeline 4 passos
7.  O que construo — 4 cards de módulos
8.  Comparativo — "Genérico vs. Sob medida"
9.  Resultados — 4 cards de métricas
10. Depoimentos — 8 cards (casos ilustrativos)
11. Sobre — Kiko Soares (avatar, stats, stack)
12. FAQ — 6 perguntas
13. CTA Final
14. Footer + Sticky CTA mobile
```

---

## 📁 Estrutura de Arquivos

```
├── index.html              # LP completa v3.0 (~77KB, self-contained)
├── index.html.v2.html      # Backup da v2.0 (referência)
├── favicon.svg             # Ícone ⚡
├── apple-touch-icon.svg    # PWA icon 180×180
├── og-image.svg            # Open Graph 1200×630
├── manifest.json           # PWA manifest
├── robots.txt              # SEO + AI crawlers permitidos
├── sitemap.xml             # 3 URLs indexadas
├── _headers                # Cloudflare Pages (CSP, HSTS, cache)
├── ESTADO.md               # Estado do projeto / changelog
├── .gitignore              # Exclusões padrão
└── README.md               # Este arquivo
```

---

## 🚀 Como Rodar Localmente

O projeto é um arquivo HTML estático — **zero dependências, zero build step**.

```bash
# Opção 1 — Abrir direto
start index.html          # Windows
open index.html           # macOS

# Opção 2 — Servidor local (recomendado pra testar PWA/headers)
npx serve .
# ou
python -m http.server 8000
```

---

## ☁️ Deploy

O projeto está configurado para **Cloudflare Pages**:

1. Conecte o repositório GitHub no painel [Cloudflare Pages](https://dash.cloudflare.com/)
2. **Build command:** _(vazio)_
3. **Output directory:** `/`
4. O arquivo `_headers` já define CSP, HSTS e cache automaticamente

---

## 📊 SEO & GEO

| Item | Status |
|------|--------|
| Meta description | ✅ 138 chars |
| Open Graph + Twitter Cards | ✅ |
| Canonical + hreflang pt-BR | ✅ |
| JSON-LD (7 schemas) | ✅ Organization, LocalBusiness, Person, Service, FAQPage, BreadcrumbList, WebSite |
| Sitemap XML | ✅ 3 URLs |
| robots.txt + AI crawlers | ✅ GPTBot, ClaudeBot, PerplexityBot, Google-Extended, Applebot |
| GEO otimizado | ✅ TL;DR, definições, headings em pergunta, FAQ curta, dados citáveis |

---

## ♿ Acessibilidade & Mobile

- `viewport-fit=cover` com `safe-area-inset` no sticky CTA
- Skip-link, `focus-visible` verde 2px, 21+ `aria-labels`
- `prefers-reduced-motion` desativa todas as animações
- `prefers-color-scheme: dark` (padrão)
- Sticky CTA mobile aparece após o hero via `requestAnimationFrame`

---

## 🛠️ Tech Stack

| Camada | Tecnologia |
|--------|------------|
| Markup | HTML5 semântico (single-file, self-contained) |
| Estilo | CSS3 vanilla (custom properties, clamp, grid, flexbox) |
| JS | Vanilla JS (IntersectionObserver, rAF, sem frameworks) |
| Fonts | Google Fonts (Space Grotesk, Manrope, JetBrains Mono) |
| Hosting | Cloudflare Pages |
| PWA | manifest.json + SVG icons |

---

## 📝 Changelog

### v3.1 — 04/jun/2026
- Ícones Academia/FitPro atualizados (halterofilista com barra)

### v3.0 — 04/jun/2026
- **Pivot de posicionamento:** "agente de IA no WhatsApp em 7 dias" → "sistemas sob medida com IA"
- Nova seção "O que construo" (4 cards modulares)
- Hero com terminal mockup de briefing
- 4 depoimentos reframed para sistemas
- FAQ atualizada
- JSON-LD atualizado (7 schemas)

---

## 👤 Autor

**Kiko Soares** — Especialista em Sistemas Sob Medida com IA
- 📍 Porto Alegre/RS
- 💬 [WhatsApp](https://wa.me/5551920000513?text=Quero+a+an%C3%A1lise+gratuita+do+meu+neg%C3%B3cio)
- 🐙 [GitHub](https://github.com/KikoSoares-DataDriven)

---

## 📄 Licença

Este projeto é **proprietário**. Todos os direitos reservados © 2026 Kiko Soares.
