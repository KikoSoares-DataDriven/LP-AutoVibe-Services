# STATE — LP Turbinando Experts

**Fase:** v2.3 Implementada (Refinamento Mobile Cirúrgico: Botões de WhatsApp Compactos e Elegantes, Alinhamento Perfeito do Card de Perfil Kiko Soares, Envelopamento e Proteção Total dos Limites Direitos dos Cards e Sub-abas Responsivas de Vendas) · 07/nov/2026 · baseline: sem build/test (HTML estático), JSON-LD válido, 100% de testes automatizados aprovados no Playwright ✅

## Estado atual
- `index.html` = Versão 2.3 com botões de ação e WhatsApp redimensionados para altura ergonômica de 44px–63px (eliminando botões gigantes de 114px–138px), alinhamento harmonioso no card de perfil (`#sobre`), proteção do limite direito em todos os cards e badge de rolagem sutil no comparativo.
- `portfolio-data-driven.html` = Versão 2.3 sincronizada com botões compactos, galeria de abas do dashboard de vendas em grade 2x2 sem transbordamento lateral e card de perfil alinhado.
- Deploy: push no `main` → Cloudflare Pages.

## Feito nesta sessão (Versão 2.3 - Refinamentos Visuais Mobile: Botões, Perfil e Limites dos Cards)
1. **Redução e Harmonização dos Botões de WhatsApp e CTAs no Mobile:**
   - **Problema:** Botões como `.btn-large` e `.btn-primary` herdavam paddings e tipografias de desktop (`20px 32px`, `font-size: 15px`), estourando em alturas gigantescas de 90px até 138px em telas móveis.
   - **Solução:** Aplicada calibração em `@media (max-width: 767px)` com `padding: 12px 18px !important; font-size: 12.5px !important; min-height: 44px !important; max-width: 320px !important;` e `.btn-large` com `padding: 13px 20px !important; font-size: 13px !important;` reduzindo a altura máxima para 63px (mais de 50% de redução), elegante, perfeitamente tocável e sem dominar a tela.
   - Botões secundários e botões de dashboard compactados para 38px–44px.

2. **Alinhamento do Card de Perfil Kiko Soares (`#sobre`):**
   - **Problema:** O card de perfil no desktop não possuía alinhamento vertical (`align-items: center;`), deixando a foto e o texto com alturas desencontradas. No mobile, a foto de 160px era desproporcional e os stats ficavam com margens assimétricas.
   - **Solução:**
     - Adicionado `align-items: center;` no desktop e tablet.
     - No mobile: foto redimensionada para 128px perfeitamente centralizada, bloco de estatísticas reorganizado em grade simétrica de 3 colunas (`grid-template-columns: repeat(3, 1fr); gap: 8px; max-width: 300px; margin: 6px auto;`) e pills de tecnologia centralizadas.

3. **Correção dos Textos e Limites Direitos dos Cards:**
   - **Problema:** Textos e tags internas (como `.result-tag` com "DISPONIBILIDADE CONTÍNUA" e listas com checkmarks) sofriam compressão ou tocavam a borda direita nos cards em telas estreitas (360px–375px). No portfólio, os botões `.vendas-tab-btn` vazavam 164px para fora do card.
   - **Solução:**
     - Universal guard em `.pain-card-v11, .pillar-card, .start-card, .strategy-card, .flow-card, .empathy-card, .depo-card, .result-card, .about-card, .dash-card` com `box-sizing: border-box !important; max-width: 100% !important; min-width: 0 !important; overflow-wrap: break-word !important; word-break: break-word !important;`.
     - `.pillar-card`: padding otimizado para 22px 16px, lista com `align-items: flex-start` para alinhar checkmark ao topo da primeira linha.
     - `.result-card`: padding 16px 12px e `.result-tag` com quebra natural sem corte.
     - `.compare-table-wrap`: adicionado badge sutil `table-scroll-hint` ("⇄ Deslize para ver o comparativo completo").
     - `portfolio-data-driven.html`: `.vendas-tabs` refatorado com `flex-wrap: wrap` e botões em 2x2 (`flex: 1 1 calc(50% - 6px)`), eliminando 100% do transbordamento lateral.

