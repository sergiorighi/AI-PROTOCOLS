# FLAIP/1.0 results summary

Protocol=FLAIP/1.0
Scenario=FCS-01 clothing store
Status=preliminary
Ranking=not_definitive

## Correction note

Status=preserved_with_contract_correction

- original results preserved as preliminary history
- FLAIP/1.0 realigned with the FlowLine External AI BriefPatchEnvelope contract in v0.10
- FLAIP/1.0 corrected in v0.11 for the current importer contract: intent brief_patch|brief_replace, confidence low|medium|high, prefix before JSON, and label/targetLabel operations
- observations about request_compile remain relevant to the last-operation rule
- earlier schema deviations should be read against the corrected contract

## Scores

- Gemini=9.8
- Claude=9.7
- Z.ai=9.5
- DeepSeek=9.2
- Gemma4-e4b-local=8.8

## Compliance observations

- STATE CHAT generally respected
- STATE FINAL respected after trigger
- request_compile last observed in Gemini and DeepSeek
- schema drift observed in model-specific fields
- source fields not standardized
- optional fitting room handled better when model asked before linearizing

## Quality observations

- best semantic control observed in Claude
- most compact balanced output observed in Gemini
- strongest structural caution observed in Z.ai
- local small model preserved basic state discipline

## Protocol pressure points

- duplicate gap and value for same parameter
- operation field strictness
- capabilityGap schema closure
- authorized assumption behavior
- target rules per operation

## Recommended protocol changes

Status=not_applied

- no_duplicate_gap_and_value_same_parameter
- tighten_allowed_fields_per_operation
- close_capabilityGap_schema
- clarify_authorized_assumptions
- authorized_assumption_generate_editable_value_if_safe
- operation_schemas_need_stricter_compact_shape
- target_rules_per_operation
