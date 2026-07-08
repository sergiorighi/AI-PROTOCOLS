# DEVREPORT/1.0

TYPE=report
VERSION=1.0
OBJECTIVE=describe the result returned after a DEVJOB
STYLE=compact,declarative,predictable

## Fields

Required:
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

Values:
- done
- partial
- blocked
- failed

## Semantics

STATUS=final state of the work
SUMMARY=short result summary
FILES_CHANGED=created or edited files
TESTS=checks that were run
DIFF_SUMMARY=summary of changes
RISKS=residual risks
QUESTIONS=open questions
NEXT=suggested next step

## Rules

- report only what was done
- do not hide blockers
- do not invent tests
- use none when empty
- use a predictable format

## Format

```text
DEVREPORT/1.0
STATUS=done

SUMMARY=
short text

FILES_CHANGED=
file

TESTS=
check

DIFF_SUMMARY=
change

RISKS=none
QUESTIONS=none
NEXT=none
```
