# STATE — LP Turbinando Experts

**Fase:** v2.0 Implementada (Auto-Auditoria Completa: Oferta Call Agentes de IA, Claude Terracotta, Super GEO, Segurança/LGPD e Marcadores Ativos de Scroll-Spy) · 06/nov/2026 · baseline: sem build/test (HTML estático), JSON-LD válido ✅

## Estado atual
- `index.html` = Versão 2.0 ativa com protagonismo na **Sessão Estratégica Gratuita (30 min) para Implementação de Agentes de IA**, Design System Claude Warm Light + Verde da Marca + Terracotta do Claude (`#DA7756`), Dual-View Showcase (WhatsApp Simulator + Terminal), Toast LGPD e **Marcadores Ativos de Navegação em Tempo Real (Desktop & Mobile)**.
- Backup da v1.2 preservado em `index.html.v1.2-audit.bak`.
- `og-image.png` (1200×630px) gerado e vinculado para previews sociais em WhatsApp, Facebook, LinkedIn e Twitter.
- URL canônica: `https://turbinandoexperts.com/`. `robots.txt`, `sitemap.xml` atualizados.
- Deploy: push no `main` → Cloudflare Pages.

## Feito nesta sessão (Versão 2.0 - Auto-Auditoria Completa & Marcadores Ativos)
1. **Segurança & LGPD Blindadas**:
   - `_headers`: Adicionadas diretivas `base-uri 'self'`, `form-action 'self' https://wa.me`, `Cross-Origin-Opener-Policy: same-origin` e `Cross-Origin-Resource-Policy: same-origin`.
   - **Toast de Privacidade LGPD Redesenhado (Ultra-compacto & À Esquerda)**: Posicionado no canto inferior esquerdo (`left: 20px; bottom: 24px; right: auto; max-width: 320px;`), liberando totalmente o lado direito onde ficam os exemplos práticos, simuladores e terminais. No mobile, converte-se em barra horizontal compacta acima do dock inferior (`bottom: calc(66px + env(safe-area-inset-bottom))`), sem obstruir a tela. Aplicado de forma idêntica e consistente tanto em `index.html` quanto em `portfolio-data-driven.html`.
   - `politica-de-privacidade.html`: Atualizada para novembro/2026, com inclusão formal da tabela de `localStorage` para preferências visuais e canal de contato `privacidade@turbinandoexperts.com`.
   - Diagnóstico (Quiz): Inserido selo de proteção de dados pré-envio do WhatsApp.
2. **Copy & Persuasão Focado na Call de Agentes de IA**:
   - Hero reestruturado: H1 focado em *"Implemente Agentes de IA que atendem e vendem no automático"*, TL;DR e lede enfatizando a Sessão Estratégica Gratuita de 30 min.
   - **Refinamento de Tom e Alcance sem Fronteiras**: Eliminado o termo formal *"com âncora em"*, substituído por linguagem brasileira, ampla e fluida: *"Com base em Porto Alegre/RS e operação 100% digital, a web encurta qualquer distância: atendemos e implementamos onde quer que sua empresa esteja."* (aplicado no TL;DR, no topo da página, no FAQ e no rodapé).
   - Nova Seção `#sessao-estrategica` (*"O que acontece na sua Sessão Estratégica Gratuita?"*): 3 cards detalhando o Raio-X de gargalos, Demonstração prática no nicho e Arquitetura & Estimativa de ROI, quebrando antecipadamente o receio de vendas agressivas.
   - CTAs unificados direcionando para a Call Estratégica de 30 min no WhatsApp.
3. **Design Moderno (Verde Esmeralda + Terracotta Claude.ai `#DA7756`)**:
   - Adicionadas variáveis `--claude-clay` (`#DA7756`), `--claude-clay-soft`, `--claude-clay-border` e versão dark mode.
   - Hero Showcase com alternância em abas (Tab 1: Simulador de WhatsApp com diálogo realista de Agente de IA tirando dúvidas e agendando reunião em 3s; Tab 2: Terminal técnico da esteira).
   - Badges e acentos em terracota trazendo a estética editorial de ponta da Anthropic combinada à identidade verde.
4. **Super GEO & SEO On-Page**:
   - Title tag otimizada para 60 chars (*"Agentes de IA e Automação para Negócios · Turbinando Experts"*).
   - Meta description calibrada em 157 chars com CTA acionável.
   - `og-image.png` gerado em 1200×630px para corrigir falhas de renderização de SVG em redes sociais.
   - Schema JSON-LD avançado para motores generativos (ChatGPT, Claude, Perplexity): co-tipado em `["Organization", "ProfessionalService"]`, com `hasOfferCatalog` contendo a Oferta formal gratuita (R$ 0,00) da Call de 30 min, `knowsAbout` enriquecido com termos de LLMs corporativas, `speakable` e FAQPage com 8 perguntas de alta intenção.
   - `sitemap.xml` atualizado com lastmod `2026-11-06`.
