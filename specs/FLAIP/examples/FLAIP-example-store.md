# FLAIP example: store

FLAIP/1.0 FINAL:

{
  "visibleReply": "Simple store patch ready for compilation.",
  "intent": "brief_patch",
  "briefPatch": {
    "operations": [
      {
        "op": "add_source",
        "label": "Customer arrivals"
      },
      {
        "op": "set_arrival_rule",
        "targetLabel": "Customer arrivals",
        "label": "customers arrive recurrently"
      },
      {
        "op": "add_entity",
        "label": "Entry"
      },
      {
        "op": "add_entity",
        "label": "Catalog"
      },
      {
        "op": "add_entity",
        "label": "Cart"
      },
      {
        "op": "add_entity",
        "label": "Checkout"
      },
      {
        "op": "add_entity",
        "label": "Receipt"
      },
      {
        "op": "add_operation",
        "targetLabel": "Entry",
        "label": "open catalog"
      },
      {
        "op": "add_operation",
        "targetLabel": "Catalog",
        "label": "add item"
      },
      {
        "op": "add_operation",
        "targetLabel": "Cart",
        "label": "submit order"
      },
      {
        "op": "add_operation",
        "targetLabel": "Checkout",
        "label": "confirm payment"
      },
      {
        "op": "set_processing_time",
        "targetLabel": "Checkout",
        "label": "120000 ms"
      },
      {
        "op": "set_queue_capacity",
        "targetLabel": "Checkout",
        "label": "8"
      },
      {
        "op": "add_drain",
        "label": "Exit after receipt"
      },
      {
        "op": "set_drain",
        "targetLabel": "Receipt",
        "label": "Exit after receipt"
      },
      {
        "op": "add_assumption",
        "label": "checkout time estimated because no value was provided"
      },
      {
        "op": "request_compile",
        "label": "validate simple store patch in FlowLine"
      }
    ]
  },
  "confidence": "medium",
  "needsUserConfirmation": false,
  "capabilityGaps": [],
  "notes": [
    "Final envelope without markdown or code fence."
  ]
}
