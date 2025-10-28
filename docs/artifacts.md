# Artifacts Summary - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* **Artifacts Summary**

## Artifacts Summary

This page provides a list of the FHIR artifacts defined as part of this implementation guide.

### Structures: Resource Profiles 

These define constraints on FHIR resources for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) | Agendamento de Regulação Assistencial |
| [CID10 Avaliado](StructureDefinition-BRCID10Avaliado-1.0.md) | Diagnóstico atribuído pelo profissional de saúde ao indivíduo no contato assistencial. |
| [Regulação Assistencial (RIRA)](StructureDefinition-BRRegulacaoAssistencial.md) | Documento público que coleta os dados da regulação assistencial |
| [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) | Requisição de Regulação Assistencial |

### Structures: Extension Definitions 

These define constraints on FHIR data types for systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [Informações Complementares de Indivíduos Não Identificados](StructureDefinition-BRIndividuoNaoIdentificado-1.0.md) | Informações complementares necessárias ao Contato Assistencial na hipótese do indivíduo não poder ser identificado. |

### Terminology: Value Sets 

These define sets of codes used by systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [Caráter de Atendimento no MIRA](ValueSet-BRCaraterAtendimentoMIRA.md) | Caráter da solicitação do procedimento. |
| [Categoria do Diagnóstico](ValueSet-BRCategoriaDiagnostico.md) | ValueSet utilizado para definir o tipo de categoria do diagnóstico realizado. |
| [Classificação Brasileira de Ocupações - CBO](ValueSet-BROcupacao-1.0.md) | Classifica as profissões do mercado de trabalho brasileiro. |
| [Classificação Internacional de Doenças - Décima Revisão - CID-10](ValueSet-BRCID10-1.0.md) | Classificação Internacional de Doenças - Décima Revisão - CID-10 |
| [Estado da Resolução de Diagnóstico ou Problema](ValueSet-BREstadoResolucaoDiagnosticoProblema-1.0.md) | Estado da resolução de um diagnóstico ou problema. |
| [Estado do Documento](ValueSet-BREstadoDocumento-1.0.md) | Classifica o estado do documento que está sendo trafegado. |
| [Intenção de requisição de regulação assistencial](ValueSet-BRIntencaoRegulacao.md) | Intenção de requisição de regulação assistencial. |
| [Justificativa da Impossibilidade de Identificação do Indivíduo](ValueSet-BRJustificativaIndividuoNaoIdentificado-1.0.md) | Classifica as razões pelo qual não foi possível obter os dados de identificação do indivíduo em um contato assistencial. (Port. nº 84/SAS/MS/1997 e Port. nº02/SAS/SGEP/MS/2012) |
| [Modalidade Assistencial MIRA](ValueSet-BRModalidadeAssistencialMIRA.md) | Modalidade assistencial que gerou a solicitação do procedimento. |
| [Procedimento realizado](ValueSet-BRProcedimentosNacionais-1.0.md) | ValueSet das classificações brasileiras para procedimentos adotadas em contexto nacional, os CodeSystems apresentam os códigos da competência atual, para o envio de competência anterior os códigos devem ser consultados na RTS. |
| [Sexo](ValueSet-BRSexo-1.0.md) | Sexo de um indivíduo. |
| [Status de agendamento de regulação assistencial](ValueSet-BRStatusAgendamentoRegulacaoAssistencial.md) | Status de agendamento de regulação assistencial. |
| [Status de regulação assistencial](ValueSet-BRStatusRegulacaoAssistencial.md) | Status de agendamento de regulação assistencial. |
| [Status de requisição de regulação assistencial](ValueSet-BRStatusRequisicaoRegulacaoAssistencial.md) | Status de requisição de regulação assistencial. |
| [Status do Participante do agendamento](ValueSet-BRStatusParticipante.md) | Status do Participante do agendamento. |
| [Tipo Participante](ValueSet-BRTipoParticipante.md) | Identificação do tipo do participante envolvido na solicitação. |
| [Tipo de Documento](ValueSet-BRTipoDocumento-1.0.md) | Classifica o tipo de documento que está sendo trafegado. |

### Terminology: Code Systems 

These define new code systems used by systems conforming to this implementation guide.

| | |
| :--- | :--- |
| [Categoria do Diagnóstico](CodeSystem-BRCategoriaDiagnostico.md) | Códigos para representação do tipo de categoria do diagnóstico realizado. |
| [Classificação Brasileira Hierarquizada de Procedimentos Médicos (CBHPM) e da Terminologia Unificada da Saúde Suplementar (TUSS)](CodeSystem-BRCBHPMTUSS.md) | Classificações de procedimentos utilizadas no Brasil, no contexto da assistência à saúde privada, não complementar ao SUS, e eventualmente no SUS para classificar procedimento inexistente na Tabela SUS. |
| [Classificação Brasileira de Ocupações (CBO)](CodeSystem-BRCBO.md) | Classifica as profissões do mercado de trabalho brasileiro. |
| [Classificação Internacional de Doenças - Décima Revisão (CID-10)](CodeSystem-BRCID10.md) | Classifica as doenças e outros problemas em saúde registrados em diversos tipos de documentos clínicos. |
| [Justificativa da Impossibilidade de Identificação do Indivíduo](CodeSystem-BRJustificativaIndividuoNaoIdentificado.md) | Classifica as razões pelo qual não foi possível obter os dados de identificação do indivíduo em um contato assistencial. (Port. nº 84/SAS/MS/1997 e Port. nº02/SAS/SGEP/MS/2012) |
| [Modalidade Assistencial](CodeSystem-BRModalidadeAssistencial.md) | Classifica os contatos assistenciais de acordo com as especificidades do modo, local e duração do atendimento |
| [Status da regulação assistencial](CodeSystem-BRStatusRegulacaoAssistencial.md) | Status da regulação assistencial. |
| [Status de agendamento de regulação assistencial](CodeSystem-BRStatusAgendamentoRegulacaoAssistencial.md) | Status de agendamento de regulação assistencial. |
| [Tabela de procedimentos, medicamentos e OPM do SUS](CodeSystem-BRTabelaSUS.md) | Padroniza os códigos e as nomenclaturas dos procedimentos, medicamentos e OPM para as informações trafegadas no SUS |
| [Tipo de Documento](CodeSystem-BRTipoDocumento.md) | Classificação dos tipos de documentos compartilhados no Brasil. |
| [Tipo do Participante](CodeSystem-BRTipoParticipante.md) | Identificação do tipo do participante envolvido na solicitação. |

### Example: Example Instances 

These are example instances that show what data produced and consumed by systems conforming with this implementation guide might look like.

| | |
| :--- | :--- |
| [Bundle de exemplo do RIRA (Agendado)](Bundle-Example-RIRA-Booked.md) | Bundle de exemplo do Registro de Regulação Assistencial (RIRA) Agendado (Booked) |
| [Bundle de exemplo do RIRA (Atendido/Internado)](Bundle-Example-RIRA-Attended.md) | Bundle de exemplo do Registro de Regulação Assistencial (RIRA) Atendido/Internado (Attended) |
| [Bundle de exemplo do RIRA (Negado/Cancelado)](Bundle-Example-RIRA-Cancelled.md) | Bundle de exemplo do Registro de Regulação Assistencial (RIRA) Negado/Cancelado (Cancelled) |
| [Bundle de exemplo do RIRA (Pendente)](Bundle-Example-RIRA-Pending.md) | Bundle de exemplo do Registro de Regulação Assistencial (RIRA) Pendente (Pending) |