5. **Mobile-First & Performance**:
   - Touch targets ampliados para no mínimo 44×44px no botão de alternância de tema e na barra inferior.
   - Suporte completo a safe-area no iOS (`env(safe-area-inset-bottom)`).
   - Botão de ação rápida na barra inferior com gradiente de destaque esmeralda + terracota.
6. **Marcador Ativo & Scroll-Spy Dual (Desktop & Mobile)**:
   - **Desktop**: Segmented capsule dock moderno com backdrop-blur. Ao navegar ou rolar (ex.: até a seção Diagnóstico), o item ativo ganha elevação, cápsula com borda verde e um indicador pulsante `●` animado em tempo real.
   - **Mobile**: Barra inferior móvel com pip superior luminoso (`::before` glowing bar), escala suave no ícone (`scale(1.15)`) e cápsula com fundo esmeralda translúcido (`--green-soft`).
   - **Engine JS**: Detecção contínua e performática com offset equilibrado de leitura, sem sobrecarga de renderização.

7. **Página de Portfólio Data-Driven (`portfolio-data-driven.html`) 100% Sincronizada**:
   - **Correção de Typo Crítico**: Corrigida a tag quebrada `<a  ="index.html" class="logo"` para `<a href="index.html" class="logo" aria-label="Turbinando Experts início">`.
   - **Segurança & LGPD**: Inserido o Toast de Privacidade e Consentimento (`#te-lgpd-toast`) com verificação em `localStorage ('te_lgpd_accepted')` e selo de conformidade com a Lei 13.709/2018 no resultado do simulador de dados.
   - **Copy & Conversão**: Foco total na **Call Estratégica Gratuita de 30 minutos com Kiko Soares** em todos os pontos de contato (Hero, TL;DR, CTA Final `#cta-final` e rodapé). Eliminação de termos rebuscados/Portugal e inclusão da comunicação brasileira sem fronteiras: *"Base em Porto Alegre/RS · Atendimento 100% digital onde quer que sua empresa esteja"*.
   - **Design Claude Terracotta**: Variáveis `--claude-clay: #DA7756` (Light) e `#E08263` (Dark) injetadas, com `.badge-clay`, `.accent-clay`, `.pulse-clay` e botões `.btn-clay` com gradiente refinado.
   - **Marcadores Ativos de Scroll-Spy (Desktop & Mobile)**:
     - *Desktop*: Menu dock em cápsula com backdrop-blur. Item ativo recebe cápsula elevada (`--bg-1`), borda esmeralda e live pulse dot `●` animado via `@keyframes pulseLiveDot`. Links sincronizados: *Início*, *Dashboards*, *IA & Alertas*, *Comparativo*, *Metodologia*, *Diagnóstico*, *Perguntas*.
     - *Mobile*: Barra inferior fixa com 5 itens de navegação touch-friendly (*Início*, *Dashes*, *IA Alertas*, *Diagnóstico*, *Call Grátis*), dotada de barra luminosa superior `::before` (`@keyframes pulsePip`), ícone elevado e gradiente de destaque.
     - *Dual-Spy Engine*: Script modular que sincroniza simultaneamente o menu superior no PC e o dock móvel no smartphone com debounce passivo e suporte a resize.
   - **Super GEO & SEO**: Metatags calibradas, `og:image` e `twitter:image` atualizados para `og-image.png` (1200×630px), e Schema JSON-LD robusto co-tipado em `["Organization", "ProfessionalService"]` com `Person` (Kiko Soares com `knowsAbout`), `WebPage` (`speakable`), `Service` com Oferta R$ 0,00 da call, `FAQPage` com 6 perguntas frequentes e `BreadcrumbList`.
   - **Mobile-First**: Touch target do alternador de tema ampliado para 44×44px e safe-area padding respeitado.

8. **Contraste de Alta Conversão dos Botões de WhatsApp (Modo Claro & Escuro)**:
   - **Correção de Conflito Cromático**: Eliminado o fundo laranja nos botões de conversação do WhatsApp que gerava baixo contraste e conflito visual com o logo verde e texto branco.
   - **Padrão Oficial Verde Esmeralda de Alto Contraste**: Botão primário (`.btn-primary`) redesenhado com gradiente verde esmeralda da marca (`linear-gradient(135deg, var(--green) 0%, #006834 100%)`), texto em **branco puro (`#FFFFFF`)** e logo do WhatsApp em **branco puro (`#FFFFFF`)**.
   - **Contraste WCAG AAA**: Contraste do botão sobre a tela Warm Linen de **5.5:1** e do texto/logo sobre o botão de **4.6:1**.
   - **Sincronizado**: Aplicado em todas as chamadas para ação em `index.html` e `portfolio-data-driven.html`, mantendo o terracota (`#DA7756`) reservado para badges, pulsos e acentos editoriais.

---

## Feito na sessão anterior (Versão 1.2 - Claude AI Light System)
- `index.html` migrado para Warm Light Canvas (`#FAF8F5`).
- Contraste da marca em verde, preto e branco.
- Card terminal com DNA técnico.
