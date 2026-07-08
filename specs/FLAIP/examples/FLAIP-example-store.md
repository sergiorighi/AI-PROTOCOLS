# FLAIP exemplo: store

```text
FLAIP/1.0
LANGUAGE=pt-BR
ROLE=flowline_model_operator
GOAL=modelar_loja_simples
STATE=FINAL

DEFAULTS=
unit=px
coordinate_space=canvas
origin=top_left

OPERATIONS=
create_node id=entry type=entry label=Entrada position=80,120
create_node id=catalog type=screen label=Catalogo position=260,120
create_node id=cart type=screen label=Carrinho position=440,120
create_node id=checkout type=action label=Checkout position=620,120
create_node id=receipt type=final label=Recibo position=800,120
create_edge id=e1 from=entry to=catalog label=abrir
create_edge id=e2 from=catalog to=cart label=adicionar_item
create_edge id=e3 from=cart to=checkout label=finalizar
create_edge id=e4 from=checkout to=receipt label=confirmar

POSTCONDITIONS=
valid_ids
valid_edges
no_runtime_changes
```

