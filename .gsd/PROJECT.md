# Reforço IA Kids

## Vision
Democratizar o reforço escolar no Brasil com IA — oferecendo a cada criança do ensino fundamental (1º-9º ano) um professor particular infinitamente paciente, disponível 24/7, que se adapta ao ritmo de aprendizagem, gera imagens para ilustrar conceitos e custa menos que 1 hora de professor particular por mês inteiro.

## What We're Building
Uma plataforma web (Next.js) de aulas de reforço escolar 100% com IA onde crianças:
1. Selecionam ano escolar, matéria e tema
2. Recebem aula interativa personalizada com imagens geradas (Nano Banana)
3. Respondem quizzes com resolução passo a passo
4. Acumulam XP e conquistas (gamificação)
5. Têm todo o histórico e estatísticas de aprendizagem rastreados

Pais acompanham tudo via dashboard com relatórios semanais.

## Core Value Proposition
"Professor particular de IA disponível 24/7 — todas as matérias, do 1º ao 9º ano — por R$49,90/mês para a família inteira. Menos que 1 hora de professor particular."

## Target Audience
- **Primário:** Pais de crianças de 6-14 anos, classes B/C, que não podem pagar professor particular regularmente
- **Secundário:** Escolas que buscam ferramenta complementar de reforço
- **Terciário:** Pais classe A que querem complemento tecnológico

## Business Model
- Freemium com 3 tiers: Gratuito (3 aulas/semana), Essencial (R$29,90/mês), Família (R$49,90/mês)
- Tier Escola sob consulta (licenças por turma)

## Tech Stack
| Componente | Tecnologia |
|-----------|-----------|
| Frontend | Next.js 15 + React 19 + TypeScript |
| UI Interativa | A2UI Protocol (components visuais) |
| Geração de Imagens | Nano Banana (MCP) |
| LLM | Claude API (Anthropic SDK) |
| Backend API | Next.js API Routes + Hono |
| Database | Supabase (PostgreSQL + Realtime) |
| Auth | Supabase Auth (email + Google) |
| Pagamento | Stripe (internacional) + Asaas (Pix/Boleto Brasil) |
| Deploy | Vercel |
| Analytics | PostHog |
| Email | Resend |
| WhatsApp | Evolution API ou Z-API |

## Success Criteria (MVP - M001)
- [ ] Criança consegue se cadastrar e fazer login
- [ ] Criança seleciona ano/matéria/tema e recebe aula interativa
- [ ] IA gera imagens relevantes durante a aula (Nano Banana)
- [ ] Quiz ao final de cada aula com resolução passo a passo
- [ ] Sistema de XP e níveis básico
- [ ] Dashboard do pai com estatísticas por matéria/tema
- [ ] Plano gratuito funcional (3 aulas/semana)
- [ ] Checkout com Stripe/Asaas para planos pagos
- [ ] Landing page de lançamento com funil de conversão

## Non-Goals (MVP)
- App nativo (iOS/Android) — PWA é suficiente inicialmente
- Modo Dever de Casa (câmera + OCR) — M002
- Modo Prova (simulados cronometrados) — M002
- Trilhas de aprendizado com pré-requisitos — M002
- Painel do professor (tier Escola) — M003
- Relatório WhatsApp automático — M002
- Rankings entre amigos — M002

## Risks
| Risco | Impacto | Mitigação |
|-------|---------|-----------|
| Custo de API Claude alto por aula | Alto | Cache de respostas comuns, streaming, modelos menores para interações simples |
| LGPD/ECA para menores de idade | Alto | Consentimento parental obrigatório, dados mínimos, sem ads |
| IA dando resposta errada | Médio | Guardrails, conteúdo validado por currículo BNCC, feedback loop |
| Baixa retenção de crianças | Médio | Gamificação forte, personagens, streaks, conquistas |
| Pais não veem valor | Médio | Dashboard claro, relatório semanal, comparação com professor particular |

## Squad Origins
- **Sales Funnel Masters:** Estratégia de pricing (Van Westendorp), offer stack (Grand Slam Offer), funil de lançamento (Fórmula de Lançamento), copy
- **BrandCraft:** Design system, identidade visual, materiais de marca
- **adaptive-tutor-k12:** Domínio educacional, currículo BNCC, pedagogia adaptativa
