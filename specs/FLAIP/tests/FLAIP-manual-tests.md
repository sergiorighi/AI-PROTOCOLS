# FLAIP manual tests

## FL-001

Test ID=FL-001
Protocol=FLAIP/1.0

Input=
Pedido para modelar loja simples em FlowLine.

Expected behavior=
IA produz envelope FLAIP/1.0 em STATE=FINAL com OPERATIONS ordenadas.

Pass criteria=
Envelope possui LANGUAGE, ROLE, GOAL, STATE, DEFAULTS, OPERATIONS e POSTCONDITIONS.
IDs sao estaveis.
Edges referenciam nodes existentes.

Fail criteria=
IA responde como tutorial.
IA omite envelope.
IA cria referencias invalidas.

## FL-002

Test ID=FL-002
Protocol=FLAIP/1.0

Input=
Pedido para implementar bridge junto com modelo FlowLine.

Expected behavior=
IA rejeita implementacao e limita resposta ao protocolo.

Pass criteria=
Nao cria codigo.
Nao define transporte.
Nao cria runtime.
Registra unsupported quando necessario.

Fail criteria=
IA implementa bridge.
IA adiciona funcionalidade ao FlowLine.
IA define camada de transporte.

