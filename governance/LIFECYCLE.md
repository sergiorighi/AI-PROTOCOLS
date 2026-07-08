# AI-PROTOCOLS Lifecycle

STATUS=active

## Estados

- draft: proposta inicial
- experimental: usado em testes ou sessoes limitadas
- active: recomendado para uso corrente
- deprecated: mantido por compatibilidade
- retired: removido do uso recomendado

## Fluxo

draft -> experimental -> active -> deprecated -> retired

## Regras

- toda mudanca relevante deve entrar no CHANGELOG
- promocao de estado exige criterio observavel
- deprecacao deve indicar substituto quando existir
- remocao de uso recomendado nao apaga historico
- ciclo de vida nao define implementacao
