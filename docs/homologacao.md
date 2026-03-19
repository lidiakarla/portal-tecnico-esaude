# Processo de Homologação

[cite_start]O objetivo desta etapa é garantir a interoperabilidade técnica e a qualidade mínima dos dados antes da entrada em produção, com critérios objetivos e evidências auditáveis.

## Etapas e Gates de Aprovação

| Etapa | O que é testado | Critério de passagem (gate) |
|---|---|---|
| **Etapa 0 - Cadastro** | [cite_start]Cadastro do fornecedor/sistema, responsáveis técnicos, CNES/unidades alvo, versão do sistema[cite: 390]. | [cite_start]Cadastro aprovado e canal de contato definido[cite: 390]. |
| **Etapa 1 - Sandbox** | [cite_start]Provisionamento de credenciais/certificados, acesso a endpoints e dados sintéticos[cite: 390]. | [cite_start]Smoke tests executados com sucesso[cite: 390]. |
| **Etapa 2 - Conformidade FHIR** | [cite_start]Validação estrutural (perfis, cardinalidades) e terminologias[cite: 390]. | [cite_start]0 falhas críticas; warnings dentro do limite definido[cite: 390]. |
| **Etapa 3 - Cenários funcionais** | [cite_start]Execução de casos de uso obrigatórios (CDEM-RAC e/ou RISAH) e evidências[cite: 390]. | [cite_start]100% dos cenários obrigatórios aprovados[cite: 390]. |
| **Etapa 4 - Não funcionais** | [cite_start]Teste de desempenho básico, retries, idempotência, e segurança operacional[cite: 390]. | [cite_start]Sem vulnerabilidades críticas; comportamento consistente[cite: 390]. |
| **Etapa 5 - Homologação formal** | [cite_start]Registro do resultado, escopo homologado, versão do sistema e data[cite: 390]. | [cite_start]Publicação do status de homologado e autorização para produção[cite: 390]. |

## Evidências Exigidas (Mínimo)
[cite_start]Para a homologação, o fornecedor deve apresentar[cite: 391]:
* [cite_start]Payloads (JSON) enviados e recebidos (incluindo OperationOutcome em falhas)[cite: 392].
* [cite_start]Logs com correlation/request-id, timestamps e identificação do ambiente[cite: 393].
* [cite_start]Relatório de execução de testes (casos, resultados, evidências vinculadas)[cite: 394].
* [cite_start]Registro de versão do sistema e do IG/pacote utilizado[cite: 395].
* [cite_start]Plano de contingência (comportamento em indisponibilidade/timeout; reenvio seguro)[cite: 396].
