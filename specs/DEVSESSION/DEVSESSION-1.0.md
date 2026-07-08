# DEVSESSION/1.0

TYPE=session
VERSION=1.0
OBJECTIVE=load shared operational context for subsequent jobs
STYLE=compact,declarative,predictable

## Fields

Required:
- DEVSESSION/1.0
- OUTPUT_LANGUAGE
- PROJECT
- ROOT
- LOAD_CONTEXTS
- PROFILE
- OUTPUT

## Semantics

OUTPUT_LANGUAGE=mandatory language for user-visible text
PROJECT=project name
ROOT=allowed root folder
LOAD_CONTEXTS=initial contexts loaded in the session
PROFILE=session operational profile
OUTPUT=expected response format

## Rules

- all user-visible text MUST be emitted in OUTPUT_LANGUAGE
- protocol field names and keywords remain in English
- subsequent jobs may omit context already loaded by the session
- FILES_ALLOWED continues to limit editable files per job
- DENY continues to take precedence over ALLOW
- OUTPUT defines the final format
- does not define transport
- does not create a runtime
- does not depend on a bridge

## Format

```text
DEVSESSION/1.0
OUTPUT_LANGUAGE=pt-BR
PROJECT=name
ROOT=path
LOAD_CONTEXTS=path
PROFILE=documentation
OUTPUT=DEVREPORT/1.0
```
