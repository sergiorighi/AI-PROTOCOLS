# Gemma4-e4b-local

Model=Gemma4-e4b-local
Provider=local
Execution context=manual_local
Protocol=FLAIP/1.0
Scenario=FCS-01 loja de roupas

Initial behavior=
modelo local pequeno entendeu estados
prefixo correto

Chat behavior=
nao gerou JSON antes
esperou trigger

Final output behavior=
estrutura geral correta

Schema issues=
erro de schema em set_queue_capacity
targetLabel incorreto
JSON com chave op duplicada

Protocol deviations=
preset self_checkout para caixa

Observed strengths=
modelo local pequeno entendeu estados
nao gerou JSON antes
esperou trigger
prefixo correto
estrutura geral correta

Observed weaknesses=
erro de schema em set_queue_capacity
targetLabel incorreto
preset self_checkout para caixa
JSON com chave op duplicada

Preliminary score=8.8

Recommended protocol changes=
operation_schemas_need_stricter_compact_shape
target_rules_per_operation