4. **Testes Automatizados & Validação:**
   - 100% aprovado no Playwright: 0 vazamentos em cards, 0 overflows no viewport em 320px, 360px, 375px e desktop.
1. **Cards que Sumiam e Deixavam Espaço Vazio no Mobile (Resolvido Definitivamente):**
   - **Causa Raiz:** O seletor `.fade-up` iniciava com `opacity: 0; transform: translateY(...)`. Em navegadores mobile (WebKit/Blink touch), o `IntersectionObserver` com margem negativa falhava ou atrasava, mantendo os cards ocupando sua altura física completa no DOM, porém invisíveis (`opacity: 0`), criando um vazio enorme de milhares de pixels.
   - **Correção:** Em `@media (max-width: 767px)`, forçado `.fade-up { opacity: 1 !important; transform: none !important; transition: none !important; visibility: visible !important; }`.
   - No JavaScript: Adicionada verificação imediata na inicialização (`if (window.innerWidth < 768) fadeElements.forEach(el => el.classList.add('in'))`).
   - Resultado: 100% dos cards (`.pain-card-v11`, `.pillar-card`, `.start-card`, `.depo-card`, `.dash-card`, `.ai-card`, etc.) renderizados com nitidez imediata no mobile.

2. **Botão de Alternar Modo Claro/Escuro no Topo Mobile (Resolvido Definitivamente):**
   - **Causa Raiz:** No mobile, o toque dispara eventos `touchend` seguidos de evento emulado de `click` (~300ms depois). Sem debounce, o tema alternava e voltava imediatamente para o estado anterior, parecendo congelado no modo claro. Além disso, acessos a `localStorage` sem `try/catch` podiam falhar em modo de navegação anônima ou WebViews.
   - **Correção:**
     - Adicionado `type="button"` e dimensionamento ergonômico touch de 42×42px (`touch-action: manipulation; -webkit-tap-highlight-color: transparent;`).
     - No JS: implementado manipulador com debounce de 300ms entre eventos e prevenção de cliques duplicados.
     - Proteção completa com `try...catch` em todas as leituras e gravações de `localStorage`.
     - Estilo escuro enriquecido com destaque em verde neon (`--green-neon`), contraste nítido e atualização dinâmica de `aria-label`.

3. **Menu Inferior Não Mostrava Onde o Usuário Estava (Resolvido Definitivamente):**
   - **Causa Raiz:** O cálculo de interseção continha lacunas entre seções e a seção `#cta-final` não possuía ID no DOM do `index.html`. Além disso, a barra inferior de 2px era parcialmente obscurecida pela barra de gestos (home indicator) do iOS/Android.
   - **Correção:**
     - Adicionado `id="cta-final"` no HTML da seção final.
     - Implementado algoritmo de scroll-spy monotônico (`top <= scrollPos`), eliminando qualquer zona morta entre seções.
     - Mapeamento robusto de todas as seções para os 4 itens âncora do dock inferior móvel.
     - Indicador visual duplo: barra superior luminosa (`::before` em `top: 0; left: 12%; right: 12%; height: 3px;`), totalmente visível e imune à barra do sistema operacional móvel, além de fundo em cápsula (`rgba(0, 135, 68, 0.12)`), tipografia weight 800 e traço inferior pulsante (`::after`).
     - Adicionado feedback tátil instantâneo no toque dos itens móveis.

4. **Testes Automatizados & Validação:**
   - 100% de aprovação na suíte Playwright mobile (375px) cobrindo:
     - 0 cards invisíveis (todos com `opacity: 1` e altura real).
     - Alternância de tema entre light e dark.
     - Scroll-spy ativo correspondendo a cada seção percorrida.
     - Zero overflow horizontal.
