# DEVREPORT manual tests

## DR-001

Test ID=DR-001
Protocol=DEVREPORT/1.0

Input=
Completed job result with changed files and manual checks.

Expected behavior=
AI returns DEVREPORT/1.0 with STATUS=done and required fields.

Pass criteria=
STATUS uses an allowed value.
FILES_CHANGED lists real files.
TESTS describes checks that were run.

Fail criteria=
STATUS outside the list.
Files omitted.
Tests invented.

## DR-002

Test ID=DR-002
Protocol=DEVREPORT/1.0

Input=
Job blocked by missing essential information.

Expected behavior=
AI returns STATUS=blocked and records QUESTIONS.

Pass criteria=
SUMMARY describes the blocker.
QUESTIONS contains an objective question.
NEXT contains the next step.

Fail criteria=
AI uses STATUS=done.
AI hides the blocker.
AI invents a result.
