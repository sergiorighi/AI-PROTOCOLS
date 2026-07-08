# DEVJOB/1.0

TYPE=job
VERSION=1.0
OBJECTIVE=describe work to be executed by AI
STYLE=compact,declarative,predictable

## Fields

Required:
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

## Semantics

LANG=expected communication language
ROLE=executor operational role
PROJECT=project name
ROOT=allowed root folder
GOAL=desired result
SCOPE=positive work limits
FILES_ALLOWED=files that may be created or edited
ALLOW=allowed actions
DENY=forbidden actions
RULES=execution rules
ACCEPTANCE=acceptance criteria
OUTPUT=expected response format

## Rules

- the executor must respect ROOT
- the executor must respect FILES_ALLOWED
- DENY takes precedence over ALLOW
- ACCEPTANCE defines completion
- OUTPUT defines the final format
- does not define transport
- does not create a runtime
- does not depend on a bridge

## Format

```text
DEVJOB/1.0
LANG=pt-BR
ROLE=executor
PROJECT=name
ROOT=path

GOAL=
short text

SCOPE=
short list

FILES_ALLOWED=
file

ALLOW=action,action
DENY=action,action

RULES=
rule

ACCEPTANCE=
criterion

OUTPUT=DEVREPORT/1.0
```
