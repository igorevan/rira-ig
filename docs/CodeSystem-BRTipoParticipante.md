# Tipo do Participante - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Tipo do Participante**

## CodeSystem: Tipo do Participante 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRTipoParticipante |

 
Identificação do tipo do participante envolvido na solicitação. 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRTipoParticipante](ValueSet-BRTipoParticipante.md)

Língua: pt-BR

Este case-sensitive sistema de código `http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante` define o seguinte códigos:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRTipoParticipante",
  "language" : "pt-BR",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante",
  "version" : "1.0.0",
  "name" : "BRTipoParticipante",
  "title" : "Tipo do Participante",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-04-13T18:16:19.9468275+00:00",
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
  "description" : "Identificação do tipo do participante envolvido na solicitação.",
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
      "code" : "PCT",
      "display" : "Paciente"
    },
    {
      "code" : "ESS",
      "display" : "Estabelecimento de saúde solicitante"
    },
    {
      "code" : "ESE",
      "display" : "Estabelecimento de saúde executante"
    },
    {
      "code" : "ESR",
      "display" : "Estabelecimento de saúde regulador"
    }
  ]
}

```
