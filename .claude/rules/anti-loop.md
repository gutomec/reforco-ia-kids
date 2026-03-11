# Anti-Loop Rules

## Circuit Breaker para Builds
- Máximo 3 tentativas consecutivas para resolver o mesmo erro de build
- Após 3 falhas: parar, documentar o erro, mudar de estratégia
- Se o erro persistir após mudança de estratégia: escalar para L3 (pedir ajuda)

## Falhas de API
- Máximo 3 retries em chamadas à Claude API, Nano Banana ou Supabase
- Backoff exponencial: 1s → 3s → 9s
- Após 3 falhas: ativar fallback

## Fallbacks
- **Claude API falhou:** Usar cache de exercícios pré-gerados por matéria/ano
- **Nano Banana falhou:** Usar banco de imagens estáticas pré-aprovadas
- **Supabase falhou:** Modo offline com localStorage (sincronizar depois)
- **Stripe/Asaas falhou:** Mostrar mensagem amigável, não travar o fluxo

## Detecção de Loop
- Se o mesmo arquivo for editado 5+ vezes sem progresso: parar e reavaliar
- Se testes falham com o mesmo erro 3+ vezes: mudar abordagem
- Se geração de conteúdo repete padrões: variar prompt/temperatura
