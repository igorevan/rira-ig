# Status de agendamento de regulação assistencial (CodeSystem) - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## CodeSystem: Status de agendamento de regulação assistencial (CodeSystem) 

 
Status de agendamento de regulação assistencial. 

This Code system is referenced in the definition of the following value sets:

* [Status de agendamento de regulação assistencial (ValueSet)](ValueSet-BRStatusAgendamentoRegulacaoAssistencial.md)

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRStatusAgendamentoRegulacaoAssistencial",
  "language" : "en",
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
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "normative",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-normative-version",
    "valueCode" : "4.0.1"
  }],
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusAgendamentoRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRStatusAgendamentoRegulacaoAssistencial",
  "title" : "Status de agendamento de regulação assistencial (CodeSystem)",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-26T13:19:46.9743559+00:00",
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
  "description" : "Status de agendamento de regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "excluded",
    "display" : "Excluded",
    "definition" : "When document was excluded.",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Excluído"
    }]
  },
  {
    "code" : "returned-to-requester",
    "display" : "Returned to requester.",
    "definition" : "When document was returned to requester",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Devolvido para o solicitante."
    }]
  }]
}

```
