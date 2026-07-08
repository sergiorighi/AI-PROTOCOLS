# FLAIP exemplo: store

FLAIP/1.0 FINAL:

{
  "visibleReply": "Patch de loja simples pronto para compilacao.",
  "intent": "brief_patch",
  "briefPatch": {
    "operations": [
      {
        "op": "add_source",
        "label": "Chegada de clientes"
      },
      {
        "op": "set_arrival_rule",
        "targetLabel": "Chegada de clientes",
        "label": "clientes chegam de forma recorrente"
      },
      {
        "op": "add_entity",
        "label": "Entrada"
      },
      {
        "op": "add_entity",
        "label": "Catalogo"
      },
      {
        "op": "add_entity",
        "label": "Carrinho"
      },
      {
        "op": "add_entity",
        "label": "Checkout"
      },
      {
        "op": "add_entity",
        "label": "Recibo"
      },
      {
        "op": "add_operation",
        "targetLabel": "Entrada",
        "label": "abrir catalogo"
      },
      {
        "op": "add_operation",
        "targetLabel": "Catalogo",
        "label": "adicionar item"
      },
      {
        "op": "add_operation",
        "targetLabel": "Carrinho",
        "label": "finalizar pedido"
      },
      {
        "op": "add_operation",
        "targetLabel": "Checkout",
        "label": "confirmar pagamento"
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
        "label": "Saida apos recibo"
      },
      {
        "op": "set_drain",
        "targetLabel": "Recibo",
        "label": "Saida apos recibo"
      },
      {
        "op": "add_assumption",
        "label": "tempo de checkout estimado por ausencia de dado informado"
      },
      {
        "op": "request_compile",
        "label": "validar patch de loja simples no FlowLine"
      }
    ]
  },
  "confidence": "medium",
  "needsUserConfirmation": false,
  "capabilityGaps": [],
  "notes": [
    "Envelope final sem markdown e sem code fence."
  ]
}
