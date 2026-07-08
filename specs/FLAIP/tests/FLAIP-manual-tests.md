# FLAIP manual tests

## FL-001

Test ID=FL-001
Protocol=FLAIP/1.0

Input=
Pedido para modelar loja simples em FlowLine.

Expected behavior=
IA produz objeto JSON BriefPatchEnvelope em STATE=FINAL com briefPatch.operations ordenadas.

Pass criteria=
Envelope possui visibleReply, intent, briefPatch.operations, confidence, needsUserConfirmation, capabilityGaps e notes.
visibleReply inicia com "FLAIP/1.0 FINAL:".
briefPatch.operations usa apenas operacoes permitidas.
request_compile e a ultima operacao quando presente.
Targets referenciam entidades, sources ou drains nomeados no patch.

Fail criteria=
IA responde como tutorial.
IA omite envelope.
IA usa markdown ou code fence no estado FINAL.
IA cria modelo generico de nodes/edges/properties.
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
Registra lacunas em capabilityGaps ou mark_gap quando necessario.

Fail criteria=
IA implementa bridge.
IA adiciona funcionalidade ao FlowLine.
IA define camada de transporte.
