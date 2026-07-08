# DEVSESSION/1.0 LANG-001

Benchmark=LANG-001
Protocol=DEVSESSION/1.0
Scope=language_conformance
Status=observed

## Expected

All reports written in pt-BR.

## Observed

- Protocol structure respected.
- Narrative emitted in English by multiple providers.

## Evidence

Observed behavior shows that providers can preserve the compact protocol structure while ignoring the expected language for user-visible narrative.

## Conclusion

The LANG field is insufficiently normative.
OUTPUT_LANGUAGE contract required.
