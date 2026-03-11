# Decisions

| # | When | Scope | Decision | Choice | Rationale | Revisable? |
|---|------|-------|----------|--------|-----------|-----------|
| D001 | M001/S01 | stack | Frontend framework | Next.js 15 + React 19 | SSR para SEO da landing, App Router, Server Components | No |
| D002 | M001/S01 | stack | Database | Supabase (PostgreSQL) | Auth integrado, Realtime, Row Level Security, free tier generoso | No |
| D003 | M001/S01 | stack | LLM provider | Claude API (Anthropic) | Melhor qualidade para educação, bom com crianças, streaming | Yes |
| D004 | M001/S01 | stack | Geração de imagens | Nano Banana (MCP) | Integrado ao ecossistema, API simples, qualidade suficiente | Yes |
| D005 | M001/S01 | stack | UI interativa | A2UI Protocol | Componentes ricos sem framework extra, integração com LLM | No |
| D006 | M001/S01 | stack | Pagamento Brasil | Asaas (Pix/Boleto) + Stripe (cartão) | Asaas tem Pix nativo, Stripe para cartão internacional | No |
| D007 | M001/S01 | arch | Auth strategy | Supabase Auth (email + Google) | Simples, consentimento parental via email do pai | No |
| D008 | M001/S01 | business | Pricing model | Freemium 3 tiers | Gratuito para aquisição, Essencial R$29,90, Família R$49,90 | Yes |
| D009 | M001/S01 | business | Offer model | Grand Slam Offer (Hormozi) | Valor percebido R$1.130/mês, preço real R$49,90, garantia 30 dias | No |
| D010 | M001/S01 | business | Launch strategy | Fórmula de Lançamento (Rocha) | CPL 3 vídeos + lista de espera + abertura 4 dias | No |
| D011 | M001/S01 | product | Currículo base | BNCC (Base Nacional Comum Curricular) | Padrão brasileiro obrigatório, organização por ano/matéria/tema | No |
| D012 | M001/S01 | product | Idade mínima | 6 anos (1º ano) com conta do pai | LGPD exige consentimento parental para menores de 18 | No |
| D013 | M001/S01 | design | Abordagem mobile | PWA (Progressive Web App) | Mais rápido que app nativo, sem App Store review, funciona em qualquer device | Yes |
| D014 | M001/S01 | product | Gamificação | XP + Níveis + Conquistas + Streaks | Engajamento comprovado em EdTech (Duolingo model) | No |
| D015 | M001/S01 | arch | Deploy | Vercel | Integração nativa Next.js, edge functions, preview deploys | No |
