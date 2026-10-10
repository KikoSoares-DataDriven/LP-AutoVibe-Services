# ⚡ Turbinando Experts — Landing Page

> **Estrutura digital, automações e IA para negócios sob medida.**  
> Sites, Landing Pages, WebApps, WhatsApp com IA, CRM e Dashboards — comece com a Linha START e evolua módulo por módulo.

[![Deploy](https://img.shields.io/badge/Cloudflare%20Pages-Live-F38020?logo=cloudflarepages&logoColor=white)](https://turbinandoexperts.com/)
[![HTML](https://img.shields.io/badge/HTML5-Single%20Page-E34F26?logo=html5&logoColor=white)](#)
[![Theme](https://img.shields.io/badge/Theme-Light%20%28Default%29%20%7C%20Dark-008744)](#-design--estética)
[![License](https://img.shields.io/badge/License-Proprietary-333)](#licença)

🔗 **Live:** [turbinandoexperts.com](https://turbinandoexperts.com/)

---

## 📋 Sobre o Projeto

Landing page de alta conversão para a marca **Turbinando Experts** (Kiko Soares — Porto Alegre/RS e atendimento remoto para todo o Brasil).

O objetivo é captar leads qualificados via **WhatsApp** para uma call de imersão gratuita de 30 minutos com o especialista, mapeando gargalos operacionais e apresentando a arquitetura modular sob medida ideal para a fase atual da empresa.

### Arquitetura Modular (START → FLOW → CONTROL → SCALE)

| Camada | Módulos Principais | Objetivo & Entrega |
| :--- | :--- | :--- |
| 🚀 **START** | Site Profissional, Landing Page, Google GMN, WebApp Inicial | Resolver a dor imediata sem necessidade de pacotes engessados |
| ⚡ **FLOW** | Agente de IA no WhatsApp 24/7, Automação n8n, Triagem | Eliminar tarefas repetitivas e acelerar respostas a leads |
| 📊 **CONTROL** | CRM Personalizado, Dashboards em Tempo Real (KPIs) | Centralizar dados e oferecer visibilidade total das vendas |
| 🏢 **SCALE** | WebApps e Sistemas Internos Customizados | Substituir planilhas ou softwares genéricos que limitam a operação |
| 🛡️ **CARE / GROWTH** | Suporte contínuo, estabilidade técnica e novos módulos | Evolução sustentável do ativo digital sem mensalidades forçadas |

---

## 🎨 Design & Estética

- **Tema Padrão:** **Light Theme** (paleta editorial aquecida no estilo Claude AI: base `#FAF8F5`, cards brancos e tipografia de alto contraste em preto obsidian `#111814`).
- **Tema Alternativo:** **Dark Mode** (estilo terminal tech com verde neon `#00E676` sobre `#050807`), alternável com persistência via `localStorage`.
- **Toggle de Tema:** Botão minimalista compacto no header exibindo somente os ícones (lua / sol) e script anti-flash no `<head>`.
- **Cores Preponderantes:** Verde Esmeralda (`#008744`), Preto Obsidian (`#111814`) e Branco puro (`#FFFFFF`).
- **Tipografia:**
  - Display / Títulos: [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk)
  - Textos & Leitura: [Manrope](https://fonts.google.com/specimen/Manrope)
  - Código & Detalhes técnicos: [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
- **Componentes Interativos:** Quiz de diagnóstico guiado em 8 passos, Bottom Nav mobile com scroll-spy, carrossel contínuo (marquee) e terminal de esteira.

---

## 🏗️ Estrutura da Landing Page

1. **Top banner:** Âncora geográfica (Porto Alegre/RS + atendimento nacional)
2. **Header sticky:** Logo, navegação rápida, alternador de tema (apenas ícone) e CTA WhatsApp
3. **Hero Section:** Proposta central, TL;DR executivo e Terminal Mockup interativo da esteira
4. **Marquee:** 10 segmentos de mercado atendidos (loop contínuo)
5. **Empathy Box:** Princípio fundamental ("Você sabe onde dói. Nós encontramos o que precisa ser construído")
6. **Dores Reais:** Grade com 10 gargalos frequentes de pequenas e médias empresas
7. **Soluções Modulares:** 4 pilares (Presença Digital, Automação & IA, Gestão & Dados, Sistemas & WebApps)
8. **Linha START:** 7 pontos de entrada práticos para contratação inicial rápida
9. **Jornada de Evolução:** Linha do tempo START → FLOW → CONTROL → SCALE + CARE/GROWTH
10. **Tabela Comparativa:** Ferramentas genéricas engessadas vs. Solução sob medida
11. **Diagnóstico Interativo:** Quiz inteligente de 8 passos gerando briefing automático para o WhatsApp
12. **Resultados & Prova Social:** Métricas de agilidade e cenários práticos por setor
13. **Sobre:** Bio de Kiko Soares, posicionamento Vibe Coding e stack de especialidades
14. **FAQ:** 8 dúvidas essenciais respondidas com transparência
15. **CTA Final:** Bloco de fechamento de alto contraste convidando para a call de 30 min
16. **Footer + Bottom Nav Mobile:** Links legais, metadados locais e navegação com scroll-spy

---

## 📁 Estrutura de Arquivos

```text
├── index.html                  # LP completa responsiva e modular (Self-contained)
├── termos-de-uso.html          # Termos de uso conforme legislação brasileira
├── politica-de-privacidade.html# Política de privacidade alinhada à LGPD
├── favicon.svg                 # Favicon vetorial
├── apple-touch-icon.svg        # Ícone para dispositivos Apple / PWA
├── og-image.svg                # Imagem Open Graph para compartilhamento social
├── manifest.json               # Configuração Web App Manifest (PWA)
├── robots.txt                  # Diretivas de indexação para buscadores e AI crawlers
├── sitemap.xml                 # Mapa do site indexado
├── _headers                    # Regras de segurança (CSP, HSTS) e cache no Cloudflare Pages
└── README.md                   # Documentação do projeto
```

---

## 🚀 Como Rodar Localmente

O projeto é construído em HTML5, CSS3 e JavaScript puros — **sem dependências externas de build**:

```bash
# Opção 1 — Abrir direto no navegador
start index.html          # Windows
open index.html           # macOS

# Opção 2 — Executar via servidor local
npx serve .
# ou
python -m http.server 8000
```

---

## ☁️ Deploy (Cloudflare Pages)

O deploy contínuo está configurado via **Cloudflare Pages**:

1. Conecte o repositório GitHub no painel do Cloudflare Pages.
2. **Build command:** *(vazio)*
3. **Build output directory:** `/`
4. As regras de cache, compressão e headers de segurança são aplicadas pelo arquivo `_headers`.

---

## 📊 SEO, GEO & Acessibilidade

- **SEO & Schema.org:** Implementação de 7 esquemas JSON-LD (`Organization`, `LocalBusiness`, `Person`, `Service`, `FAQPage`, `BreadcrumbList`, `WebSite`).
- **GEO (Generative Engine Optimization):** Meta tags geográficas de Porto Alegre/RS, blocos TL;DR para inteligências artificiais e respostas estruturadas para busca generativa.
- **Acessibilidade (WCAG):** Contraste calibrado em ambos os temas, navegação por teclado (`:focus-visible`), skip-link e atributos semânticos `aria-label`.
- **Tema Claro por Padrão:** Carregamento inicial em tema claro sem flashes visuais (FOUC), com opção de alternar para modo escuro salva no navegador.

---

## 👤 Autor

**Kiko Soares** — Estrutura Digital e Sistemas Sob Medida com IA
- 📍 Porto Alegre/RS · Brasil (Atendimento remoto nacional)
- 💬 [WhatsApp Oficial](https://wa.me/5551920000513?text=Quero%20a%20an%C3%A1lise%20gratuita%20do%20meu%20neg%C3%B3cio)
- 🐙 [GitHub](https://github.com/KikoSoares-DataDriven)

---

## 📄 Licença

Projeto proprietário. Todos os direitos reservados © 2026 Turbinando Experts.
