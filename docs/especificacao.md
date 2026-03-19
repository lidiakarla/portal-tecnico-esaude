# Especificação Técnica (HL7 FHIR R4 / IG)

Esta é a referência técnica única para integração: perfis, extensões, terminologias, bundles, transações, erros e requisitos de segurança.

## Conteúdo da Especificação
* IG por versão, com guia de leitura e compatibilidade.
* Lista de perfis (StructureDefinition) com 'Must Support' e invariants.
* ValueSets/CodeSystems e orientação de terminologias (códigos preferidos, proibidos, equivalências).
* Padrões de interação: create/update, transaction/batch, idempotência e correlacionamento.
* Padrão de erros: OperationOutcome (severity, code, diagnostics) e catálogo de códigos.
* Requisitos de segurança (ex.: OAuth2/mTLS), escopos e trilhas de auditoria.
* Convenções: timezone, precisão temporal, campos obrigatórios, e limites de payload.