1. **Eliminação Definitiva do Overflow Horizontal (Mobile Viewports 320px–480px)**:
   - `html` e `body` blindados com `overflow-x: hidden; overflow-x: clip; width: 100%; max-width: 100vw; box-sizing: border-box;`.
   - `.marquee-section`: aplicada proteção `overflow: hidden; overflow-x: clip; width: 100%; max-width: 100%; box-sizing: border-box;`, impedindo o rastro infinito de vazar o viewport.
   - `.hero::before` e `.cta-final::before`: reescalados no mobile para `max-width: 100%; right: -30px;` e dimensões proporcionais, eliminando o esticamento da viewport.
   - `.compare-table-wrap`: protegido com `width: 100%; max-width: 100%; box-sizing: border-box; overflow-x: auto; -webkit-overflow-scrolling: touch;`, com células compactadas e rolagem interna touch fluida sem alargar o corpo do documento.
   - Testado e validado em 320px, 360px, 375px, 390px e 412px: `scrollWidth === window.innerWidth` em 100% dos testes.

2. **Menu de Navegação Inferior (Rodapé Mobile) Totalmente Refatorado**:
   - Barra fixa `.bottom-nav` configurada com `w-full` (`width: 100%; max-width: 100%; left: 0; right: 0; margin: 0 auto; box-sizing: border-box;`).
   - Distribuição perfeitamente simétrica em CSS Grid: `grid-template-columns: repeat(5, minmax(0, 1fr));`, garantindo exatamente 20% de largura para cada item sem desvios ou compressão à esquerda.
   - Touch targets ergonômicos: `min-height: 48px; min-width: 44px; width: 100%;` (cumpre e supera o padrão WCAG de 44px).
   - Marcador Ativo Moderno:
     - Tipografia reforçada (`font-weight: 800; font-size: clamp(9.5px, 2.3vw, 10.5px)`).
     - Cor de acento da marca (`var(--green)` no light e `var(--green-neon)` no dark).
     - Traço/pill indicador embaixo: pseudo-elemento `::after` posicionado na base (`bottom: 2px; left: 18%; right: 18%; height: 3px; border-radius: 999px; background: var(--green);`).
     - Fundo em cápsula suave (`background: var(--green-soft);`).
   - Desktop preservado: `@media (min-width: 768px/860px) { .bottom-nav { display: none !important; } }`.

3. **Banner / Modal de LGPD 100% Funcional e Resiliente**:
   - Tratamento de `localStorage` seguro com bloco `try...catch`, impedindo que modos de navegação anônima ou restrições de terceiros travem a execução do script.
   - Disparo automático com timer após 600ms quando não aceito previamente, ou sob demanda via parâmetro de URL (`?lgpd=1` ou hash `#lgpd`).
   - Botão gatilho no rodapé legal de ambas as páginas: `<button type="button" class="btn-footer-privacy" id="btn-open-lgpd">Privacidade & Cookies (LGPD)</button>`, além de ouvintes para seletores `[data-open-lgpd]`, `a[href="#lgpd"]` e `a[href="#privacidade"]`.
   - Funções globais expostas: `window.openLgpdModal()` e `window.closeLgpdModal()`.
   - Camada visual com `z-index: 1000` (acima de z-50), posicionado acima do dock móvel com `bottom: calc(64px + env(safe-area-inset-bottom))`, sem obstruir a navegação nem vazar a largura do viewport.

4. **Preservação de Visualizações Desktop & Validação de Build**:
   - Menus desktop (`.site-header .nav`) mantidos íntegros com visualização flex, cápsulas segmentadas e scroll-spy sincronizado.
   - Suíte de testes automatizados com Playwright executada com 100% de aprovação (JSON-LD bem formado, zero erros no console, zero overflow horizontal em todas as larguras).
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

- **Fix de Timing do Toast LGPD**: Corrigido posicionamento do `<aside id="te-lgpd-toast">` em `index.html` (que estava após a tag `<script>` no DOM, causando `null` na busca pelo elemento) e encapsulado o controller em função resiliente com listener de `DOMContentLoaded` em ambas as páginas.

---

## Feito na sessão anterior (Versão 1.2 - Claude AI Light System)
- `index.html` migrado para Warm Light Canvas (`#FAF8F5`).
- Contraste da marca em verde, preto e branco.
- Card terminal com DNA técnico.
