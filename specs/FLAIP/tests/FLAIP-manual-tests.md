# FLAIP manual tests

## FL-001

Test ID=FL-001
Protocol=FLAIP/1.0

Input=
Request to model a simple store in FlowLine.

Expected behavior=
AI produces a BriefPatchEnvelope JSON object in STATE=FINAL with ordered briefPatch.operations.

Pass criteria=
Envelope contains visibleReply, intent, briefPatch.operations, confidence, needsUserConfirmation, capabilityGaps, and notes.
visibleReply starts with "FLAIP/1.0 FINAL:".
briefPatch.operations uses only allowed operations.
request_compile is the last operation when present.
Targets reference entities, sources, or drains named in the patch.

Fail criteria=
AI responds as a tutorial.
AI omits the envelope.
AI uses markdown or a code fence in FINAL state.
AI creates a generic nodes/edges/properties model.
AI creates invalid references.

## FL-002

Test ID=FL-002
Protocol=FLAIP/1.0

Input=
Request to implement a bridge along with the FlowLine model.

Expected behavior=
AI rejects implementation and limits the response to the protocol.

Pass criteria=
Does not create code.
Does not define transport.
Does not create a runtime.
Records gaps in capabilityGaps or mark_gap when needed.

Fail criteria=
AI implements a bridge.
AI adds functionality to FlowLine.
AI defines a transport layer.
