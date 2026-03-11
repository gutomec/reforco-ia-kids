# Pesquisa: Pedagogia Adaptativa — adaptive-tutor-k12

**Fonte:** Squad `adaptive-tutor-k12` (~/squads/adaptive-tutor-k12/)
**Relevância:** ALTA — Este squad define toda a base pedagógica do produto

## Key Findings

### 1. Fundamentação Científica
- **Bloom (1984):** Tutoria individual gera 98% de melhoria vs 20% em sala convencional
- **Zone of Proximal Development (Vygotsky):** Manter conteúdo no nível de desafio adequado
- **Spaced Repetition:** Intervalos de revisão: 1d, 3d, 7d, 14d, 30d
- **Bloom's Taxonomy:** Para classificar profundidade de compreensão
- **Webb's DOK:** Para nivelar complexidade cognitiva

### 2. Sistema de Dificuldade Adaptativa
| Condição | Ação |
|----------|------|
| 3 acertos consecutivos | Aumentar dificuldade |
| 2 erros consecutivos | Diminuir dificuldade |
| Resultado misto | Manter nível |

**Níveis:** foundational → developing → proficient → advanced

### 3. Estilos de Aprendizagem
Cada conceito deve ser explicado de 4 formas:
- **Visual:** Imagens, diagramas, mapas mentais (Nano Banana)
- **Auditivo:** Explicação verbal detalhada
- **Cinestésico:** Exercícios práticos interativos (A2UI)
- **Leitura/Escrita:** Texto estruturado com destaques

### 4. Pipeline de Tutoria Completa
```
Diagnostic Assessment → Curriculum Mapping → Tutoring Session → Progress Tracking → Parent Report
```
**Duração:** 60-90 minutos para ciclo completo, 20-40 min para sessão rápida

### 5. Currículo BNCC
- Alinhamento obrigatório com Base Nacional Comum Curricular
- Organização: ano escolar → componente curricular → unidade temática → habilidade
- Suporte a Common Core (USA) e National Curriculum (UK) para futuro internacional

### 6. Detecção de Estagnação (Early Warning)
| Indicador | Threshold |
|-----------|-----------|
| Maestria flat | 3+ sessões sem progresso |
| Acurácia caindo | 2+ sessões em declínio |
| Tempo de resposta aumentando | Tendência crescente |
| Baixo engajamento | Sessões curtas, poucos exercícios |

### 7. Relatórios para Pais
- Linguagem acessível, ZERO jargão técnico
- Celebrar conquistas antes de apontar melhorias
- Recomendações práticas para casa
- Frequência: semanal, quinzenal ou mensal

### 8. Compliance
- **LGPD (Brasil):** Consentimento parental para menores
- **COPPA (USA):** Para expansão futura
- **ECA:** Proteção integral da criança

## Decisões Derivadas para o Produto

1. Implementar dificuldade adaptativa com regra 3-acertos/2-erros
2. Sempre oferecer "Explica de outro jeito" com 4 abordagens
3. Spaced repetition embutido nas trilhas (revisão automática)
4. Dashboard do pai celebra conquistas + mostra áreas de melhoria
5. Detecção de estagnação com alerta para pais
6. Alinhamento BNCC obrigatório em toda estrutura curricular
7. Cada aula ter pelo menos 1 imagem gerada + 3 exercícios adaptativos
