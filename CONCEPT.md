# Reforço IA Kids — Conceito do Produto

## Visão

Sistema de aulas de reforço escolar 100% feito com IA, onde crianças do ensino fundamental (1º ao 9º ano) aprendem de forma interativa, visual e personalizada — como ter um professor particular infinitamente paciente, disponível 24/7, que se adapta ao ritmo de cada criança.

## Público-Alvo

- **Primário:** Pais de crianças de 6-14 anos (ensino fundamental), classes B/C/D
- **Secundário:** Escolas que buscam ferramenta complementar
- **Terciário:** Professores particulares que querem escalar

## Problema

1. **Custo:** Professor particular custa R$50-150/hora — inacessível para maioria
2. **Disponibilidade:** Horários limitados, dependência geográfica
3. **Qualidade inconsistente:** Difícil encontrar bom professor para cada matéria
4. **Vergonha:** Criança tem medo de perguntar na escola
5. **Acompanhamento:** Pais não conseguem acompanhar evolução

## Solução

### Fluxo Principal

```
Criança abre app
  → Seleciona ano escolar (1º ao 9º ano)
  → Seleciona matéria (Matemática, Português, Ciências, História, Geografia, Inglês)
  → Seleciona tema (ex: Frações, Verbos, Sistema Solar)
  → IA inicia aula interativa personalizada
```

### Features Core

#### 1. Aulas Interativas com IA
- IA ensina o tema conversacionalmente, como um professor
- Explica conceitos com linguagem adequada à idade
- Faz perguntas durante a aula para verificar compreensão
- Se adapta: se errou, explica de outro jeito

#### 2. Geração de Imagens (Nano Banana)
- Ilustrações geradas em tempo real para cada conceito
- "Imagine 3 pizzas divididas em 4 pedaços cada..."
- Diagramas, mapas mentais, esquemas visuais
- Personagens recorrentes que acompanham a criança

#### 3. Componentes Visuais Interativos (A2UI)
- Formulários para quizzes com opções clicáveis
- Barras de progresso da aula
- Cards com conceitos-chave
- Timeline de aprendizado
- Gráficos de desempenho

#### 4. Sistema de Testes e Quizzes
- Testes ao final de cada tema
- Questões de múltipla escolha, verdadeiro/falso, preencher lacuna
- Resolução passo a passo de cada questão
- Explicação do porquê cada alternativa está certa ou errada

#### 5. Histórico e Estatísticas
- Dashboard para pais acompanharem evolução
- Estatísticas por matéria, tema, acertos/erros
- Tempo investido por sessão
- Temas que precisam de reforço
- Relatório semanal enviado por email/WhatsApp

#### 6. Gamificação
- XP por aula completada, quiz acertado
- Níveis (Explorador, Descobridor, Mestre, Gênio)
- Conquistas desbloqueáveis
- Sequência diária (streaks)
- Rankings opcionais entre amigos

### Features Diferenciais

#### 7. Modo "Me Explica de Outro Jeito"
- Criança pode pedir explicação alternativa a qualquer momento
- IA usa analogias do universo da criança (jogos, desenhos, esportes)

#### 8. Modo Dever de Casa
- Criança fotografa exercício da escola
- IA guia a resolução passo a passo (NÃO dá resposta pronta)
- Ensina o método, não a resposta

#### 9. Aula para Prova
- Criança informa "tenho prova de X na Y"
- IA monta plano de estudo focado
- Simulados com timer
- Revisão dos pontos fracos

#### 10. Trilhas de Aprendizado
- Sequências estruturadas de temas
- Pré-requisitos automáticos (precisa saber X antes de Y)
- Sugestões personalizadas baseadas no desempenho

## Stack Técnica (Planejada)

| Componente | Tecnologia |
|-----------|-----------|
| Frontend | Next.js 15 + React 19 |
| UI Components | A2UI Protocol |
| Geração de Imagens | Nano Banana (MCP) |
| LLM | Claude API (Anthropic) |
| Backend | Node.js + Hono |
| Database | Supabase (PostgreSQL) |
| Auth | Supabase Auth |
| Pagamento | Stripe / Asaas (Brasil) |
| Deploy | Vercel |
| Analytics | PostHog |

## Modelo de Negócio

### Pricing (a definir com Van Westendorp)

| Plano | Preço | Inclui |
|-------|-------|--------|
| **Gratuito** | R$0 | 3 aulas/semana, 1 matéria, sem histórico |
| **Essencial** | R$29,90/mês | Ilimitado, 3 matérias, histórico básico |
| **Família** | R$49,90/mês | Ilimitado, todas matérias, até 3 filhos, dashboard pais |
| **Escola** | Sob consulta | Licenças por turma, painel do professor |

### Métricas-Chave

- **Ativação:** Criança completa 1ª aula
- **Retenção:** Volta na 2ª semana
- **Conversão:** Free → Essencial
- **Engajamento:** Aulas/semana por usuário ativo
