# DEVREPORT/1.0

TIPO=report
VERSAO=1.0
OBJETIVO=descrever resultado retornado apos um DEVJOB
ESTILO=compacto,declarativo,previsivel

## Campos

Obrigatorios:
- DEVREPORT/1.0
- STATUS
- SUMMARY
- FILES_CHANGED
- TESTS
- DIFF_SUMMARY
- RISKS
- QUESTIONS
- NEXT

## STATUS

Valores:
- done
- partial
- blocked
- failed

## Semantica

STATUS=estado final do trabalho
SUMMARY=resumo curto do resultado
FILES_CHANGED=arquivos criados ou editados
TESTS=verificacoes executadas
DIFF_SUMMARY=resumo das mudancas
RISKS=riscos residuais
QUESTIONS=perguntas em aberto
NEXT=proximo passo sugerido

## Regras

- relatar somente o que foi feito
- nao ocultar bloqueios
- nao inventar testes
- usar none quando vazio
- usar formato previsivel

## Formato

```text
DEVREPORT/1.0
STATUS=done

SUMMARY=
texto curto

FILES_CHANGED=
arquivo

TESTS=
verificacao

DIFF_SUMMARY=
mudanca

RISKS=none
QUESTIONS=none
NEXT=none
```

