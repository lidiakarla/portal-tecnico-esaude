# Modelo Municipal do Sumário de Alta Hospitalar (RISAH)

Este documento descreve o Modelo Municipal de Informação do Registro de Internação e Sumário de Alta Hospitalar (RISAH) adotado pelo Município de São Paulo, organizado conforme os incisos I a XVII do art. [cite_start]2º da Portaria GM/MS nº 8.026/2025, para integração ao Repositório Clínico Municipal – e-saúdeSP, em alinhamento aos padrões HL7 FHIR R4[cite: 464, 465].

## I – Identificação do prontuário no sistema de origem
[cite_start]Identificador local do prontuário ou episódio de internação no sistema do estabelecimento de saúde, com rastreabilidade ao sistema de origem[cite: 468].

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do prontuário no sistema de origem | Identificador estruturado | Identificador único do prontuário ou episódio de internação no sistema de origem. [cite_start]Deve ser imutável após a criação. [cite: 469] |
| 2 | [1..1] | Sistema de origem | Código estruturado | [cite_start]Código ou identificador padronizado do sistema de origem, pertencente a um catálogo municipal de sistemas. [cite: 469] |
| 2 | [0..1] | Versão do registro no sistema de origem | Texto codificado | [cite_start]Versão/ordinal do registro no sistema de origem, quando houver controle de versionamento local. [cite: 469] |

## II – Identificação do indivíduo (CPF ou CNS)
[cite_start]Identificação da pessoa a quem se refere o Sumário de Alta, preferencialmente por CNS ou CPF, com bloco demográfico complementar para vinculação[cite: 471].

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do indivíduo | – | O registro deve conter CNS ou CPF. [cite_start]Na ausência, utilizar obrigatoriamente o bloco de identificação por dados demográficos. [cite: 472] |
| 2 | [1..1] | Identificador nacional do indivíduo | Identificador estruturado | CPF. system deve indicar o namespace CPF. [cite_start]O valor deve ser validado conforme regras nacionais. [cite: 472] |
| 2 | [0..1] | Identificação por dados demográficos | Bloco estruturado | Utilizado quando CNS/CPF não estiver disponível no momento do registro. [cite_start]Deve permitir posterior vinculação. [cite: 472] |
