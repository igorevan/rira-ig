# Status de requisição de regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Status de requisição de regulação assistencial 

 
Status de requisição de regulação assistencial. 

 **References** 

* [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)

### Logical Definition (CLD)

 

### Expansion

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRStatusRequisicaoRegulacaoAssistencial",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRequisicaoRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRStatusRequisicaoRegulacaoAssistencial",
  "title" : "Status de requisição de regulação assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-04-13T13:17:18.5012669+00:00",
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
  "description" : "Status de requisição de regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/request-status",
      "concept" : [{
        "code" : "draft",
        "display" : "Draft",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Rascunho"
        }]
      },
      {
        "code" : "active",
        "display" : "Active",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Ativo"
        }]
      },
      {
        "code" : "on-hold",
        "display" : "On Hold",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Em espera"
        }]
      },
      {
        "code" : "revoked",
        "display" : "Revoked",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Revogado"
        }]
      },
      {
        "code" : "completed",
        "display" : "Completed",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Completo"
        }]
      },
      {
        "code" : "entered-in-error",
        "display" : "Entered in error",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Em estado de erro"
        }]
      },
      {
        "code" : "unknown",
        "display" : "Unknown",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Desconhecido"
        }]
      }]
    }]
  }
}

```
