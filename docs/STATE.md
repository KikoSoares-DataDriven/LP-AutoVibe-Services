# STATE — LP Turbinando Experts

**Fase:** v1.1 Implementada (Baseada em `docs/PRD-v1.1.md`) · 25/set/2026 · baseline: sem build/test (HTML estático), JSON-LD válido ✅

## Estado atual
- `index.html` = Versão 1.1 da LP ativa (arquitetura comercial e técnica de entrada e expansão).
- URL canônica: `https://turbinandoexperts.com/`. `robots.txt`, `sitemap.xml` (lastmod 2026-09-25), `_headers`, PWA ok.
- Spec: `docs/spec/v1.1-index.md` (concluída).
- Deploy: push no `main` → Cloudflare Pages.

## Feito nesta sessão (Versão 1.1 do index.html)
Baseado estritamente em `docs/PRD-v1.1.md`:
1. **Hero & Dobra 1**: Eyebrow `ESTRUTURA DIGITAL · AUTOMAÇÕES E IA PARA NEGÓCIOS · PORTO ALEGRE/RS`, H1 oficial, TL;DR, Subheadline com as soluções completas e CTAs de ação imediata + terminal visual com a esteira interativa.
2. **Empatia Tecnológica**: Seção "Você sabe onde dói. Nós encontramos o que precisa ser construído." (dor primeiro, tecnologia depois).
3. **Mapeamento de Gargalos**: Grade com as 10 dores reais do PRD v1.1 direcionando para os módulos de entrada ou diagnóstico.
4. **Soluções que podemos construir**: 4 pilares semânticos (Presença Digital, Automação e IA, Gestão e Dados, Sistemas e WebApps) com o lema "Produtos organizam. Os módulos são personalizados para cada negócio."
5. **Linha START Reestruturada**: 7 produtos de entrada (START Site, START Landing, START Google, START App, START Flow, START Data, START Diagnóstico). "Comece pelo que sua empresa precisa agora."
6. **Jornada de Evolução Visual**: Stepper interativo `DOR → START → RESULTADO → FLOW → CONTROL → SCALE → CARE + GROWTH` ("Comece pequeno. Evolua quando fizer sentido.")
7. **Pilares em Ação**: 3 fluxos visuais do FLOW, CRM + Dashboards no CONTROL, expansão no SCALE e continuidade no CARE/GROWTH.
8. **Comparativo Comercial**: Tabela Genérico vs. Sob Medida ajustada para "Sem depender de plataforma engessada / Sua solução, sua arquitetura".
9. **Diagnóstico Interativo (Quiz 8 passos)**: Motor 100% no cliente calculando recomendação (START, FLOW, CONTROL, SCALE) e montando mensagem completa para WhatsApp em 1 clique.
10. **Resultados & Cenários Reais**: Métricas (< 7d deploy, 24/7 atendimento, 100% sob medida, 0% travado) e casos ilustrativos por segmento.
11. **Sobre & Posicionamento**: Kiko Soares, bio de Vibe Coding e "Aqui, a solução começa pela sua operação — não por um template."
12. **FAQ Atualizado**: 8 perguntas essenciais cobrindo atendimento remoto, sites, automação, CRM, sistemas e suporte.
13. **CTA Final Institucional**: Frase oficial: "Uma solução para a dor de hoje. Uma arquitetura preparada para o amanhã. Comece pelo que sua empresa precisa agora. Evolua quando fizer sentido."
14. **SEO & Dados Estruturados**: Schema JSON-LD com 7 nós (Organization, LocalBusiness com área local/remota, Person, Service, FAQPage, BreadcrumbList, WebSite).
15. **Sitemap**: `sitemap.xml` atualizado com lastmod `2026-09-25`.
16. **Ajuste Visual de Avatar**: `perfil.png` ajustado com `object-position: center top` para evitar o corte da testa e centralizar perfeitamente o rosto dentro da moldura circular.

## Próximos passos (fora do escopo desta sessão)
1. Commitar e dar push (deploy Cloudflare Pages) — **depende de aprovação do usuário**.
2. Google Search Console: solicitar reindexação após o deploy.
3. Fases 2 e 3 do PRD: criação das páginas de aquisição específicas (`/automacao-ia-porto-alegre`, `/sites-landing-pages`, etc.).

## Notas
- Backup da versão anterior salvo em `index.html.bak`.
- `ESTADO.md` (raiz) é o changelog legado até v3.1; `docs/STATE.md` é a fonte canônica atualizada.

