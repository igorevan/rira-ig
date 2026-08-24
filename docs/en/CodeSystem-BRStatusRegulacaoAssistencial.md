# Status da regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## CodeSystem: Status da regulação assistencial 

 
Status da regulação assistencial. 

This Code system is referenced in the definition of the following value sets:

* [Status de regulação assistencial](ValueSet-BRStatusRegulacaoAssistencial.md)

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRStatusRegulacaoAssistencial",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRStatusRegulacaoAssistencial",
  "title" : "Status da regulação assistencial",
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
  "description" : "Status da regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "pending",
    "display" : "Pending",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Pendente"
    }]
  },
  {
    "code" : "booked",
    "display" : "Booked",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Agendado"
    }]
  },
  {
    "code" : "attended",
    "display" : "Attended/Hospitalized",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Atendido/Internado"
    }]
  },
  {
    "code" : "cancelled",
    "display" : "Cancelled",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Negado/Cancelado"
    }]
  },
  {
    "code" : "absence",
    "display" : "Absence",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Falta"
    }]
  },
  {
    "code" : "excluded",
    "display" : "Excluded",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Excluído"
    }]
  },
  {
    "code" : "returned-to-requester",
    "display" : "Returned to requester.",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Devolvido para o solicitante."
    }]
  }]
}

```
