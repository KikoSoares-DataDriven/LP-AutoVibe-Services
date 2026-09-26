# AUDIT — LP Turbinando Experts · 2026-09-21

Baseline: build n/a (HTML estático) · lint n/a · testes inexistentes (projeto sem suite — aceitável para LP single-file) · JSON-LD: válido após edições ✅

| Sev | Achado | Onde | Ação sugerida | Status |
|---|---|---|---|---|
| Crítico | `index.html` havia sido deletado e a LP nova estava como `TurbinandoExperts.html` → raiz do site ficaria sem página no Cloudflare Pages | git status | Renomear para `index.html` | ✅ Resolvido nesta sessão |
| Médio | Marca só cobria "Turbinando Experts"; query "turbinando expert" (singular) sem suporte | metas/schema | `alternateName` + menção no rodapé | ✅ Resolvido |
| Médio | Sem correspondência para "automações e ia poa rs" / "automações e ia para negócios" | title/description/schema/hero | Reescrita de metas + LocalBusiness com areaServed | ✅ Resolvido |
| Leve | `sitemap.xml` lastmod desatualizado (04/jun) | sitemap.xml | Atualizado para 2026-09-21 | ✅ Resolvido |
| Leve | `og-image.svg` é SVG (OG idealmente PNG/JPG para preview garantido) | og-image.svg | Gerar PNG 1200×630 quando possível | Pendente |
| Leve | Depoimentos marcados "caso ilustrativo" | index.html (seção depoimentos) | Trocar por reais quando houver | Pendente |
| Leve | 2 PDFs de cartão não commitados; sem rastreamento de analytics | raiz | Decidir se versionam + GSC/analytics | Pendente |

Não verificado: comportamento visual pós-edição no browser (edições foram textuais em metas/schema/rodapé, sem tocar CSS/layout); métricas reais de ranking (exigem GSC pós-deploy).
