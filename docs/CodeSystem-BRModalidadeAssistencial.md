# Modalidade Assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Modalidade Assistencial**

## CodeSystem: Modalidade Assistencial 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRModalidadeAssistencial |

 
Classifica os contatos assistenciais de acordo com as especificidades do modo, local e duração do atendimento 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRModalidadeAssistencialMIRA](ValueSet-BRModalidadeAssistencialMIRA.md)

Língua: pt-BR

Este sistema de código define o seguinte código:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRModalidadeAssistencial",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
  "version" : "1.0.0",
  "name" : "BRModalidadeAssistencial",
  "title" : "Modalidade Assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-11T18:16:19.9468275+00:00",
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
  "description" : "Classifica os contatos assistenciais de acordo com as especificidades do modo, local e duração do atendimento",
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
      "code" : "01",
      "display" : "Atenção Básica"
    },
    {
      "code" : "02",
      "display" : "Atenção Domiciliar"
    },
    {
      "code" : "03",
      "display" : "Atenção Intermediária"
    },
    {
      "code" : "04",
      "display" : "Atenção Hospitalar"
    },
    {
      "code" : "05",
      "display" : "Atenção Psicossocial"
    },
    {
      "code" : "06",
      "display" : "Atenção à Urgência/Emergência"
    },
    {
      "code" : "07",
      "display" : "Ambulatorial Especializada"
    },
    {
      "code" : "08",
      "display" : "Assistência Farmacêutica"
    },
    {
      "code" : "09",
      "display" : "Assistência Ambulatorial"
    }
  ]
}

```
