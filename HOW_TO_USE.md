# How to Use AI-PROTOCOLS

Use AI-PROTOCOLS as small text contracts. Paste the relevant block into an AI session, then ask the model to follow it exactly.

For human or chat onboarding, start with [BOOTSTRAP.md](BOOTSTRAP.md). It separates chat/orchestrator and CLI/executor responsibilities, and shows GitHub URL and local path loading.

The CLI/executor does not need to read README.md or HOW_TO_USE.md. For minimal bootstrap, it may load AI-PROTOCOL.md from AI_PROTOCOLS_SOURCE, then load project context from LOAD_CONTEXTS. Original specs remain canonical.

Minimal human request:

```text
Use AI-PROTOCOLS.
```

Minimal executor startup:

```text
Use AI-PROTOCOLS as executor.
AI_PROTOCOLS_SOURCE=https://github.com/<owner>/AI-PROTOCOLS
READ=AI-PROTOCOL.md
```

## 1. Start a Session

After bootstrap, use DEVSESSION when several jobs will share the same project context.

```text
AI_PROTOCOLS_SOURCE=https://github.com/<owner>/AI-PROTOCOLS
READ=AI-PROTOCOL.md
```

```text
DEVSESSION/1.0
OUTPUT_LANGUAGE=en
PROJECT=example-project
ROOT=/path/to/project
LOAD_CONTEXTS=.
PROFILE=documentation
OUTPUT=DEVREPORT/1.0
```

AI_PROTOCOLS_SOURCE locates the protocol repository. AI-PROTOCOL.md is the minimal operational bundle. LOAD_CONTEXTS locates project context and resolves relative to ROOT.

## 2. Send a Job

Use DEVJOB for one concrete task.

```text
DEVJOB/1.0
LANG=en
ROLE=executor
PROJECT=example-project
ROOT=/path/to/project

GOAL=
Fix duplicated text in README.

SCOPE=
Documentation only.

FILES_ALLOWED=
README.md

ALLOW=read,edit_docs_minimal,report
DENY=delete,rename,code_changes,outside_root

RULES=
Keep the change small.
Do not edit files outside FILES_ALLOWED.

ACCEPTANCE=
README has no duplicated text.
No code changed.

OUTPUT=DEVREPORT/1.0
```

## 3. Require a Report

Ask the AI to finish with DEVREPORT.

```text
DEVREPORT/1.0
STATUS=done

SUMMARY=
Duplicated README text removed.

FILES_CHANGED=
README.md

TESTS=
Manual document review.

DIFF_SUMMARY=
README: removed duplicated sentence.

RISKS=none
QUESTIONS=none
NEXT=none
```

## Notes

- Keep each job small.
- Set FILES_ALLOWED narrowly.
- Put hard limits in DENY.
- Do not use these protocols as a runtime or transport layer.
