# CHANGELOG

## v0.18

STATUS=context_loading_model_corrected

Changes:
- BOOTSTRAP.md separates AI_PROTOCOLS_SOURCE from LOAD_CONTEXTS
- LOAD_CONTEXTS clarified as project context resolved relative to ROOT
- PROJECT clarified as logical project name only
- HOW_TO_USE.md examples updated to keep protocol source out of LOAD_CONTEXTS
- no protocol semantic changes

## v0.17

STATUS=cli_bootstrap_minimal_reads

Changes:
- BOOTSTRAP.md now distinguishes human/chat onboarding from CLI/executor bootstrap
- CLI/executor required reads reduced to DEVSESSION, DEVJOB, DEVREPORT, plus job-required specs
- README.md and HOW_TO_USE.md marked as non-mandatory for CLI/executor bootstrap
- GitHub URL remains the canonical protocol source
- no protocol semantic changes

## v0.16

STATUS=bootstrap_responsibilities_clarified

Changes:
- BOOTSTRAP.md now distinguishes chat/orchestrator and CLI/executor responsibilities
- GitHub URL documented as the canonical protocol source option
- local path documented as an optional cache or working copy
- HOW_TO_USE.md and README updated to reference the clarified bootstrap flow
- no protocol semantic changes

## v0.15

STATUS=bootstrap_001_closed

Changes:
- BOOTSTRAP.md added as the canonical first-session onboarding entry
- README now points brand-new agents to BOOTSTRAP.md
- HOW_TO_USE.md now references BOOTSTRAP instead of repeating startup rules
- startup sequence documented from README through DEVJOB loop
- no protocol semantic changes

## v0.14

STATUS=first_use_guide

Changes:
- HOW_TO_USE.md added with a minimal DEVSESSION, DEVJOB, and DEVREPORT workflow
- README linked to the first-use guide
- unresolved README conflict markers removed
- no protocol semantic changes

## v0.13

STATUS=documentation_language_normalization

Changes:
- public-facing documentation normalized to English
- governance, specs, and benchmark prose translated to English
- protocol semantics preserved
- examples that demonstrate pt-BR language behavior preserved where useful

## v0.12

STATUS=public_repository_preparation

Changes:
- README revised for first GitHub publication
- Apache-2.0 license added
- CONTRIBUTING, CODE_OF_CONDUCT, and SECURITY added
- benchmark index updated with DEVSESSION/1.0
- experimental repository status made explicit
- no protocol semantic changes

## v0.11

STATUS=flaip_importer_aligned_correction

Changes:
- FLAIP/1.0 corrected to match FlowLine's current BriefPatchEnvelope importer contract
- confidence limited to low, medium, or high
- intent limited to brief_patch or brief_replace
- FLAIP/1.0 FINAL prefix required before JSON, without prefix inside visibleReply
- operations preserved with label and targetLabel, without target/entity/source/drain/value schema

## v0.10

STATUS=flaip_brief_patch_correction

Changes:
- FLAIP/1.0 realigned with the FlowLine External AI BriefPatchEnvelope contract
- generic graph operation model removed from the FLAIP specification
- store example updated to a BriefPatchEnvelope JSON envelope
- FLAIP benchmark preserved with historical correction note
- README and ROADMAP updated with the corrected FLAIP alignment

## v0.9

STATUS=devsession_language_contract

Changes:
- DEVSESSION/1.0 LANG-001 benchmark added for OUTPUT_LANGUAGE compliance
- DEVSESSION/1.0 specification added
- language contract strengthened with OUTPUT_LANGUAGE
- README updated with DEVSESSION/1.0
- ROADMAP updated with DEVSESSION/1.0 benchmarks
- CHANGELOG updated for v0.9

## v0.8

STATUS=governance_baseline

Changes:
- documentation constitution added with 10 principles
- minimum lifecycle added for protocols
- README updated with governance
- ROADMAP updated with Governance Baseline
- CHANGELOG updated for v0.8

## v0.6

STATUS=devsession_compact_experiment

Changes:
- experimental compact DEVSESSION note added
- flow recorded for loading protocols once and running subsequent jobs
- CHANGELOG updated for v0.6

## v0.5

STATUS=manual_benchmarks

Changes:
- manual benchmark structure created
- FLAIP/1.0 summary added
- preliminary results recorded by model
- README updated with benchmarks
- ROADMAP updated with Protocol Validation

## v0.3

STATUS=manual_tests

Changes:
- project vision added
- DEVJOB manual tests added
- DEVREPORT manual tests added
- FLAIP manual tests added
- README updated with VISION
- ROADMAP updated

## v0.2

STATUS=initial_flaip

Changes:
- FLAIP/1.0 specification added
- minimal store example added
- README updated with FLAIP
- ROADMAP updated

## v0.1

STATUS=initial

Changes:
- initial documentation base created
- DEVJOB/1.0 specification added
- DEVREPORT/1.0 specification added
- minimal examples added
- compact references added
