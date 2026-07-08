# DEVSESSION Compact Test

STATUS=experimental

Objetivo:
- validar uso compacto de DEVSESSION para carregar protocolos uma vez
- executar jobs subsequentes sem repetir instrucoes completas
- manter resposta final em DEVREPORT/1.0

Observacoes:
- a sessao carregou DEVJOB/1.0 e DEVREPORT/1.0 no inicio
- o job subsequente pode omitir campos ja assumidos pela sessao
- FILES_ALLOWED continua limitando arquivos editaveis por job
- DENY continua prevalecendo sobre ALLOW

Resultado esperado:
- menor repeticao de protocolo em mensagens futuras
- execucao previsivel por job
- relatorio compacto e padronizado
