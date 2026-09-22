# Agendamento de Regulação Assistencial - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Resource Profile: Agendamento de Regulação Assistencial 

 
Agendamento de Regulação Assistencial 

**Usos:**

* Refere a este Perfil: [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/br.gov.saude.rira.fhir|current/StructureDefinition/StructureDefinition-BRAgendamentoRegulacaoAssistencial.json)

### Formal Views of Profile Content

 [Description Differentials, Snapshots, and other representations](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](../StructureDefinition-BRAgendamentoRegulacaoAssistencial.csv), [Excel](../StructureDefinition-BRAgendamentoRegulacaoAssistencial.xlsx), [Schematron](../StructureDefinition-BRAgendamentoRegulacaoAssistencial.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "BRAgendamentoRegulacaoAssistencial",
  "meta" : {
    "lastUpdated" : "2026-09-15T14:00:00-03:00"
  },
  "language" : "pt-BR",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-wg",
    "valueCode" : "ehr"
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 1,
    "_valueInteger" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "http://fhir.saude.gov.br/rira/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "normative",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "http://fhir.saude.gov.br/rira/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-normative-version",
    "valueCode" : "4.0.1"
  }],
  "url" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRAgendamentoRegulacaoAssistencial",
  "title" : "Agendamento de Regulação Assistencial",
  "status" : "active",
  "date" : "2023-04-04",
  "publisher" : "Ministério da Saúde do Brasil",
  "contact" : [{
    "name" : "Ministério da Saúde do Brasil",
    "telecom" : [{
      "system" : "url",
      "value" : "http://www.saude.gov.br"
    },
    {
      "system" : "email",
      "value" : "cgiis.datasus@saude.gov.br"
    }]
  }],
  "description" : "Agendamento de Regulação Assistencial",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "workflow",
    "uri" : "http://hl7.org/fhir/workflow",
    "name" : "Workflow Pattern"
  },
  {
    "identity" : "rim",
    "uri" : "http://hl7.org/v3",
    "name" : "RIM Mapping"
  },
  {
    "identity" : "ical",
    "uri" : "http://ietf.org/rfc/2445",
    "name" : "iCalendar"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  },
  {
    "identity" : "v2",
    "uri" : "http://hl7.org/v2",
    "name" : "HL7 v2 Mapping"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Appointment",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Appointment",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Appointment",
      "path" : "Appointment"
    },
    {
      "id" : "Appointment.id",
      "path" : "Appointment.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.implicitRules",
      "path" : "Appointment.implicitRules",
      "max" : "0"
    },
    {
      "id" : "Appointment.language",
      "path" : "Appointment.language",
      "max" : "0"
    },
    {
      "id" : "Appointment.text",
      "path" : "Appointment.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.contained",
      "path" : "Appointment.contained",
      "max" : "0"
    },
    {
      "id" : "Appointment.identifier",
      "path" : "Appointment.identifier",
      "max" : "0"
    },
    {
      "id" : "Appointment.status",
      "path" : "Appointment.status",
      "condition" : ["mira-13",
      "mira-14",
      "mira-15",
      "mira-16",
      "mira-17",
      "mira-18",
      "mira-19"],
      "binding" : {
        "strength" : "required",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusAgendamentoRegulacaoAssistencial"
      }
    },
    {
      "id" : "Appointment.cancelationReason",
      "path" : "Appointment.cancelationReason",
      "max" : "0"
    },
    {
      "id" : "Appointment.serviceCategory",
      "path" : "Appointment.serviceCategory",
      "short" : "Modalidade assistencial",
      "definition" : "Modalidade assistencial que gerou a solicitação do procedimento.",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "Modalidade Assistencial",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRModalidadeAssistencialMIRA"
      }
    },
    {
      "id" : "Appointment.serviceCategory.coding",
      "path" : "Appointment.serviceCategory.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Appointment.serviceCategory.coding.system",
      "path" : "Appointment.serviceCategory.coding.system",
      "min" : 1
    },
    {
      "id" : "Appointment.serviceCategory.coding.code",
      "path" : "Appointment.serviceCategory.coding.code",
      "min" : 1
    },
    {
      "id" : "Appointment.serviceCategory.text",
      "path" : "Appointment.serviceCategory.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.serviceType",
      "path" : "Appointment.serviceType",
      "short" : "Código do procedimento",
      "definition" : "O código que identifica unicamente o procedimento conforme tabela SUS.",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "SIGTAP",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRProcedimentosNacionais-1.0"
      }
    },
    {
      "id" : "Appointment.serviceType.coding",
      "path" : "Appointment.serviceType.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Appointment.serviceType.coding.system",
      "path" : "Appointment.serviceType.coding.system",
      "min" : 1
    },
    {
      "id" : "Appointment.serviceType.coding.code",
      "path" : "Appointment.serviceType.coding.code",
      "min" : 1
    },
    {
      "id" : "Appointment.serviceType.text",
      "path" : "Appointment.serviceType.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.specialty",
      "path" : "Appointment.specialty",
      "short" : "Especialidade médica do executante",
      "definition" : "Identificação da especialidade médica do profissional executante do procedimento, conforme tabela de CBO. \r\nCaso o procedimento informado pertença à forma de organização 03.01.01 da tabela SUS, o código CBO será obrigatório.",
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "Classificação Brasileira de Ocupações.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BROcupacao-1.0"
      }
    },
    {
      "id" : "Appointment.specialty.coding",
      "path" : "Appointment.specialty.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Appointment.specialty.coding.system",
      "path" : "Appointment.specialty.coding.system",
      "min" : 1
    },
    {
      "id" : "Appointment.specialty.coding.code",
      "path" : "Appointment.specialty.coding.code",
      "min" : 1
    },
    {
      "id" : "Appointment.specialty.text",
      "path" : "Appointment.specialty.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.appointmentType",
      "path" : "Appointment.appointmentType",
      "short" : "Caráter da solicitação",
      "definition" : "O código que identifica unicamente o caráter da solicitação do procedimento, conforme tabela de caráter da solicitação.",
      "min" : 1,
      "binding" : {
        "strength" : "required",
        "description" : "Caráter de atendimento.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRCaraterAtendimentoMIRA"
      }
    },
    {
      "id" : "Appointment.appointmentType.coding",
      "path" : "Appointment.appointmentType.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Appointment.appointmentType.coding.system",
      "path" : "Appointment.appointmentType.coding.system",
      "min" : 1
    },
    {
      "id" : "Appointment.appointmentType.coding.code",
      "path" : "Appointment.appointmentType.coding.code",
      "min" : 1
    },
    {
      "id" : "Appointment.appointmentType.text",
      "path" : "Appointment.appointmentType.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.reasonCode",
      "path" : "Appointment.reasonCode",
      "max" : "0"
    },
    {
      "id" : "Appointment.reasonReference",
      "path" : "Appointment.reasonReference",
      "short" : "Motivo da solicitação",
      "definition" : "Identificação do motivo da solicitação do procedimento, conforme Classificação Internacional de Doenças - CID ou Classificação Internacional de Atenção Primária - CIAP.",
      "max" : "1",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRProblemaDiagnostico"]
      }]
    },
    {
      "id" : "Appointment.reasonReference.id",
      "path" : "Appointment.reasonReference.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.reasonReference.reference",
      "path" : "Appointment.reasonReference.reference",
      "min" : 1
    },
    {
      "id" : "Appointment.reasonReference.type",
      "path" : "Appointment.reasonReference.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.reasonReference.identifier",
      "path" : "Appointment.reasonReference.identifier",
      "max" : "0"
    },
    {
      "id" : "Appointment.reasonReference.display",
      "path" : "Appointment.reasonReference.display",
      "max" : "0"
    },
    {
      "id" : "Appointment.priority",
      "path" : "Appointment.priority",
      "max" : "0"
    },
    {
      "id" : "Appointment.description",
      "path" : "Appointment.description",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation",
      "path" : "Appointment.supportingInformation",
      "slicing" : {
        "discriminator" : [{
          "type" : "value",
          "path" : "identifier.system"
        }],
        "rules" : "open"
      },
      "max" : "1",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"]
      }]
    },
    {
      "id" : "Appointment.supportingInformation.id",
      "path" : "Appointment.supportingInformation.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.type",
      "path" : "Appointment.supportingInformation.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.identifier.id",
      "path" : "Appointment.supportingInformation.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.identifier.use",
      "path" : "Appointment.supportingInformation.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.identifier.type",
      "path" : "Appointment.supportingInformation.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.identifier.period",
      "path" : "Appointment.supportingInformation.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.identifier.assigner",
      "path" : "Appointment.supportingInformation.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation.display",
      "path" : "Appointment.supportingInformation.display",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization",
      "path" : "Appointment.supportingInformation",
      "sliceName" : "regulatoryOrganization",
      "short" : "Estabelecimento de saúde regulador",
      "definition" : "Identificação única do estabelecimento regulador, por meio do CNES.",
      "max" : "1",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"]
      }]
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.id",
      "path" : "Appointment.supportingInformation.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.type",
      "path" : "Appointment.supportingInformation.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier",
      "path" : "Appointment.supportingInformation.identifier",
      "min" : 1,
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.id",
      "path" : "Appointment.supportingInformation.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.use",
      "path" : "Appointment.supportingInformation.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.type",
      "path" : "Appointment.supportingInformation.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.system",
      "path" : "Appointment.supportingInformation.identifier.system",
      "min" : 1,
      "fixedUri" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.value",
      "path" : "Appointment.supportingInformation.identifier.value",
      "min" : 1
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.period",
      "path" : "Appointment.supportingInformation.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.identifier.assigner",
      "path" : "Appointment.supportingInformation.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Appointment.supportingInformation:regulatoryOrganization.display",
      "path" : "Appointment.supportingInformation.display",
      "max" : "0"
    },
    {
      "id" : "Appointment.start",
      "path" : "Appointment.start",
      "short" : "Data de agendamento - início",
      "definition" : "A data e hora agendada para a realização do procedimento regulado no padrão ISO 8601.",
      "condition" : ["mira-2", "mira-5", "mira-7", "mira-10"]
    },
    {
      "id" : "Appointment.end",
      "path" : "Appointment.end",
      "short" : "Data de agendamento - fim",
      "definition" : "A data e hora agendada para a realização do procedimento regulado no padrão ISO 8601.",
      "condition" : ["mira-2", "mira-5", "mira-7", "mira-10"]
    },
    {
      "id" : "Appointment.minutesDuration",
      "path" : "Appointment.minutesDuration",
      "max" : "0"
    },
    {
      "id" : "Appointment.slot",
      "path" : "Appointment.slot",
      "max" : "0"
    },
    {
      "id" : "Appointment.created",
      "path" : "Appointment.created",
      "short" : "Data de autorização",
      "definition" : "A data e hora em que a solicitação de procedimento regulado foi autorizada no padrão ISO 8601."
    },
    {
      "id" : "Appointment.comment",
      "path" : "Appointment.comment",
      "max" : "0"
    },
    {
      "id" : "Appointment.patientInstruction",
      "path" : "Appointment.patientInstruction",
      "max" : "0"
    },
    {
      "id" : "Appointment.basedOn",
      "path" : "Appointment.basedOn",
      "min" : 1,
      "max" : "1",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRequisicaoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Appointment.basedOn.id",
      "path" : "Appointment.basedOn.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.basedOn.reference",
      "path" : "Appointment.basedOn.reference",
      "min" : 1
    },
    {
      "id" : "Appointment.basedOn.type",
      "path" : "Appointment.basedOn.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.basedOn.identifier",
      "path" : "Appointment.basedOn.identifier",
      "max" : "0"
    },
    {
      "id" : "Appointment.basedOn.display",
      "path" : "Appointment.basedOn.display",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant",
      "path" : "Appointment.participant",
      "short" : "Identificador do paciente",
      "definition" : "Identificação única do paciente, por meio de CPF ou CNS.",
      "max" : "1"
    },
    {
      "id" : "Appointment.participant.id",
      "path" : "Appointment.participant.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.type",
      "path" : "Appointment.participant.type",
      "short" : "Função do participante da solicitação",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "Função do participante da solicitação",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRTipoParticipante"
      }
    },
    {
      "id" : "Appointment.participant.type.id",
      "path" : "Appointment.participant.type.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.type.coding",
      "path" : "Appointment.participant.type.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Appointment.participant.type.coding.id",
      "path" : "Appointment.participant.type.coding.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.type.coding.system",
      "path" : "Appointment.participant.type.coding.system",
      "min" : 1
    },
    {
      "id" : "Appointment.participant.type.coding.code",
      "path" : "Appointment.participant.type.coding.code",
      "min" : 1,
      "fixedCode" : "PCT"
    },
    {
      "id" : "Appointment.participant.type.coding.userSelected",
      "path" : "Appointment.participant.type.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.type.text",
      "path" : "Appointment.participant.type.text",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor",
      "path" : "Appointment.participant.actor",
      "short" : "Identificador do paciente",
      "definition" : "Identificação única do paciente, por meio de CPF ou CNS.",
      "min" : 1,
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0"]
      }]
    },
    {
      "id" : "Appointment.participant.actor.id",
      "path" : "Appointment.participant.actor.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.reference",
      "path" : "Appointment.participant.actor.reference",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.type",
      "path" : "Appointment.participant.actor.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.identifier",
      "path" : "Appointment.participant.actor.identifier",
      "min" : 1,
      "constraint" : [{
        "key" : "ident-1",
        "severity" : "error",
        "human" : "O número de CPF ou CNS informado é inválido (identifier.value).",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{10})\\\\d{11}$') or value.matches('^(?!(\\\\d)\\\\1{14})[125789]\\\\d{14}$')"
      }]
    },
    {
      "id" : "Appointment.participant.actor.identifier.id",
      "path" : "Appointment.participant.actor.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.identifier.use",
      "path" : "Appointment.participant.actor.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.identifier.type",
      "path" : "Appointment.participant.actor.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.identifier.system",
      "path" : "Appointment.participant.actor.identifier.system",
      "min" : 1
    },
    {
      "id" : "Appointment.participant.actor.identifier.value",
      "path" : "Appointment.participant.actor.identifier.value",
      "min" : 1
    },
    {
      "id" : "Appointment.participant.actor.identifier.period",
      "path" : "Appointment.participant.actor.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.identifier.assigner",
      "path" : "Appointment.participant.actor.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.actor.display",
      "path" : "Appointment.participant.actor.display",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.required",
      "path" : "Appointment.participant.required",
      "max" : "0"
    },
    {
      "id" : "Appointment.participant.status",
      "path" : "Appointment.participant.status",
      "short" : "Status da participação no agendamento",
      "binding" : {
        "strength" : "required",
        "description" : "Status da participação no agendamento.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusParticipante"
      }
    },
    {
      "id" : "Appointment.participant.period",
      "path" : "Appointment.participant.period",
      "max" : "0"
    },
    {
      "id" : "Appointment.requestedPeriod",
      "path" : "Appointment.requestedPeriod",
      "max" : "0"
    }]
  }
}

```
