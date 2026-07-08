# DEVSESSION/1.0

TIPO=session
VERSAO=1.0
OBJETIVO=carregar contexto operacional compartilhado para jobs subsequentes
ESTILO=compacto,declarativo,previsivel

## Campos

Obrigatorios:
- DEVSESSION/1.0
- OUTPUT_LANGUAGE
- PROJECT
- ROOT
- LOAD_CONTEXTS
- PROFILE
- OUTPUT

## Semantica

OUTPUT_LANGUAGE=idioma obrigatorio para texto visivel ao usuario
PROJECT=nome do projeto
ROOT=pasta raiz permitida
LOAD_CONTEXTS=contextos iniciais carregados na sessao
PROFILE=perfil operacional da sessao
OUTPUT=formato esperado de resposta

## Regras

- todo texto visivel ao usuario MUST ser emitido em OUTPUT_LANGUAGE
- nomes de campos e palavras-chave do protocolo permanecem em English
- jobs subsequentes podem omitir contexto ja carregado pela sessao
- FILES_ALLOWED continua limitando arquivos editaveis por job
- DENY continua prevalecendo sobre ALLOW
- OUTPUT define formato final
- nao define transporte
- nao cria runtime
- nao depende de bridge

## Formato

```text
DEVSESSION/1.0
OUTPUT_LANGUAGE=pt-BR
PROJECT=nome
ROOT=caminho
LOAD_CONTEXTS=caminho
PROFILE=documentation
OUTPUT=DEVREPORT/1.0
```

