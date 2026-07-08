# DEVREPORT manual tests

## DR-001

Test ID=DR-001
Protocol=DEVREPORT/1.0

Input=
Resultado de job concluido com arquivos alterados e verificacoes manuais.

Expected behavior=
IA retorna DEVREPORT/1.0 com STATUS=done e campos obrigatorios.

Pass criteria=
STATUS usa valor permitido.
FILES_CHANGED lista arquivos reais.
TESTS descreve verificacoes executadas.

Fail criteria=
STATUS fora da lista.
Arquivos omitidos.
Testes inventados.

## DR-002

Test ID=DR-002
Protocol=DEVREPORT/1.0

Input=
Job bloqueado por falta de informacao essencial.

Expected behavior=
IA retorna STATUS=blocked e registra QUESTIONS.

Pass criteria=
SUMMARY descreve bloqueio.
QUESTIONS contem pergunta objetiva.
NEXT contem proximo passo.

Fail criteria=
IA usa STATUS=done.
IA oculta bloqueio.
IA inventa resultado.

