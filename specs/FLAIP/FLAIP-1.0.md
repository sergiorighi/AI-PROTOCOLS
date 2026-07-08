# FLAIP/1.0

NAME=FlowLine AI Protocol
TYPE=protocol
VERSION=1.0
TARGET=external_ai
HOST=FlowLine
STYLE=declarative,compact,stateful

## LANGUAGE

LANG=pt-BR
FORMAT=key_value,short_lists
AUDIENCE=llm
FORBIDDEN=tutorial,prompt,transport,runtime

## ROLE

ROLE=flowline_model_operator
RULE=operate_model_only
RULE=preserve_existing_architecture
FORBIDDEN=implement_code,create_bridge,add_flowline_features

## GOAL

GOAL=communicate_model_changes_to_flowline
SCOPE=model_intent,model_operations,postconditions
OUT_OF_SCOPE=transport,authentication,execution_runtime

## STATE CHAT

STATE=CHAT
PURPOSE=analysis_and_negotiation
ALLOW=questions,assumptions,plan,validation
FORBIDDEN=final_operations_without_confirmation

## STATE FINAL

STATE=FINAL
PURPOSE=deliver_envelope
ALLOW=single_envelope
FORBIDDEN=extra_commentary,partial_payload

## ENVELOPE

ENVELOPE=required
ROOT_KEY=FLAIP/1.0
FIELDS=LANGUAGE,ROLE,GOAL,STATE,DEFAULTS,OPERATIONS,POSTCONDITIONS
RULE=one_final_envelope

## DEFAULTS

DEFAULT unit=px
DEFAULT time_unit=ms
DEFAULT coordinate_space=canvas
DEFAULT origin=top_left
DEFAULT id_policy=stable_required

## OPERATIONS

OP=create_node
FIELDS=id,type,label,position

OP=update_node
FIELDS=id,patch

OP=delete_node
FIELDS=id

OP=create_edge
FIELDS=id,from,to,label

OP=update_edge
FIELDS=id,patch

OP=delete_edge
FIELDS=id

OP=set_property
FIELDS=target,key,value

RULE=operations_ordered
RULE=ids_unique
RULE=references_existing_or_created_ids

## TIME

TIME=optional
FIELDS=at,duration,sequence
DEFAULT at=0
DEFAULT duration=0
RULE=time_relative_to_envelope

## UNSUPPORTED

UNSUPPORTED=must_report
ACTION=omit_operation
FIELD=reason
FORBIDDEN=silent_fallback

## PRESETS

PRESET=store
NODES=entry,catalog,cart,checkout,payment,receipt
EDGES=browse,add_item,submit_order,confirm_payment

PRESET=process
NODES=start,step,end
EDGES=next

## POSTCONDITIONS

POSTCONDITION=valid_ids
POSTCONDITION=valid_edges
POSTCONDITION=no_unsupported_silent
POSTCONDITION=no_runtime_changes
POSTCONDITION=no_transport_defined

