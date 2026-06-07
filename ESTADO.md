# ESTADO — Turbinando Experts LP v3.0

> **Uso:** quando voltar, diga "voltei" e eu leio só este arquivo. Atualizar a cada mudança.

---

## 🎯 Projeto

Landing page "Turbinando Experts" — **sistemas sob medida com IA** para pequenas empresas (dashboards, CRM, automações, agente de IA). Dono: Kiko Soares, Porto Alegre/RS. WhatsApp: `+55 51 92000-0513`. Deploy target: `https://turbinando-experts.pages.dev/`.

## 🔄 Mudança v3.1 (04/jun/2026)

**Ícones Academia/FitPro:** SVG genérico (nuvem/cérebro no marquee, troféu no depoimento) → ícone de **pessoa levantando peso** (halterofilista com barra e anilhas).

- Marquee "segmentos atendidos": 2 ocorrências (1ª cópia + loop) trocadas
- Depoimento FitPro (casos ilustrativos): ícone do card trocado
- SVG mantém padrão `stroke` consistente com os demais ícones da LP

## 🔄 Mudança v3.0 (04/jun/2026)

**Pivot de posicionamento:** saiu "agente de IA no WhatsApp em 7 dias" → entrou "sistemas sob medida com IA, com agente como ponto de entrada, escalável conforme o resultado aparece".

- Backup v2.0 salvo em `index.html.v2.html`
- Nova seção "O que construo" (4 cards: Agente, Dashboard, CRM, Automação)
- 4 depoimentos reframe pra refletir sistemas (Imobiliária, Médica, Estética, Hotelaria); 4 mantêm foco no agente (Odonto, Salão, Pets, Academia)
- Hero com novo terminal mockup (mostra briefing de sistema, não conversa WhatsApp)
- FAQ: nova pergunta "Posso começar pequeno?" substitui "Tem garantia de resultado?"
- JSON-LD: Service + Person + FAQ atualizados

## 📁 Arquivos (pasta raiz)

| Arquivo | Função |
|---------|--------|
| `index.html` | LP completa v3.0 · 76.1 KB · 11 sections |
| `index.html.v2.html` | Backup v2.0 (não usar) |
| `favicon.svg` | Ícone ⚡ |
| `apple-touch-icon.svg` | PWA icon 180x180 |
| `og-image.svg` | Open Graph 1200x630 |
| `manifest.json` | PWA manifest |
| `robots.txt` | Permite 5 AI crawlers (GPTBot, Claude, Perplexity, Google-Extended, Applebot) |
| `sitemap.xml` | 3 URLs |
| `_headers` | Cloudflare Pages (CSP, HSTS, cache) |
| `LP-Agentes de IA no Seu Negócio - Copia.html` | Backup original (não usar) |
| `LP-Agentes de IA no Seu Negócio.md` | Backup original (não usar) |

## 🎨 Decisões Travadas

