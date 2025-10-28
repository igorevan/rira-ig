# Intenção de requisição de regulação assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Intenção de requisição de regulação assistencial**

## ValueSet: Intenção de requisição de regulação assistencial 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BRIntencaoRegulacao | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRIntencaoRegulacao |

 
Intenção de requisição de regulação assistencial. 

 **References** 

* [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)

### Logical Definition (CLD)

Língua: en

* Include estes códigos, tal como definidos em [`http://hl7.org/fhir/request-intent`](http://tx.fhir.org/r4)versão 📍4.0.1

 

### Expansion

No Expansion for this valueset (Unsupported Code System Version)

-------

 Explanation of the columns that may appear on this page: 

| | |
| :--- | :--- |
| Level | A few code lists that FHIR defines are hierarchical - each code is assigned a level. In this scheme, some codes are under other codes, and imply that the code they are under also applies |
| System | The source of the definition of the code (when the value set draws in codes defined elsewhere) |
| Code | The code (used as the code in the resource instance) |
| Display | The display (used in the*display*element of a[Coding](http://hl7.org/fhir/R4/datatypes.html#Coding)). If there is no display, implementers should not simply display the code, but map the concept into their application |
| Definition | An explanation of the meaning of the concept |
| Comments | Additional notes about how to use the code |



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRIntencaoRegulacao",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRIntencaoRegulacao",
  "version" : "1.0.0",
  "name" : "BRIntencaoRegulacao",
  "title" : "Intenção de requisição de regulação assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-04-13T13:17:18.5012669+00:00",
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
  "description" : "Intenção de requisição de regulação assistencial.",
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
  "immutable" : false,
  "compose" : {
    "include" : [
      {
        "system" : "http://hl7.org/fhir/request-intent",
        "version" : "*",
        "concept" : [
          {
            "code" : "proposal",
            "display" : "Proposal",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Proposto"
              }
            ]
          },
          {
            "code" : "plan",
            "display" : "Plan",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Planejado"
              }
            ]
          },
          {
            "code" : "directive",
            "display" : "Directive",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Diretriz"
              }
            ]
          },
          {
            "code" : "order",
            "display" : "Order",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Autorizado"
              }
            ]
          },
          {
            "code" : "original-order",
            "display" : "Original Order",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Autorização original"
              }
            ]
          },
          {
            "code" : "reflex-order",
            "display" : "Reflex Order",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Autorização suplementar"
              }
            ]
          },
          {
            "code" : "filler-order",
            "display" : "Filler Order",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Intenção de autorização"
              }
            ]
          },
          {
            "code" : "instance-order",
            "display" : "Instance Order",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Autorização de atividade única"
              }
            ]
          },
          {
            "code" : "option",
            "display" : "Option",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Condicional"
              }
            ]
          }
        ]
      }
    ]
  }
}

```
