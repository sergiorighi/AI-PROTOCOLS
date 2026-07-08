# AI-PROTOCOLS Bootstrap

Use this file to explain how AI-PROTOCOLS is introduced to a brand-new agent or executor.

Canonical protocol source: the GitHub repository URL provided by the user or project. A local path is optional and acts as a cache or working copy, not proof that a CLI/executor has already loaded the protocols.

## Responsibilities

Chat/orchestrator:

- tells the agent to use AI-PROTOCOLS
- provides AI_PROTOCOLS_SOURCE as a GitHub URL or local repository path when known
- may read README.md, HOW_TO_USE.md, and BOOTSTRAP.md for human-facing onboarding
- does not bootstrap the CLI/executor by reading files in chat

CLI/executor:

- reads only operational protocol specs required for execution
- minimum required specs: DEVSESSION/1.0, DEVJOB/1.0, and DEVREPORT/1.0
- reads job-required specs such as FLAIP/1.0 only when the job needs them
- loads those specs from AI_PROTOCOLS_SOURCE
- must resolve LOAD_CONTEXTS itself
- must not assume protocol knowledge from the chat/orchestrator
- must report READY only after its own successful initialization

## Startup Sequence

Human/chat onboarding sequence:

```text
README
-> HOW_TO_USE
-> BOOTSTRAP
```

CLI/executor bootstrap sequence:

```text
AI_PROTOCOLS_SOURCE
-> DEVSESSION spec
-> DEVJOB spec
-> DEVREPORT spec
-> job-required specs
-> LOAD_CONTEXTS resolution
-> READY
-> DEVJOB loop
```

## Locate the Repository

Prefer the canonical GitHub URL when available. AI_PROTOCOLS_SOURCE is the source that contains specs/ and the optional human-facing documents.

If the user provides a GitHub URL, set AI_PROTOCOLS_SOURCE to that URL and load required specs from that repository. The CLI/executor does not need to read README.md, HOW_TO_USE.md, or BOOTSTRAP.md to execute a job.

If the user provides a local path, set AI_PROTOCOLS_SOURCE to that path and treat it as a candidate cache or working copy. Verify that required specs exist there.

ROOT belongs to the target project session, not to AI_PROTOCOLS_SOURCE. Do not operate outside ROOT unless the user explicitly provides a permitted path and the active job allows it.

Examples:

```text
AI_PROTOCOLS_SOURCE=https://github.com/<owner>/AI-PROTOCOLS
READ=specs/DEVSESSION/DEVSESSION-1.0.md,specs/DEVJOB/DEVJOB-1.0.md,specs/DEVREPORT/DEVREPORT-1.0.md
```

```text
AI_PROTOCOLS_SOURCE=/path/to/AI-PROTOCOLS
READ=specs/DEVSESSION/DEVSESSION-1.0.md,specs/DEVJOB/DEVJOB-1.0.md,specs/DEVREPORT/DEVREPORT-1.0.md
```

## Minimal CLI Reads

For execution, the CLI/executor reads only operational protocol specs:

1. specs/DEVSESSION/DEVSESSION-1.0.md
2. specs/DEVJOB/DEVJOB-1.0.md
3. specs/DEVREPORT/DEVREPORT-1.0.md

Read FLAIP only when the job involves FlowLine external AI patches:

- specs/FLAIP/FLAIP-1.0.md

## DEVSESSION

After reading the minimal CLI specs, wait for or parse a DEVSESSION block.

Minimal session:

```text
DEVSESSION/1.0
OUTPUT_LANGUAGE=en
PROJECT=example-project
ROOT=/path/to/project
LOAD_CONTEXTS=.
PROFILE=documentation
OUTPUT=DEVREPORT/1.0
```

Bootstrap with GitHub-hosted protocol source and local project context:

```text
AI_PROTOCOLS_SOURCE=https://github.com/<owner>/AI-PROTOCOLS
```

```text
DEVSESSION/1.0
OUTPUT_LANGUAGE=en
PROJECT=example-project
ROOT=/path/to/project
LOAD_CONTEXTS=docs,README.md
PROFILE=documentation
OUTPUT=DEVREPORT/1.0
```

Do not assume protocol knowledge before reading the specifications. Names like DEVSESSION, DEVJOB, and DEVREPORT are contracts defined by the files in specs/.

## LOAD_CONTEXTS Resolution

AI_PROTOCOLS_SOURCE and LOAD_CONTEXTS are different:

- AI_PROTOCOLS_SOURCE locates the protocol repository.
- LOAD_CONTEXTS locates project context for the active session.
- AI-PROTOCOLS is not project context unless the project being edited is AI-PROTOCOLS itself.

Resolve LOAD_CONTEXTS relative to ROOT:

- Absolute paths are used as written when allowed by ROOT.
- Relative paths are resolved from ROOT.
- If LOAD_CONTEXTS names a file, read that file.
- If LOAD_CONTEXTS names a directory, read only the files needed for the session and job.
- If LOAD_CONTEXTS is omitted, unreadable, or outside ROOT, ask for clarification or report blocked.

PROJECT is only the logical project name. ROOT is the file access boundary. LOAD_CONTEXTS tells the agent which initial project context to load inside that boundary.

## READY Behavior

After successful initialization, reply with a concise READY message:

```text
READY
PROJECT=example-project
ROOT=/path/to/project
AI_PROTOCOLS_SOURCE=https://github.com/<owner>/AI-PROTOCOLS
LOADED=specs/DEVSESSION/DEVSESSION-1.0.md,specs/DEVJOB/DEVJOB-1.0.md,specs/DEVREPORT/DEVREPORT-1.0.md
OUTPUT=DEVREPORT/1.0
```

Do not start editing files during bootstrap. Edits happen only after a DEVJOB defines GOAL, FILES_ALLOWED, ALLOW, DENY, RULES, and ACCEPTANCE.

## DEVJOB Loop

For each DEVJOB:

1. Read the job fully.
2. Check ROOT and FILES_ALLOWED.
3. Apply DENY before ALLOW.
4. Execute only the GOAL inside SCOPE.
5. Verify ACCEPTANCE.
6. Return DEVREPORT/1.0.

If the job conflicts with the loaded protocols or file limits, stop and return DEVREPORT/1.0 with STATUS=blocked.