- **Estética:** "Terminal Operacional" (cyberpunk-tech, mono-font, neon #00E676 sobre preto #050807)
- **Tipografia:** Space Grotesk (display) + Manrope (body) + JetBrains Mono (accents)
- **Cor principal:** `#00E676` (verde neon) | BG: `#050807`
- **Idioma:** pt-BR
- **Tom:** direto, técnico, sem jargão vazio
- **Modo caveman:** ATIVO em todas respostas futuras

## 🏗️ Estrutura da LP (ordem)

1. Top banner (shine animation, copy v3.0)
2. Header sticky (glassmorphism, logo + nav + CTA WhatsApp)
3. **Hero** — H1 "Sistemas construídos pro seu negócio", TL;DR modular, terminal mockup de briefing
4. **Marquee** — 8 segmentos atendidos (loop infinito)
5. **Dor** — 4 pain cards (ferramentas prontas, planilhas no braço, atendimento travado, sem visibilidade)
6. **Solução** — Timeline 4 passos (call de imersão → arquitetura → 7d deploy → escala contínua)
7. **O que construo** — 4 cards (Agente, Dashboard, CRM, Automação) + callout "comece com 1 módulo"
8. **Comparativo** — Tabela "Genérico vs. Sob medida" (6 linhas)
9. **Resultados** — 4 cards (24h, 7d, -80%, +3x) com tags mono
10. **Depoimentos** — 8 cards (4 reframes sistema, 4 mantém agente) — "caso ilustrativo"
11. **Sobre** — Kiko Soares (avatar KS, stats 7d/4+/8+, stack de pills)
12. **FAQ** — 6 perguntas (incluindo "Posso começar pequeno?")
13. **CTA Final** — "Pronto pra ter um sistema seu?"
14. Footer + Sticky CTA mobile

## 📊 SEO/GEO Implementado

- **Meta:** description 138 chars, keywords v3.0, author, robots, article:modified_time
- **OG/Twitter:** atualizados pra "Sistemas sob medida com IA"
- **Canonical:** `https://turbinando-experts.pages.dev/`
- **Hreflang:** pt-BR
- **JSON-LD (7 schemas):** Organization, LocalBusiness, Person (Kiko — "Especialista em Sistemas Sob Medida com IA"), Service ("Sistemas Sob Medida com IA para Pequenas Empresas"), FAQPage (6 Q), BreadcrumbList, WebSite
- **GEO:** TL;DR no hero, definições, headings em pergunta, FAQ curta, dados citáveis, "Atualizado em jun/2026", autor com E-E-A-T

## 📱 Mobile + A11y

- viewport-fit=cover, safe-area-inset em sticky CTA
- skip-link, focus-visible verde 2px, 21× aria-labels
- prefers-reduced-motion desativa animações
- prefers-color-scheme: dark (default)
- Sticky CTA aparece após hero (rAF scroll)
- Scroll-reveal com IntersectionObserver vanilla

## 🔗 Links WhatsApp (todos apontam pra)

`https://wa.me/5551920000513?text=Quero+a+an%C3%A1lise+gratuita+do+meu+neg%C3%B3cio`

## 🚀 Deploy Pendente

```bash
# 1. Git init + commit + push pra GitHub
git init && git add . && git commit -m "Turbinando Experts v3.0 — sistemas sob medida"
git remote add origin <repo-url>
git push -u origin main

# 2. Cloudflare Pages
# → Workers & Pages → Create → Pages → Connect to Git
# → Build command: (vazio) · Output: /
```

## 📝 Conteúdo a Customizar (placeholders ou versões iniciais)

- `og-image.svg` — feito, mas considere trocar por versão PNG real (e atualizar copy pra refletir v3.0)
- Depoimentos marcados "caso ilustrativo" — trocar por reais quando houver
- WhatsApp `5551920000513` — confirmar se está correto
- Local: Porto Alegre/RS — confirmar

## ✅ Validações Feitas

- HTML well-formed: 11/11 sections, 20/20 articles, 141/141 divs, 38/38 svgs
- JSON-LD válido (7 schemas parseiam)
- Meta description 138 chars (≤155 ✓)
- sitemap.xml válido (3 URLs)
- manifest.json válido
- robots.txt com 5/5 AI bots
- Arquivo abre em browser

## 🔄 Próximos Passos Sugeridos

1. Subir pro Cloudflare Pages
2. Cadastrar em Google Search Console + Bing Webmaster
3. Trocar `turbinando-experts.pages.dev` pelo domínio custom (se houver)
4. Atualizar og-image.svg com nova copy v3.0 (ou PNG)
5. Adicionar Google Analytics / Plausible
6. A/B test no CTA (texto, cor, posição)
7. Adicionar depoimentos reais (com permissão) e remover "caso ilustrativo"
8. Adicionar seção "Cases reais" quando houver 2-3 pra mostrar

## 💡 Skills Carregadas neste Projeto

- frontend-design, seo-fundamentals, geo-fundamentals, web-design-guidelines
- caveman (modo persistente)
- copywriting (mentalidade aplicada no copy)

---

**Última atualização:** 04/jun/2026 23h15
**Status:** Pronto pra deploy ✅
**Modo conversa:** Caveman full (padrão)
