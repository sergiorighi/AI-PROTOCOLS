AI-PROTOCOL/1.0
TYPE=operational_bundle
VERSION=1.0
SOURCE=canonical_specs
PURPOSE=operational_bootstrap
SEMANTICS=identical_to_canonical_specs
LOAD_EXTRA=only_job_required_specs

SESSION:
required=DEVSESSION/1.0,OUTPUT_LANGUAGE,PROJECT,ROOT,LOAD_CONTEXTS,OUTPUT
optional=PROFILE
rules=output_language_required; field_names_en; context_persists_until_reload; deny_over_allow; no_work_before_devjob

JOB:
required=DEVJOB/1.0,GOAL,FILES_ALLOWED,ALLOW,DENY,RULES,ACCEPTANCE,OUTPUT
optional=LANG,ROLE,PROJECT,ROOT,SCOPE
rules=root_boundary; files_allowed_boundary; deny_over_allow; acceptance_defines_done; no_transport_runtime_bridge

REPORT:
required=DEVREPORT/1.0,STATUS,SUMMARY,FILES_CHANGED,TESTS,DIFF_SUMMARY,RISKS,QUESTIONS,NEXT
status=done|partial|blocked|failed
rules=truthful; no_hidden_blockers; no_fake_tests; none_when_empty; predictable_format

EXECUTOR_BOOT:
reply=
DEVREPORT/1.0
STATUS=READY
SUMMARY=AI-PROTOCOL loaded. Waiting for DEVSESSION or DEVJOB.
FILES_CHANGED=none
TESTS=none
DIFF_SUMMARY=none
RISKS=none
QUESTIONS=none
NEXT=none

EXECUTION:
DEVSESSION ->
load_contexts_relative_to_ROOT

DEVJOB ->
check_ROOT
check_FILES_ALLOWED
apply_DENY_before_ALLOW
execute_GOAL
verify_ACCEPTANCE
return_DEVREPORT

CONFLICT ->
DEVREPORT STATUS=blocked
