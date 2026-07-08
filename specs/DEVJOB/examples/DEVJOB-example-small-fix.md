# DEVJOB example: small fix

```text
DEVJOB/1.0
LANG=pt-BR
ROLE=executor
PROJECT=demo
ROOT=C:\demo

GOAL=
Fix duplicated text in README.

SCOPE=
Documentation only.

FILES_ALLOWED=
README.md

ALLOW=read,edit_docs_minimal,report
DENY=delete,rename,code_changes,outside_root

RULES=
Keep the text short.
Do not change files outside the list.

ACCEPTANCE=
README has no duplicated text.
No code.

OUTPUT=DEVREPORT/1.0
```
