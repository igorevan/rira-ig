# Intenção de requisição de regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Intenção de requisição de regulação assistencial 

 
Intenção de requisição de regulação assistencial. 

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
  "id" : "BRIntencaoRegulacao",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRIntencaoRegulacao",
  "version" : "1.0.0-release",
  "name" : "BRIntencaoRegulacao",
  "title" : "Intenção de requisição de regulação assistencial",
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
  "description" : "Intenção de requisição de regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/request-intent",
      "concept" : [{
        "code" : "proposal",
        "display" : "Proposal",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Proposto"
        }]
      },
      {
        "code" : "plan",
        "display" : "Plan",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Planejado"
        }]
      },
      {
        "code" : "directive",
        "display" : "Directive",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Diretriz"
        }]
      },
      {
        "code" : "order",
        "display" : "Order",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Autorizado"
        }]
      },
      {
        "code" : "original-order",
        "display" : "Original Order",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Autorização original"
        }]
      },
      {
        "code" : "reflex-order",
        "display" : "Reflex Order",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Autorização suplementar"
        }]
      },
      {
        "code" : "filler-order",
        "display" : "Filler Order",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Intenção de autorização"
        }]
      },
      {
        "code" : "instance-order",
        "display" : "Instance Order",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Autorização de atividade única"
        }]
      },
      {
        "code" : "option",
        "display" : "Option",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Condicional"
        }]
      }]
    }]
  }
}

```
