# Gemma4-e4b-local

Model=Gemma4-e4b-local
Provider=local
Execution context=manual_local
Protocol=FLAIP/1.0
Scenario=FCS-01 clothing store

Initial behavior=
small local model understood states
correct prefix

Chat behavior=
did not generate JSON early
waited for trigger

Final output behavior=
overall structure correct

Schema issues=
schema error in set_queue_capacity
incorrect targetLabel
JSON with duplicated op key

Protocol deviations=
self_checkout preset for cashier

Observed strengths=
small local model understood states
did not generate JSON early
waited for trigger
correct prefix
overall structure correct

Observed weaknesses=
schema error in set_queue_capacity
incorrect targetLabel
self_checkout preset for cashier
JSON with duplicated op key

Preliminary score=8.8

Recommended protocol changes=
operation_schemas_need_stricter_compact_shape
target_rules_per_operation
