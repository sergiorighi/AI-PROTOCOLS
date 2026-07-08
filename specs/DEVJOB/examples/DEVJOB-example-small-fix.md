# DEVJOB exemplo: small fix

```text
DEVJOB/1.0
LANG=pt-BR
ROLE=executor
PROJECT=demo
ROOT=C:\demo

GOAL=
Corrigir texto duplicado no README.

SCOPE=
Somente documentacao.

FILES_ALLOWED=
README.md

ALLOW=read,edit_docs_minimal,report
DENY=delete,rename,code_changes,outside_root

RULES=
Manter o texto curto.
Nao alterar arquivos fora da lista.

ACCEPTANCE=
README sem texto duplicado.
Sem codigo.

OUTPUT=DEVREPORT/1.0
```

