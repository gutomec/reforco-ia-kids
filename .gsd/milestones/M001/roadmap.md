# M001: Reforço IA Kids — MVP

**Vision:** Plataforma funcional onde uma criança pode se cadastrar, selecionar ano/matéria/tema, receber uma aula interativa com IA + imagens geradas, fazer quiz com resolução passo a passo, acumular XP — e o pai pode acompanhar tudo via dashboard. Landing page com funil de conversão e checkout.

**Success Criteria:**
- Criança completa aula interativa do início ao fim
- Imagens são geradas durante a aula (Nano Banana)
- Quiz funciona com resolução passo a passo
- XP e níveis são calculados e exibidos
- Pai vê dashboard com estatísticas reais
- Landing page converte visitantes em cadastros
- Checkout processa pagamento (Stripe/Asaas)
- PWA funciona em mobile

## Slices

- [ ] **S01: Foundation** `risk:low` `depends:[]`
  > After: Next.js 15 configurado com Supabase, auth (pai cria conta + perfil filho), schema do banco, layout base responsivo, design tokens definidos

- [ ] **S02: Curriculum Engine** `risk:medium` `depends:[S01]`
  > After: API que retorna estrutura BNCC (anos → matérias → temas), tela de seleção funcional (ano → matéria → tema), dados de currículo seed no banco

- [ ] **S03: AI Lesson Core** `risk:high` `depends:[S02]`
  > After: Criança seleciona tema e recebe aula interativa via streaming do Claude API. IA ensina conversacionalmente com linguagem adequada à idade. Geração de imagens via Nano Banana integrada. Componentes A2UI renderizam conteúdo visual (cards, diagramas, destaque de conceitos)

- [ ] **S04: Quiz System** `risk:medium` `depends:[S03]`
  > After: Quiz gerado pela IA ao final de cada aula (múltipla escolha, V/F, preencher lacuna). Resolução passo a passo de cada questão. Cálculo de acertos. Armazenamento de resultados no banco

- [ ] **S05: Gamification + Stats** `risk:low` `depends:[S04]`
  > After: Sistema de XP (por aula completada, quiz acertado). Níveis (Explorador→Descobridor→Mestre→Gênio). Conquistas desbloqueáveis. Streaks diários. Dashboard do pai com gráficos de evolução por matéria/tema, tempo investido, acertos/erros

- [ ] **S06: Landing + Checkout** `risk:medium` `depends:[S01]`
  > After: Landing page de lançamento com hero, social proof, features, pricing, depoimentos, FAQ. Funil: lead magnet (diagnóstico grátis) → trial 7 dias → conversão. Checkout com Stripe (cartão) + Asaas (Pix/Boleto). Planos Gratuito/Essencial/Família implementados com feature flags

- [ ] **S07: Polish + PWA** `risk:low` `depends:[S03,S04,S05,S06]`
  > After: PWA manifest + service worker. Responsividade perfeita em mobile. Loading states, error boundaries, empty states. Onboarding flow para primeira aula. Meta tags para SEO. Analytics (PostHog) integrado

## Boundary Map

### S01 → S02
**S01 Produces:**
- `src/lib/supabase.ts` → createClient(), auth helpers
- `src/types/database.ts` → Database type definitions
- Schema SQL com tabelas: profiles, children, lessons, quiz_results
- Layout responsivo com sidebar/mobile nav

**S02 Consumes:**
- Supabase client de S01
- Database types de S01
- Layout base de S01

### S02 → S03
**S02 Produces:**
- `src/lib/curriculum.ts` → getCurriculum(), getTopics()
- API route `/api/curriculum/[year]/[subject]`
- Tabela curriculum_topics com seed data BNCC

**S03 Consumes:**
- Dados de currículo de S02 para montar o prompt da aula
- Supabase client de S01

### S03 → S04
**S03 Produces:**
- `src/lib/ai-lesson.ts` → streamLesson(), generateImage()
- `src/components/lesson/` → LessonChat, LessonImage, ConceptCard
- Modelo de dados: lessons (id, child_id, topic_id, messages, status)

**S04 Consumes:**
- Contexto da aula de S03 para gerar quiz relevante
- Componentes de UI de S03

### S04 → S05
**S04 Produces:**
- `src/lib/quiz.ts` → generateQuiz(), evaluateAnswer(), getStepByStep()
- Tabela quiz_results (lesson_id, questions, answers, score)

**S05 Consumes:**
- Dados de quiz_results para calcular XP e estatísticas
- Dados de lessons para histórico

### S06 (independente de S02-S05)
**S06 Produces:**
- Landing page em `/`
- Checkout flow em `/checkout`
- Stripe/Asaas integration em `src/lib/billing.ts`
- Feature flags em `src/lib/plans.ts`

**S07 Consumes:**
- Tudo de S01-S06 para polimento final
