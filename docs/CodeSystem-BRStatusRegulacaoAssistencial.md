# Status da regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Status da regulação assistencial**

## CodeSystem: Status da regulação assistencial 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRStatusRegulacaoAssistencial |

 
Status da regulação assistencial. 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRStatusRegulacaoAssistencial](ValueSet-BRStatusRegulacaoAssistencial.md)

Língua: en

Este case-sensitive sistema de código `http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial` define o seguinte códigos:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRStatusRegulacaoAssistencial",
  "language" : "en",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 1,
      "_valueInteger" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
            "valueCanonical" : "http://www.saude.gov.br/fhir/r4/ImplementationGuide/br.gov.saude.rira.fhir"
          }
        ]
      }
    },
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
      "valueCode" : "informative",
      "_valueCode" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
            "valueCanonical" : "http://www.saude.gov.br/fhir/r4/ImplementationGuide/br.gov.saude.rira.fhir"
          }
        ]
      }
    }
  ],
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial",
  "version" : "1.0.0",
  "name" : "BRStatusRegulacaoAssistencial",
  "title" : "Status da regulação assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-26T13:19:46.9743559+00:00",
  "publisher" : "Ministério da Saúde do Brasil",
  "contact" : [
    {
      "name" : "Ministério da Saúde do Brasil",
      "telecom" : [
        {
          "system" : "url",
          "value" : "http://www.saude.gov.br"
        }
      ]
    }
  ],
  "description" : "Status da regulação assistencial.",
  "jurisdiction" : [
    {
      "coding" : [
        {
          "system" : "urn:iso:std:iso:3166",
          "code" : "BR"
        }
      ]
    }
  ],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [
    {
      "code" : "pending",
      "display" : "Pending",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Pendente"
        }
      ]
    },
    {
      "code" : "booked",
      "display" : "Booked",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Agendado"
        }
      ]
    },
    {
      "code" : "attended",
      "display" : "Attended/Hospitalized",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Atendido/Internado"
        }
      ]
    },
    {
      "code" : "cancelled",
      "display" : "Cancelled",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Negado/Cancelado"
        }
      ]
    },
    {
      "code" : "absence",
      "display" : "Absence",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Falta"
        }
      ]
    },
    {
      "code" : "excluded",
      "display" : "Excluded",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Excluído"
        }
      ]
    },
    {
      "code" : "returned-to-requester",
      "display" : "Returned to requester.",
      "designation" : [
        {
          "language" : "pt-BR",
          "value" : "Devolvido para o solicitante."
        }
      ]
    }
  ]
}

```
