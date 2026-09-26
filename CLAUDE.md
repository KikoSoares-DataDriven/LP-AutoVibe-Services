# CLAUDE.md — LP Turbinando Experts

## O que é
Landing page estática (single-file) da marca **Turbinando Experts** (Kiko Soares, Porto Alegre/RS).
Objetivo: captar leads via WhatsApp para call gratuita de 30 min sobre sistemas/automações com IA.
Live: https://turbinandoexperts.com/ (Cloudflare Pages, deploy via push no `main` do GitHub).

## Stack
- HTML5 single-file, self-contained (`index.html`, ~98 KB). **Zero build, zero dependências.**
- CSS3 vanilla (custom properties) + Vanilla JS (IntersectionObserver, rAF).
- Google Fonts: Space Grotesk / Manrope / JetBrains Mono.
- Deploy: Cloudflare Pages. `_headers` define CSP/HSTS/cache.

## Arquivos-chave
| Arquivo | Função |
|---|---|
| `index.html` | A LP inteira (markup + CSS + JS + JSON-LD) |
| `sitemap.xml` / `robots.txt` | SEO; robots permite 5+ AI crawlers |
| `manifest.json`, `favicon.svg`, `apple-touch-icon.svg`, `og-image.svg` | PWA/social |
| `termos-de-uso.html`, `politica-de-privacidade.html` | Páginas legais |
| `ESTADO.md` | Changelog legado (v3.0/v3.1) — fonte histórica; canonical agora é `docs/STATE.md` |
| `_headers` | Cloudflare Pages headers |

## Comandos de verificação
- Validar JSON-LD: extrair o bloco `application/ld+json` de `index.html` e parsear (Python `json.loads`).
- Servir local: `npx serve .` ou `python -m http.server 8000`.
- Abrir: `start index.html`.

## Convenções
- pt-BR; tom direto, técnico, sem jargão vazio.
- Estética "Terminal Operacional": verde neon `#00E676` sobre `#050807`.
- Edições na LP = editar `index.html` diretamente (não há outro arquivo-fonte).
- Headings: 1× H1 (hero) + H2 por seção. Meta description ≤155 chars.

## Ciclo de trabalho
1. Ler `docs/STATE.md` antes de mexer.
2. Mudança pequena → implementar direto; média/grande → alinhar o que muda antes.
3. Verificar (HTML válido, JSON-LD parseia, links ok) antes de dar por pronto.
4. Registrar em `docs/STATE.md`; commit só quando o usuário pedir.

## KPIs de busca alvo
- Marca: "turbinando experts" **e** "turbinando expert" (singular — coberto via `alternateName` no schema + rodapé).
- Serviço/local: "automações e ia poa rs", "automações e ia para negócios" (title, description, eyebrow do hero, footer, JSON-LD).
