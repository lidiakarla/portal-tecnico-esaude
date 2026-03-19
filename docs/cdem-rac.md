# Modelo Informacional do Conjunto de Dados Expandido Municipal (CDEM-RAC)

Este documento define o Modelo Informacional do Conjunto de Dados Expandido Municipal, composto por CMD e RAC, incluindo campos, cardinalidades/ocorrências, conceito/observações, regras de preenchimento e validação.

## I – Identificação do prontuário no sistema de origem, quando disponível
Identificador local do prontuário/episódio de atendimento no sistema do estabelecimento de saúde, com rastreabilidade ao sistema de origem.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do prontuário no sistema de origem | Identificador estruturado (system \| value) | Identificador único do prontuário no sistema de origem. Deve ser imutável após a criação. Ex.: system = URI institucional do sistema (p.ex. https://<domínio>/ehr) e value = ID do prontuário/episódio. |
| 2 | [1..1] | Sistema de origem | Código estruturado | Código/identificador padronizado do sistema de origem, pertencente a um catálogo municipal de sistemas. Usado para rastreabilidade e auditoria. |
| 2 | [0..1] | Versão do prontuário no sistema de origem | Texto codificado | Versão/ordinal do prontuário no sistema de origem, quando houver versionamento local (ex.: v1, v2). |

## II – Identificação do registro no sistema de origem
Identificador local do próprio registro RAC no sistema de origem (registro de atendimento), permitindo auditoria e deduplicação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do registro no sistema de origem : número do episódio, passagem, encontro | Identificador estruturado (system \| value) | Identificador único do registro RAC no sistema de origem. Ex.: system = URI institucional do sistema e value = ID do registro. |
| 2 | [0..1] | Data e hora de criação do registro no sistema de origem | Data e hora (ISO 8601) | Momento de criação do registro no sistema de origem, quando disponível. |
| 2 | [0..1] | Versão do registro no sistema de origem | Texto codificado | Versão/ordinal do registro no sistema de origem, quando houver controle de versionamento local (ex.: v1, v2). |

## III – CNES do estabelecimento de saúde onde ocorreu o atendimento
Identificação do estabelecimento de saúde responsável pelo atendimento.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Estabelecimento de saúde do atendimento | – | Bloco obrigatório de identificação do estabelecimento de saúde onde ocorreu o atendimento (inclui telessaúde). |
| 2 | [1..1] | Identificador do estabelecimento de saúde | Identificador estruturado (system \| value) | CNES do estabelecimento. system deve ser o namespace oficial do CNES e value o código CNES. |
| 2 | [1..1] | Nome do estabelecimento de saúde | Texto livre | Nome do estabelecimento, conforme cadastro no CNES (para exibição). |
| 2 | [0..1] | Tipo de estabelecimento | Texto codificado (CNES) | Tipologia do estabelecimento conforme CNES (opcional para exibição e análise). |

## IV – Identificação do profissional responsável pelo atendimento
Identificação do(s) profissional(is) envolvido(s) no atendimento, incluindo aquele que assume responsabilidade clínica.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Profissionais do atendimento | – | Bloco de identificação do(s) profissional(is) do atendimento. Deve haver pelo menos um profissional marcado como responsável. |
| 3 | [1..N] | Profissional | | |
| 4 | [0..1] | Nome do profissional | Texto livre | |
| 4 | [1..1] | Número do conselho do profissional atendente | Caracteres numéricos | Indica o número do conselho do profissional atendente. |
| 4 | [1..1] | Conselho do profissional atendente | Texto Codificado | Indica a entidade de conselho (CRM, CRF, CRO,...). |
| 4 | [1..1] | UF do conselho do profissional atendente | Texto Codificado | Indica a UF do Conselho do Profissional atendente. |
| 3 | [1..1] | Identificador do profissional atendente | Caracteres numéricos | Identificação unívoca do profissional atendente. |
| 4 | [1..1] | Ocupação do profissional | Texto codificado | Atividade desempenhada pelo profissional que realizou o atendimento. |
| 4 | [1..1] | É o responsável pelo atendimento? | Texto codificado: | |
| 3 | [0..N] | Especialidade do profissional | Texto codificado (CBOS/CBO) | Especialidade/área de atuação do profissional. |

## V – Identificação do indivíduo atendido (CPF)
Identificação da pessoa atendida, obrigatoriamente por CPF, com bloco demográfico complementar para vinculação quando necessário.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do indivíduo | Seção | RN01: O documento deve trazer um identificador nacional do indíviduo. Se não houver (CPF/CNS), é obrigatório o bloco de dados demográficos. |
| 2 | [1..1] | Identificador Nacional do Indivíduo - CPF | Caracteres numéricos | Identificação unívoca dos usuários: CPF |
| 2 | [0..1] | Identificador Nacional do Indivíduo - CNS | Caracteres numéricos | Identificação unívoca dos usuários: CNS |
| 2 | [0..1] | Identificação por dados demográficos | - | RN03: Usados como parâmetros de pesquisa para a identificação do indivíduo. |
| 3 | [1..1] | Nome completo | Alfanumérico | -  |
| 3 | [0..1] | Nome social | Alfanumérico | - |
| 3 | [1..1] | Nome completo da mãe | Alfanumérico | - |
| 3 | [1..1] | Data de nascimento | Data | Conforme ISO 8601. |
| 3 | [1..1] | Sexo | Texto codificado | Masculino; Feminino; Ignorado  |

## VI – Data e hora de início e de término do atendimento
Registro temporal do atendimento, contendo início e término (quando disponível).

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Data e hora do atendimento | – | Bloco temporal do atendimento. A data/hora deve estar em conformidade com ISO 8601 e conter fuso/offset quando possível. |
| 2 | [1..1] | Data e hora de início do atendimento | Data e hora (ISO 8601) | Data e hora da aceitação do indivíduo para início do atendimento. |
| 2 | [1..1] | Data e hora de término do atendimento | Data e hora (ISO 8601) | Data e hora de encerramento do atendimento. |

## VII – Tipo de atendimento (presencial ou por telessaúde)
Identifica se o atendimento ocorreu presencialmente ou por telessaúde.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Tipo de atendimento | Texto codificado | Classificação do tipo de atendimento: presencial ou telessaúde. |
| 2 | [0..1] | Modalidade de telessaúde | Texto codificado | Indicar a modalidade (ex.: síncrono por vídeo, síncrono por áudio, assíncrono). |

## VIII – Informações clínicas definidas na Estratégia e-SUS APS
Conjunto de informações clínicas estruturadas (medições/aferições, uso de substâncias, etc).

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [0..1] | Observações |  |  |
| 2 | [0..1] | Sinais vitais |  |  |
| 3 | [0..1] | Pressão Arterial |  |  |
| 4 | [1..1] | Sistólica | Caracteres numéricos | Quantidade indicada de 0 a 1000 |
| 4 | [1..1] | Diastólica | Caracteres numéricos | Quantidade indicada de 0 a 1000 |
| 2 | [0..1] | Medições |  |  |
| 3 | [0..1] | Peso | Caracteres numéricos | Quantidade indicada de 0 a 1000  |
| 3 | [0..1] | Altura | Caracteres numéricos | Quantidade indicada de 0 a 1000  |

## IX – Motivo do atendimento (CID ou CIAP)
Motivo principal do atendimento, codificado em CID ou CIAP.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [0..1] | Motivo do atendimento estruturado |  |  |
| 3 | [1..1] | Terminologia que descreve o motivo | Texto codificado | CID ; CIAP |
| 3 | [1..1] | Código do motivo do atendimento | Texto codificado | cid-9; cid-10; cid-11; ciap-1; Ciap-2 |
| 2 | [0..1] | Declaração subjetiva do indivíduo | Texto livre |  |

## X – Problemas ou diagnósticos avaliados
Conjunto de problemas/diagnósticos avaliados durante o atendimento.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..N] | Problemas / diagnósticos avaliados | | Informações sobre a condição de saúde, lesão, deficiência.  |
| 2 | [1..1] | Código do diagnóstico/Problema | Texto codificado | Código do diagnóstico/Problema detectado (ex: Z47; M52.3)  |
| 2 | [0..1] | Estado de resolução do problema | Texto codificado | Ativo, Recorrente, Recidiva, Inativo, Remissão, Resolvido  |
