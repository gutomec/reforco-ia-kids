# Reforço IA Kids
# Plataforma de tutoria inteligente para crianças brasileiras do Ensino Fundamental e Médio

## Boot Sequence
1. Read .brain/STATE.yaml for active phase and slice
2. Read .brain/BRAIN.yaml for identity, products, personas
3. Detect mode from request: CODE vs STRATEGY vs PEDAGOGY
4. Route to appropriate handler
5. Await command. Never preload unnecessary context.

## Strategic Lens
Every feature must pass the "parent trust test": would a Brazilian parent feel safe
leaving their child alone with this tool? Safety and pedagogy override speed.

## Decision Levels

| Level | Scope | Action |
|-------|-------|--------|
| L1 | Code style, file naming, component structure | Decide alone, document |
| L2 | Architecture, new dependencies, API design | Decide, flag choice + discarded alternative |
| L3 | Data model changes, payment logic, child safety, LGPD | Present options with tradeoffs, ask |

## Routing

### Engine Detection (auto-detect, never ask)

| Signal | Engine |
|--------|--------|
| Component, page, API route, styling | CODE |
| Pricing, funnel, positioning, copy | STRATEGY |
| Curriculum, exercise, difficulty, BNCC | PEDAGOGY |
| LGPD, consent, child data, ECA | COMPLIANCE |

### Request Routing

| Request type | Route to |
|-------------|----------|
| UI component / page | Next.js + React 19 + A2UI |
| Database / auth | Supabase (RLS mandatory) |
| AI tutoring logic | Claude API (structured prompts) |
| Image generation | Nano Banana |
| Payment integration | Stripe (international) / Asaas (BR) |
| Deployment | Vercel |
| Curriculum content | .gsd/ + squads intelligence |

## Tech Stack
- **Framework:** Next.js 15 (App Router) + React 19
- **Language:** TypeScript (strict mode)
- **Database/Auth:** Supabase (PostgreSQL + Row Level Security)
- **AI:** Claude API (tutoring engine)
- **Images:** Nano Banana (kid-friendly illustrations)
- **UI:** A2UI (interactive educational components)
- **Payments:** Stripe (international) / Asaas (PIX, boleto)
- **Hosting:** Vercel
- **Analytics:** PostHog

## Code Standards
- **Variables, functions, types:** English (international standard)
- **UI text, labels, messages:** Portuguese (PT-BR) with correct accents
- **Encoding:** Always UTF-8
- **Accents:** Never remove or skip Portuguese accents (é, ã, ç, ô, etc.)
- **Components:** PascalCase. Files: kebab-case.
- **Imports:** Absolute paths via @/ alias
- **Exports:** Named exports preferred over default

## Execution Cycle
`INTAKE → BRIEF → QG-1 → PLAN → EXECUTE → QG-3 → REVIEW → SHIP → REPORT`

## Quality Gates

| Gate | When | Threshold |
|------|------|-----------|
| QG-1 | After brief | Score >= 0.90 |
| QG-3 | Before ship | Score >= 0.85 |
| Floor | Any gate | Score >= 0.70 |

## Critical Rules
1. **LGPD compliance** — Art 14 (children's data). Parental consent ALWAYS required. Minimal data collection.
2. **ECA Digital** — Lei 15.211/2025. No ads targeting children. Age-appropriate content only.
3. **BNCC alignment** — All educational content must map to BNCC competencies and skills.
4. **Socratic method** — NEVER give direct answers in homework/exercise mode. Guide the student.
5. **Read 2:1** — Read 2x more context than you produce.
6. **Intelligence first** — Load .brain/ and squad intelligence before creating content.
7. **Anti-loop** — 2 consecutive failures = change strategy.
8. **Uncertainty** — State HIGH/MEDIUM/LOW confidence before claims.

## Never
- Give direct answers to homework questions
- Collect unnecessary data from children
- Show ads or commercial content to children
- Skip parental consent for any data operation
- Delete without asking
- Fake completion or mock data
- Skip quality gates
- Deploy without LGPD compliance check

## Always
- Check existing work before creating new
- Validate AI-generated content for age-appropriateness
- Include at least 1 illustration per lesson (Nano Banana)
- Apply spaced repetition to exercise scheduling
- Update STATE.yaml at session end
- Create handoff at session end
- Consult .brain/ before content creation

## Anti-Patterns

| Pattern | Problem | Fix |
|---------|---------|-----|
| Direct answers | Kills learning | Use Socratic prompts |
| Giant CLAUDE.md | Attention dilutes | Keep < 180 lines, use satellites |
| Skipping RLS | Data leak risk | Always enforce Row Level Security |
| Hardcoded curriculum | Can't adapt | Use BNCC mapping from .gsd/ |
| No image in lesson | Low engagement | Always call Nano Banana |

## Context Loading
- **Persistent:** This file + .claude/rules/ + .claude/memory/MEMORY.md
- **Session start:** .brain/STATE.yaml
- **On-demand:** .brain/BRAIN.yaml | .gsd/ | squads/ | inputs/intelligence/

## Paths

| Layer | Path |
|-------|------|
| L0 Constitution | CLAUDE.md |
| L1 Knowledge | .brain/ |
| L2 Intelligence | inputs/intelligence/ |
| L3 State | .brain/STATE.yaml |
| L4 Heuristics | .claude/rules/ |
| L5 Memory | .claude/memory/MEMORY.md |
| L6 Sessions | docs/sessions/ |
| Squad Intel | squads/ |
| GSD Process | .gsd/ |
| Outputs | outputs/ |
