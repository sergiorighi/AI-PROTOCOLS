# DEVJOB/1.0

TIPO=job
VERSAO=1.0
OBJETIVO=descrever trabalho a executar por IA
ESTILO=compacto,declarativo,previsivel

## Campos

Obrigatorios:
- DEVJOB/1.0
- LANG
- ROLE
- PROJECT
- ROOT
- GOAL
- SCOPE
- FILES_ALLOWED
- ALLOW
- DENY
- RULES
- ACCEPTANCE
- OUTPUT

## Semantica

LANG=idioma esperado para comunicacao
ROLE=papel operacional do executor
PROJECT=nome do projeto
ROOT=pasta raiz permitida
GOAL=resultado desejado
SCOPE=limites positivos do trabalho
FILES_ALLOWED=arquivos que podem ser criados ou editados
ALLOW=acoes permitidas
DENY=acoes proibidas
RULES=regras de execucao
ACCEPTANCE=criterios de aceite
OUTPUT=formato esperado de resposta

## Regras

- o executor deve respeitar ROOT
- o executor deve respeitar FILES_ALLOWED
- DENY prevalece sobre ALLOW
- ACCEPTANCE define conclusao
- OUTPUT define formato final
- nao define transporte
- nao cria runtime
- nao depende de bridge

## Formato

```text
DEVJOB/1.0
LANG=pt-BR
ROLE=executor
PROJECT=nome
ROOT=caminho

GOAL=
texto curto

SCOPE=
lista curta

FILES_ALLOWED=
arquivo

ALLOW=acao,acao
DENY=acao,acao

RULES=
regra

ACCEPTANCE=
criterio

OUTPUT=DEVREPORT/1.0
```

