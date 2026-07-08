# DEVSESSION/1.0 LANG-001

Benchmark=LANG-001
Protocol=DEVSESSION/1.0
Scope=language_conformance
Status=observed

## Expected

Todos os relatorios escritos em pt-BR.

## Observed

- Estrutura do protocolo respeitada.
- Narrativa emitida em ingles por multiplos provedores.

## Evidence

O comportamento observado mostra que provedores podem preservar a estrutura compacta do protocolo enquanto ignoram o idioma esperado para narrativa visivel ao usuario.

## Conclusion

O campo LANG e insuficientemente normativo.
Contrato OUTPUT_LANGUAGE requerido.
