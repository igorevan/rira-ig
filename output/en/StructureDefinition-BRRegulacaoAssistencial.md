# Regulação Assistencial - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Resource Profile: Regulação Assistencial 

 
Documento público que coleta os dados das solicitações de regulação assistencial 

**Usos:**

* Refere a este Perfil: [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/br.gov.saude.rira.fhir|current/StructureDefinition/StructureDefinition-BRRegulacaoAssistencial.json)

### Formal Views of Profile Content

 [Description Differentials, Snapshots, and other representations](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](../StructureDefinition-BRRegulacaoAssistencial.csv), [Excel](../StructureDefinition-BRRegulacaoAssistencial.xlsx), [Schematron](../StructureDefinition-BRRegulacaoAssistencial.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "BRRegulacaoAssistencial",
  "meta" : {
    "versionId" : "1",
    "lastUpdated" : "2026-09-15T11:47:26-03:00"
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
  "url" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRRegulacaoAssistencial",
  "title" : "Regulação Assistencial",
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
  "description" : "Documento público que coleta os dados das solicitações de regulação assistencial",
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
    "identity" : "cda",
    "uri" : "http://hl7.org/v3/cda",
    "name" : "CDA (R2)"
  },
  {
    "identity" : "fhirdocumentreference",
    "uri" : "http://hl7.org/fhir/documentreference",
    "name" : "FHIR DocumentReference"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Composition",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Composition",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Composition",
      "path" : "Composition",
      "short" : "Regulação Assistencial",
      "definition" : "Documento que representa o registro de uma solicitação de regulação assistencial.",
      "constraint" : [{
        "key" : "ident-4",
        "severity" : "error",
        "human" : "O número de CPF ou CNS do indivíduo deve ser igual em seus respecitivos elementos dos recursos (subject.identifier.value ou participant.actor.identifier.value).",
        "expression" : "(subject.identifier.value = section.entry.resolve().ofType(Appointment).participant.actor.identifier.value) and (subject.identifier.value = section.entry.resolve().ofType(Appointment).basedOn.resolve().ofType(ServiceRequest).subject.identifier.value) and (section.entry.resolve().ofType(Appointment).reasonReference.exists().not() or (subject.identifier.value = section.entry.resolve().ofType(Appointment).reasonReference.resolve().ofType(Condition).subject.identifier.value))"
      }]
    },
    {
      "id" : "Composition.identifier",
      "path" : "Composition.identifier",
      "max" : "0"
    },
    {
      "id" : "Composition.status",
      "path" : "Composition.status",
      "short" : "final | entered-in-error",
      "mustSupport" : true,
      "binding" : {
        "strength" : "required",
        "description" : "Estado do Documento",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoDocumento-1.0"
      }
    },
    {
      "id" : "Composition.type",
      "path" : "Composition.type",
      "short" : "Tipo de Documento",
      "definition" : "Especifica o tipo de documento que está sendo enviado na composição.",
      "mustSupport" : true,
      "binding" : {
        "strength" : "required",
        "description" : "Tipo de Documento",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRTipoDocumento-1.0"
      }
    },
    {
      "id" : "Composition.type.id",
      "path" : "Composition.type.id",
      "max" : "0"
    },
    {
      "id" : "Composition.type.coding",
      "path" : "Composition.type.coding",
      "short" : "Código definido por uma terminologia",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true
    },
    {
      "id" : "Composition.type.coding.id",
      "path" : "Composition.type.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.type.coding.system",
      "path" : "Composition.type.coding.system",
      "short" : "Identificador do sistema de terminologia",
      "min" : 1
    },
    {
      "id" : "Composition.type.coding.code",
      "path" : "Composition.type.coding.code",
      "short" : "Código conforme terminologia",
      "min" : 1,
      "fixedCode" : "RA"
    },
    {
      "id" : "Composition.type.coding.display",
      "path" : "Composition.type.coding.display",
      "max" : "0"
    },
    {
      "id" : "Composition.type.coding.userSelected",
      "path" : "Composition.type.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.type.text",
      "path" : "Composition.type.text",
      "max" : "0"
    },
    {
      "id" : "Composition.category",
      "path" : "Composition.category",
      "short" : "Modalidade assistencial",
      "definition" : "Modalidade assistencial que gerou a solicitação do procedimento.",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true,
      "binding" : {
        "strength" : "required",
        "description" : "Modalidade Assistencial",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRModalidadeAssistencialMIRA"
      }
    },
    {
      "id" : "Composition.category.coding",
      "path" : "Composition.category.coding",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true
    },
    {
      "id" : "Composition.category.coding.system",
      "path" : "Composition.category.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.category.coding.code",
      "path" : "Composition.category.coding.code",
      "min" : 1
    },
    {
      "id" : "Composition.category.coding.display",
      "path" : "Composition.category.coding.display",
      "max" : "0"
    },
    {
      "id" : "Composition.category.coding.userSelected",
      "path" : "Composition.category.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.category.text",
      "path" : "Composition.category.text",
      "max" : "0"
    },
    {
      "id" : "Composition.subject",
      "path" : "Composition.subject",
      "short" : "Identificador do indivíduo da solicitação de regulação assistencial",
      "definition" : "Identificação única do paciente, por meio de CPF ou CNS.",
      "comment" : "Nesta versão, a RNDS suportará somente indivíduos.",
      "min" : 1,
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Composition.subject.extension:unidentifiedPatient",
      "path" : "Composition.subject.extension",
      "sliceName" : "unidentifiedPatient",
      "short" : "Dados do Indivíduo Não Identificado",
      "type" : [{
        "code" : "Extension",
        "profile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuoNaoIdentificado-1.0"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Composition.subject.extension:unidentifiedPatient.extension",
      "path" : "Composition.subject.extension.extension",
      "min" : 3
    },
    {
      "id" : "Composition.subject.extension:unidentifiedPatient.extension:gender",
      "path" : "Composition.subject.extension.extension",
      "sliceName" : "gender",
      "mustSupport" : true
    },
    {
      "id" : "Composition.subject.extension:unidentifiedPatient.extension:birthYear",
      "path" : "Composition.subject.extension.extension",
      "sliceName" : "birthYear",
      "mustSupport" : true
    },
    {
      "id" : "Composition.subject.extension:unidentifiedPatient.extension:reason",
      "path" : "Composition.subject.extension.extension",
      "sliceName" : "reason",
      "mustSupport" : true
    },
    {
      "id" : "Composition.subject.reference",
      "path" : "Composition.subject.reference",
      "max" : "0"
    },
    {
      "id" : "Composition.subject.type",
      "path" : "Composition.subject.type",
      "max" : "0",
      "fixedUri" : "Patient"
    },
    {
      "id" : "Composition.subject.identifier",
      "path" : "Composition.subject.identifier",
      "short" : "Referência lógica, quando a referência literal não é conhecida",
      "constraint" : [{
        "key" : "ident-1",
        "severity" : "error",
        "human" : "O número de CPF ou CNS informado é inválido (subject.identifier.value).",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{10})\\\\d{11}$') or value.matches('^(?!(\\\\d)\\\\1{14})[125789]\\\\d{14}$')"
      }]
    },
    {
      "id" : "Composition.subject.identifier.use",
      "path" : "Composition.subject.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.subject.identifier.type",
      "path" : "Composition.subject.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.subject.identifier.system",
      "path" : "Composition.subject.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.subject.identifier.value",
      "path" : "Composition.subject.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.subject.identifier.period",
      "path" : "Composition.subject.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.subject.identifier.assigner",
      "path" : "Composition.subject.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.subject.display",
      "path" : "Composition.subject.display",
      "max" : "0"
    },
    {
      "id" : "Composition.encounter",
      "path" : "Composition.encounter",
      "max" : "0"
    },
    {
      "id" : "Composition.date",
      "path" : "Composition.date",
      "short" : "Data/hora de Geração do Documento",
      "definition" : "Data e hora em que o documento foi gerado.",
      "constraint" : [{
        "key" : "date-1",
        "severity" : "error",
        "human" : "A data do documento (Composition.date) deve ser no formato 'Ano-Mês-Dia'. Exemplo: 2026-01-01.",
        "expression" : "value.matches('^(200[1-9]|20[1-9]\\\\d|[2-9]\\\\d{3})-(0[1-9]|1[0-2])-(0[1-9]|[12]\\\\d|3[01])$')"
      }],
      "mustSupport" : true
    },
    {
      "id" : "Composition.author",
      "path" : "Composition.author",
      "short" : "Autor do documento",
      "definition" : "Identifica o Estabelecimento de Saúde responsável por gerar o documento.",
      "comment" : "Nesta versão da RNDS somente serão suportadas edições provenientes de Estabelecimentos de Saúde.",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"]
      }],
      "mustSupport" : true
    },
    {
      "id" : "Composition.author.reference",
      "path" : "Composition.author.reference",
      "max" : "0"
    },
    {
      "id" : "Composition.author.type",
      "path" : "Composition.author.type",
      "max" : "0"
    },
    {
      "id" : "Composition.author.identifier",
      "path" : "Composition.author.identifier",
      "short" : "Referência lógica, quando a referência literal não é conhecida",
      "min" : 1,
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.author.identifier.use",
      "path" : "Composition.author.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.author.identifier.type",
      "path" : "Composition.author.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.author.identifier.system",
      "path" : "Composition.author.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.author.identifier.value",
      "path" : "Composition.author.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.author.identifier.period",
      "path" : "Composition.author.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.author.identifier.assigner",
      "path" : "Composition.author.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.author.display",
      "path" : "Composition.author.display",
      "max" : "0"
    },
    {
      "id" : "Composition.title",
      "path" : "Composition.title",
      "short" : "Título do documento",
      "definition" : "Título do documento em linguagem humana.",
      "mustSupport" : true
    },
    {
      "id" : "Composition.confidentiality",
      "path" : "Composition.confidentiality",
      "max" : "0"
    },
    {
      "id" : "Composition.attester",
      "path" : "Composition.attester",
      "max" : "0"
    },
    {
      "id" : "Composition.custodian",
      "path" : "Composition.custodian",
      "max" : "0"
    },
    {
      "id" : "Composition.relatesTo",
      "path" : "Composition.relatesTo",
      "short" : "Relação a Outros Documentos",
      "definition" : "Indica uma relação entre esse documento e outro documento (ou composição) existente.",
      "requirements" : "Este elemento deve ser utilizado exclusivamente para indicar que este documento substitui (replaces) outro documento / composição; ou seja, é utilizado para cancelar o anterior e passar a considerar este no seu lugar. Este documento receberá um ID próprio; o documento anterior continuará disponível na RNDS e poderá ser recuperado integralmente por referência direta ao seu ID, garantindo a rastreabilidade do processo, mas não estará diretamente disponível na timeline do cidadão.",
      "max" : "1"
    },
    {
      "id" : "Composition.relatesTo.code",
      "path" : "Composition.relatesTo.code",
      "short" : "Tipo de Relacionamento",
      "definition" : "Indica o tipo de relacionamento que este documento tem com o outro documento (composição).",
      "requirements" : "O valor é fixado em replaces, pois a substituição de documentos é a única operação permitida na RNDS.",
      "fixedCode" : "replaces"
    },
    {
      "id" : "Composition.relatesTo.target[x]",
      "path" : "Composition.relatesTo.target[x]",
      "short" : "Documento a Ser Substituído",
      "definition" : "Referência ao documento anterior que este documento está substituindo.",
      "requirements" : "O valor é fixado em replaces, pois a substituição de documentos é a única operação permitida na RNDS.",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.relatesTo.target[x].id",
      "path" : "Composition.relatesTo.target[x].id",
      "max" : "0"
    },
    {
      "id" : "Composition.relatesTo.target[x].reference",
      "path" : "Composition.relatesTo.target[x].reference",
      "min" : 1
    },
    {
      "id" : "Composition.relatesTo.target[x].type",
      "path" : "Composition.relatesTo.target[x].type",
      "max" : "0"
    },
    {
      "id" : "Composition.relatesTo.target[x].identifier",
      "path" : "Composition.relatesTo.target[x].identifier",
      "max" : "0"
    },
    {
      "id" : "Composition.relatesTo.target[x].display",
      "path" : "Composition.relatesTo.target[x].display",
      "max" : "0"
    },
    {
      "id" : "Composition.event",
      "path" : "Composition.event",
      "slicing" : {
        "discriminator" : [{
          "type" : "value",
          "path" : "code.coding.code"
        }],
        "rules" : "open"
      },
      "short" : "Status da Solicitação",
      "definition" : "Definição dos eventos de um processo de regulação. Neste elemento será preenchido o código que identifica unicamente o status da solicitação, conforme tabela de status de solicitação.",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:pending",
      "path" : "Composition.event",
      "sliceName" : "pending",
      "short" : "Evento de solicitação de procedimento regulado",
      "definition" : "Evento destinado a modelar a solicitação de um serviço, bem como o estabelecimento solicitante.",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-2",
        "severity" : "error",
        "human" : "A Data de Agendamento (Appointment.start e Appointment.end) não pode estar preenchida caso o status da solicitação seja Pendente (pending).",
        "expression" : "code.coding.exists(code = 'pending') implies %resource.section.entry.resolve().start.empty() and %resource.section.entry.resolve().end.empty()"
      },
      {
        "key" : "mira-3",
        "severity" : "error",
        "human" : "A Data de Execução (ServiceRequest.ocurrenceDateTime) não pode estar preenchida caso o status da solicitação seja Pendente (pending).",
        "expression" : "code.coding.exists(code = 'pending') implies %resource.section.entry.resolve().basedOn.resolve().occurrenceDateTime.empty()"
      },
      {
        "key" : "mira-4",
        "severity" : "error",
        "human" : "O identificador do Estabelecimento de Saúde executante (ServiceRequest.performer) não pode estar preenchido caso o status da solicitação seja Pendente (pending).",
        "expression" : "code.coding.exists(code = 'pending') implies %resource.section.entry.resolve().basedOn.resolve().performer.empty()"
      },
      {
        "key" : "mira-13",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Pendente (pending) o status do recurso Appointment deve ser proposed e o status do recurso ServiceRequest deve ser active.",
        "expression" : "code.coding.exists(code = 'pending') implies %resource.section.entry.resolve().status = 'proposed' and %resource.section.entry.resolve().basedOn.resolve().status = 'active'"
      }]
    },
    {
      "id" : "Composition.event:pending.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:pending.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:pending.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "pending",
      "condition" : ["mira-2", "mira-3", "mira-4", "mira-13"]
    },
    {
      "id" : "Composition.event:pending.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
        "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRequisicaoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.event:pending.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:pending.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.id",
      "path" : "Composition.event.detail.identifier.type.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.coding",
      "path" : "Composition.event.detail.identifier.type.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.coding.id",
      "path" : "Composition.event.detail.identifier.type.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.coding.system",
      "path" : "Composition.event.detail.identifier.type.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.coding.code",
      "path" : "Composition.event.detail.identifier.type.coding.code",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.coding.userSelected",
      "path" : "Composition.event.detail.identifier.type.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.type.text",
      "path" : "Composition.event.detail.identifier.type.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:pending.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:pending.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester",
      "path" : "Composition.event",
      "sliceName" : "returned-to-requester",
      "short" : "Evento de devolução ao solicitante",
      "definition" : "Evento destinado a modelar a devolução (feita por um estabelecimento regulador) de um serviço ao estabelecimento solicitante.",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-14",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Devolvido para o solicitante (returned-to-requester) o status do recurso Appointment deve ser waitlist e o status do recurso ServiceRequest deve ser on-hold.",
        "expression" : "code.coding.exists(code = 'returned-to-requester') implies %resource.section.entry.resolve().status = 'waitlist' and %resource.section.entry.resolve().basedOn.resolve().status = 'on-hold'"
      }]
    },
    {
      "id" : "Composition.event:returned-to-requester.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:returned-to-requester.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:returned-to-requester.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:returned-to-requester.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "returned-to-requester",
      "condition" : ["mira-14"]
    },
    {
      "id" : "Composition.event:returned-to-requester.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:returned-to-requester.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:returned-to-requester.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"]
      }]
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.reference",
      "path" : "Composition.event.detail.reference",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:returned-to-requester.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked",
      "path" : "Composition.event",
      "sliceName" : "booked",
      "short" : "Evento de agendamento de procedimento regulado",
      "definition" : "Evento destinado a modelar o agendamento de um serviço, bem como o estabelecimento executante.",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-5",
        "severity" : "error",
        "human" : "A Data de Agendamento (Appointment.start e Appointment.end) deve ser preenchida caso o status da solicitação seja Agendado (booked).",
        "expression" : "code.coding.exists(code = 'booked') implies %resource.section.entry.resolve().start.exists() and %resource.section.entry.resolve().end.exists()"
      },
      {
        "key" : "mira-6",
        "severity" : "error",
        "human" : "O identificador do Estabelecimento de Saúde executante (ServiceRequest.performer) deve ser preenchido caso o status da solicitação seja Agendado (booked).",
        "expression" : "code.coding.exists(code = 'booked') implies %resource.section.entry.resolve().basedOn.resolve().performer.exists()"
      },
      {
        "key" : "mira-15",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Agendado (booked) o status do recurso Appointment deve ser booked e o status do recurso ServiceRequest deve ser active.",
        "expression" : "code.coding.exists(code = 'booked') implies %resource.section.entry.resolve().status = 'booked' and %resource.section.entry.resolve().basedOn.resolve().status = 'active'"
      }]
    },
    {
      "id" : "Composition.event:booked.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:booked.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:booked.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:booked.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "booked",
      "condition" : ["mira-5", "mira-6", "mira-15"]
    },
    {
      "id" : "Composition.event:booked.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:booked.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:booked.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
        "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.event:booked.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:booked.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:booked.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:booked.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:booked.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended",
      "path" : "Composition.event",
      "sliceName" : "attended",
      "short" : "Evento de atendimento de procedimento regulado",
      "definition" : "Evento destinado a modelar o atendimento de um serviço, bem como o estabelecimento executante.",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-7",
        "severity" : "error",
        "human" : "A Data de Agendamento (Appointment.start e Appointment.end) deve ser preenchida caso o status da solicitação seja Atendido/Internado (attended).",
        "expression" : "code.coding.exists(code = 'attended') implies %resource.section.entry.resolve().start.exists() and %resource.section.entry.resolve().end.exists()"
      },
      {
        "key" : "mira-8",
        "severity" : "error",
        "human" : "O identificador do Estabelecimento de Saúde executante (ServiceRequest.performer) deve ser preenchido caso o status da solicitação seja Atendido/Internado (attended).",
        "expression" : "code.coding.exists(code = 'attended') implies %resource.section.entry.resolve().basedOn.resolve().performer.exists()"
      },
      {
        "key" : "mira-9",
        "severity" : "error",
        "human" : "A Data de Execução (ServiceRequest.ocurrenceDateTime) deve ser preenchida caso o status da solicitação seja Atendido/Internado (attended).",
        "expression" : "code.coding.exists(code = 'attended') implies %resource.section.entry.resolve().basedOn.resolve().occurrenceDateTime.exists()"
      },
      {
        "key" : "mira-16",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Atendido/Internado (attended) o status do recurso Appointment deve ser fulfilled e o status do recurso ServiceRequest deve ser completed.",
        "expression" : "code.coding.exists(code = 'attended') implies %resource.section.entry.resolve().status = 'fulfilled' and %resource.section.entry.resolve().basedOn.resolve().status = 'completed'"
      }]
    },
    {
      "id" : "Composition.event:attended.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:attended.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:attended.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:attended.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "attended",
      "condition" : ["mira-7", "mira-8", "mira-9", "mira-16"]
    },
    {
      "id" : "Composition.event:attended.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:attended.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:attended.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
        "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.event:attended.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:attended.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:attended.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:attended.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:attended.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled",
      "path" : "Composition.event",
      "sliceName" : "cancelled",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-17",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Negado/Cancelado (cancelled) o status do recurso Appointment deve ser cancelled e o status do recurso ServiceRequest deve ser revoked.",
        "expression" : "code.coding.exists(code = 'cancelled') implies %resource.section.entry.resolve().status = 'cancelled' and %resource.section.entry.resolve().basedOn.resolve().status = 'revoked'"
      }]
    },
    {
      "id" : "Composition.event:cancelled.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:cancelled.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:cancelled.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:cancelled.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "cancelled",
      "condition" : ["mira-17"]
    },
    {
      "id" : "Composition.event:cancelled.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:cancelled.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:cancelled.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0"]
      }]
    },
    {
      "id" : "Composition.event:cancelled.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:cancelled.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence",
      "path" : "Composition.event",
      "sliceName" : "absence",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-10",
        "severity" : "error",
        "human" : "A Data de Agendamento (Appointment.start e Appointment.end) deve ser preenchida caso o status da solicitação seja Falta (absence).",
        "expression" : "code.coding.exists(code = 'absence') implies %resource.section.entry.resolve().start.exists() and %resource.section.entry.resolve().end.exists()"
      },
      {
        "key" : "mira-11",
        "severity" : "error",
        "human" : "O identificador do Estabelecimento de Saúde executante (ServiceRequest.performer) deve ser preenchido caso o status da solicitação seja Falta (absence).",
        "expression" : "code.coding.exists(code = 'absence') implies %resource.section.entry.resolve().basedOn.resolve().performer.exists()"
      },
      {
        "key" : "mira-12",
        "severity" : "error",
        "human" : "A Data de Execução (ServiceRequest.ocurrenceDateTime) deve ser preenchida caso o status da solicitação seja Falta (absence).",
        "expression" : "code.coding.exists(code = 'absence') implies %resource.section.entry.resolve().basedOn.resolve().occurrenceDateTime.exists()"
      },
      {
        "key" : "mira-18",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Falta (absence) o status do recurso Appointment deve ser noshow e o status do recurso ServiceRequest deve ser completed.",
        "expression" : "code.coding.exists(code = 'absence') implies %resource.section.entry.resolve().status = 'noshow' and %resource.section.entry.resolve().basedOn.resolve().status = 'completed'"
      }]
    },
    {
      "id" : "Composition.event:absence.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:absence.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:absence.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:absence.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "fixedCode" : "absence",
      "condition" : ["mira-10", "mira-11", "mira-12", "mira-18"]
    },
    {
      "id" : "Composition.event:absence.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:absence.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:absence.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
        "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.event:absence.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:absence.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:absence.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:absence.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:absence.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded",
      "path" : "Composition.event",
      "sliceName" : "excluded",
      "max" : "1",
      "constraint" : [{
        "key" : "mira-19",
        "severity" : "error",
        "human" : "Caso o status da solicitação seja Excluído (excluded) o status do recurso Appointment deve ser cancelled e o status do recurso ServiceRequest deve ser revoked.",
        "expression" : "code.coding.exists(code = 'excluded') implies %resource.section.entry.resolve().status = 'cancelled' and %resource.section.entry.resolve().basedOn.resolve().status = 'revoked'"
      }]
    },
    {
      "id" : "Composition.event:excluded.id",
      "path" : "Composition.event.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.code",
      "path" : "Composition.event.code",
      "min" : 1,
      "max" : "1",
      "binding" : {
        "strength" : "required",
        "description" : "O código que identifica unicamente o status da solicitação.",
        "valueSet" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial"
      }
    },
    {
      "id" : "Composition.event:excluded.code.id",
      "path" : "Composition.event.code.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.code.coding",
      "path" : "Composition.event.code.coding",
      "min" : 1,
      "max" : "1"
    },
    {
      "id" : "Composition.event:excluded.code.coding.id",
      "path" : "Composition.event.code.coding.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.code.coding.system",
      "path" : "Composition.event.code.coding.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:excluded.code.coding.code",
      "path" : "Composition.event.code.coding.code",
      "min" : 1,
      "fixedCode" : "excluded",
      "condition" : ["mira-19"]
    },
    {
      "id" : "Composition.event:excluded.code.coding.userSelected",
      "path" : "Composition.event.code.coding.userSelected",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.code.text",
      "path" : "Composition.event.code.text",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.period",
      "path" : "Composition.event.period",
      "short" : "Data e hora de alteração do status",
      "definition" : "Data e hora em que o status da solicitação de procedimento regulado foi alterado no sistema de origem dos dados.",
      "min" : 1
    },
    {
      "id" : "Composition.event:excluded.period.id",
      "path" : "Composition.event.period.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.period.end",
      "path" : "Composition.event.period.end",
      "min" : 1
    },
    {
      "id" : "Composition.event:excluded.detail",
      "path" : "Composition.event.detail",
      "short" : "Detalhes sobre o status da solicitação do procedimento regulado"
    },
    {
      "id" : "Composition.event:excluded.detail.id",
      "path" : "Composition.event.detail.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.type",
      "path" : "Composition.event.detail.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.identifier",
      "path" : "Composition.event.detail.identifier",
      "short" : "Estabelecimento de saúde que realizou a alteração do status",
      "definition" : "Identificação única do estabelecimento que realizou a alteração do status da solicitação de procedimento regulado, por meio do CNES.",
      "constraint" : [{
        "key" : "estab-2",
        "severity" : "error",
        "human" : "O número do CNES do estabelecimento de saúde é inválido (identifier.value). O número deve conter 7 dígitos e não pode conter letras ou caracteres especiais, apenas números.",
        "expression" : "value.matches('^(?!(\\\\d)\\\\1{6})\\\\d{7}$')"
      }]
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.id",
      "path" : "Composition.event.detail.identifier.id",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.use",
      "path" : "Composition.event.detail.identifier.use",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.type",
      "path" : "Composition.event.detail.identifier.type",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.system",
      "path" : "Composition.event.detail.identifier.system",
      "min" : 1
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.value",
      "path" : "Composition.event.detail.identifier.value",
      "min" : 1
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.period",
      "path" : "Composition.event.detail.identifier.period",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.identifier.assigner",
      "path" : "Composition.event.detail.identifier.assigner",
      "max" : "0"
    },
    {
      "id" : "Composition.event:excluded.detail.display",
      "path" : "Composition.event.detail.display",
      "max" : "0"
    },
    {
      "id" : "Composition.section",
      "path" : "Composition.section",
      "short" : "Seções do documento",
      "definition" : "Referencia todas as seções (profiles/resources) contidos neste documento.",
      "min" : 1,
      "max" : "1",
      "mustSupport" : true
    },
    {
      "id" : "Composition.section.id",
      "path" : "Composition.section.id",
      "max" : "0"
    },
    {
      "id" : "Composition.section.title",
      "path" : "Composition.section.title",
      "max" : "0"
    },
    {
      "id" : "Composition.section.code",
      "path" : "Composition.section.code",
      "max" : "0"
    },
    {
      "id" : "Composition.section.author",
      "path" : "Composition.section.author",
      "max" : "0"
    },
    {
      "id" : "Composition.section.focus",
      "path" : "Composition.section.focus",
      "max" : "0"
    },
    {
      "id" : "Composition.section.text",
      "path" : "Composition.section.text",
      "max" : "0"
    },
    {
      "id" : "Composition.section.mode",
      "path" : "Composition.section.mode",
      "max" : "0"
    },
    {
      "id" : "Composition.section.orderedBy",
      "path" : "Composition.section.orderedBy",
      "max" : "0"
    },
    {
      "id" : "Composition.section.entry",
      "path" : "Composition.section.entry",
      "min" : 1,
      "max" : "1",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial"]
      }]
    },
    {
      "id" : "Composition.section.entry.id",
      "path" : "Composition.section.entry.id",
      "max" : "0"
    },
    {
      "id" : "Composition.section.entry.reference",
      "path" : "Composition.section.entry.reference",
      "min" : 1
    },
    {
      "id" : "Composition.section.entry.type",
      "path" : "Composition.section.entry.type",
      "max" : "0"
    },
    {
      "id" : "Composition.section.entry.identifier",
      "path" : "Composition.section.entry.identifier",
      "max" : "0"
    },
    {
      "id" : "Composition.section.entry.display",
      "path" : "Composition.section.entry.display",
      "max" : "0"
    },
    {
      "id" : "Composition.section.emptyReason",
      "path" : "Composition.section.emptyReason",
      "max" : "0"
    },
    {
      "id" : "Composition.section.section",
      "path" : "Composition.section.section",
      "max" : "0"
    }]
  }
}

```
