# Modelo Computacional - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Modelo Computacional

### Modelo Computacional

 Para a modelagem do modelo computacionais do Registro de Informação de Regulação Assistencial (RIRA), foram mapeados os campos do Modelo de Informação (MI) aos recursos do [FHIR R4](https://hl7.org/fhir/R4/). Assim, foi realizada a modelagem fechada dos perfis de modo a atender o contexto nacional. 

Foi criado um [Projeto Rede Nacional de Dados em Saúde](https://simplifier.net/redenacionaldedadosemsaude/), na plataforma [SIMPLIFIER.NET](https://simplifier.net/), para a publicação e distribuição dos perfis relacionados aos documentos computacionais em produção na rede.

### Recursos FHIR

 O modelo computacional do RIRA é definido pelo perfil Regulação Assistencial (RIRA) [`Composition`] e os demais Recursos FHIR apresentados abaixo.

| | |
| :--- | :--- |
| *Composition* | ` [BRRegulacaoAssistencial](StructureDefinition-BRRegulacaoAssistencial.md) ` |
| *Appointment* | ` [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) ` |
| *ServiceRequest* | ` [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) ` |
| *Condition* | ` [BRProblemaDiagnostico](StructureDefinition-BRProblemaDiagnostico.md) ` |

Perfis dos tipos *ValueSet* e *CodeSystem* estão associados a recursos terminológicos. No contexto de regulação assistencial e os domínios utilizados, foram criados *CodeSystems* específicos definidos pelo [Comitê Gestor de Saúde Digital (CGSD)](https://www.gov.br/saude/pt-br/acesso-a-informacao/participacao-social/conselhos-e-orgaos-colegiados/cgsd).

Vale destacar que os perfis terminológicos podem passar por atualizações e versionamentos com periodicidade específica de cada domínio, por isso é importante acompanhar a disponibilização dessas atualizações no projeto [RNDS no Simplifier](https://simplifier.net/redenacionaldedadosemsaude). 

Note que na estrutura dos perfis há elementos com bindings para *ValueSets* que apontam para *CodeSystems*. Já no JSON (`Bundle`), o elemento “*system*” sempre indicará os *CodeSystems* relacionados aos códigos (“*value*”) indicados pelo integrador (autor do registro). 

| | | | |
| :--- | :--- | :--- | :--- |
| ` [BRRegulacaoAssistencial](StructureDefinition-BRRegulacaoAssistencial.md) ` | status | [BREstadoDocumento-1.0](ValueSet-BREstadoDocumento-1.0.md) | [composition-status](http://hl7.org/fhir/composition-status) |
| type | [BRTipoDocumento-1.0](ValueSet-BRTipoDocumento-1.0.md) | [BRTipoDocumento](CodeSystem-BRTipoDocumento.md) | |
| category | [BRModalidadeAssistencialMIRA](ValueSet-BRModalidadeAssistencialMIRA.md) | [BRModalidadeAssistencial](CodeSystem-BRModalidadeAssistencial.md) | |
| relatesTo.code | [document-relationship-type](http://hl7.org/fhir/ValueSet/document-relationship-type) | [document-relationship-type](http://hl7.org/fhir/document-relationship-type) | |
| event.code | [BRStatusRegulacaoAssistencial](ValueSet-BRStatusRegulacaoAssistencial.md) | [BRStatusRegulacaoAssistencial](CodeSystem-BRStatusRegulacaoAssistencial.md) | |
| ` [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) ` | status | [BRStatusAgendamentoRegulacaoAssistencial](ValueSet-BRStatusAgendamentoRegulacaoAssistencial.md) | [appointmentstatus](http://hl7.org/fhir/appointmentstatus) |
| serviceCategory | [BRModalidadeAssistencialMIRA](ValueSet-BRModalidadeAssistencialMIRA.md) | [BRModalidadeAssistencial](CodeSystem-BRModalidadeAssistencial.md) | |
| serviceType | [BRProcedimentosNacionais-1.0](ValueSet-BRProcedimentosNacionais-1.0.md) | [BRTabelaSUS](CodeSystem-BRTabelaSUS.md) | |
| [BRCBHPMTUSS](CodeSystem-BRCBHPMTUSS.md) | | | |
| specialty | [BROcupacao-1.0](ValueSet-BROcupacao-1.0.md) | [BRCBO](CodeSystem-BRCBO.md) | |
| appointmentType | [BRCaraterAtendimentoMIRA](ValueSet-BRCaraterAtendimentoMIRA.md) | [request-priority](http://hl7.org/fhir/request-priority) | |
| participant.type | [BRTipoParticipante](ValueSet-BRTipoParticipante.md) | [BRTipoParticipante](CodeSystem-BRTipoParticipante.md) | |
| participant.status | [BRStatusParticipante](ValueSet-BRStatusParticipante.md) | [participationstatus](http://hl7.org/fhir/participationstatus) | |
| ` [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) ` | status | [BRStatusRequisicaoRegulacaoAssistencial](ValueSet-BRStatusRequisicaoRegulacaoAssistencial.md) | [request-status](http://hl7.org/fhir/request-status) |
| intent | [BRIntencaoRegulacao](ValueSet-BRIntencaoRegulacao.md) | [request-intent](http://hl7.org/fhir/request-intent) | |
| category | [BRModalidadeAssistencialMIRA](ValueSet-BRModalidadeAssistencialMIRA.md) | [BRModalidadeAssistencial](CodeSystem-BRModalidadeAssistencial.md) | |
| priority | [BRCaraterAtendimentoMIRA](ValueSet-BRCaraterAtendimentoMIRA.md) | [request-priority](http://hl7.org/fhir/request-priority) | |
| code | [BRProcedimentosNacionais-1.0](ValueSet-BRProcedimentosNacionais-1.0.md) | [BRTabelaSUS](CodeSystem-BRTabelaSUS.md) | |
| [BRCBHPMTUSS](CodeSystem-BRCBHPMTUSS.md) | | | |
| performerType | [BROcupacao-1.0](ValueSet-BROcupacao-1.0.md) | [BRCBO](CodeSystem-BRCBO.md) | |
| ` [BRProblemaDiagnostico](StructureDefinition-BRProblemaDiagnostico.md) ` | clinicalStatus | [BREstadoResolucaoDiagnosticoProblema-1.0](ValueSet-BREstadoResolucaoDiagnosticoProblema-1.0.md) | [condition-clinical](http://terminology.hl7.org/CodeSystem/condition-clinical) |
| category | [BRCategoriaCondicao](ValueSet-BRCategoriaCondicao.md) | [condition-category](http://terminology.hl7.org/CodeSystem/condition-category) | |
| code | [BRProblemaDiagnostico](ValueSet-BRProblemaDiagnostico.md) | [BRCID10](CodeSystem-BRCID10.md) | |
| [BRCIAP2](CodeSystem-BRCIAP2.md) | | | |

### Relação de Status

Abaixo é apresentado uma relação dos Status possíveis no MC do RIRA.

 **Figura 2 - Relação de Status possíveis no MC do RIRA** 

