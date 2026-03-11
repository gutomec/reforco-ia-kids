# Child Safety Rules

## LGPD Art 14 — Proteção de Dados de Crianças e Adolescentes
- Consentimento parental OBRIGATÓRIO antes de qualquer coleta de dados
- Coleta mínima: apenas dados estritamente necessários para o serviço
- Dados de crianças NUNCA podem ser compartilhados com terceiros
- Direito à exclusão completa dos dados a qualquer momento
- Linguagem clara e acessível nos termos de uso (adequada para pais)
- Relatório de impacto à proteção de dados (RIPD) obrigatório

## ECA Digital — Lei 15.211/2025
- PROIBIDO qualquer tipo de publicidade direcionada a crianças
- PROIBIDO design manipulativo (dark patterns) que induza uso excessivo
- Conteúdo deve ser classificado por faixa etária
- Notificações push limitadas e nunca em horário noturno (22h-7h)
- Mecanismos de controle parental obrigatórios
- Tempo de uso deve ser monitorado e limitado (sugestão: 45min/sessão)

## Regras de Implementação
- Row Level Security (RLS) obrigatório em TODAS as tabelas com dados de crianças
- Nunca armazenar dados biométricos ou de localização precisa
- Logs de acesso devem registrar quem acessou dados de menores
- Criptografia em trânsito (TLS) e em repouso para dados sensíveis
- Idade mínima: 6 anos (com consentimento parental verificável)
- Conteúdo gerado por IA deve ser filtrado para adequação à faixa etária
- Imagens geradas nunca devem conter violência, medo ou conteúdo inadequado
