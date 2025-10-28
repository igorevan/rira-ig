# Status de agendamento de regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Status de agendamento de regulação assistencial**

## CodeSystem: Status de agendamento de regulação assistencial 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusAgendamentoRegulacaoAssistencial | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRStatusAgendamentoRegulacaoAssistencial |

 
Status de agendamento de regulação assistencial. 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRStatusAgendamentoRegulacaoAssistencial](ValueSet-BRStatusAgendamentoRegulacaoAssistencial.md)

Língua: en

Este sistema de código define o seguinte código:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRStatusAgendamentoRegulacaoAssistencial",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusAgendamentoRegulacaoAssistencial",
  "version" : "1.0.0",
  "name" : "BRStatusAgendamentoRegulacaoAssistencial",
  "title" : "Status de agendamento de regulação assistencial",
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
  "description" : "Status de agendamento de regulação assistencial.",
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
      "code" : "excluded",
      "display" : "Excluded",
      "definition" : "When document was excluded.",
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
      "definition" : "When document was returned to requester",
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
