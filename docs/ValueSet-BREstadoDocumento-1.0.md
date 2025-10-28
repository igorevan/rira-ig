# Estado do Documento - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Estado do Documento**

## ValueSet: Estado do Documento 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoDocumento-1.0 | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BREstadoDocumento |

 
Classifica o estado do documento que está sendo trafegado. 

 **References** 

* [Regulação Assistencial (RIRA)](StructureDefinition-BRRegulacaoAssistencial.md)

### Logical Definition (CLD)

Última atualização: 2020-03-12 13:26:59+0000; Língua: en

* Include estes códigos, tal como definidos em [`http://hl7.org/fhir/composition-status`](http://tx.fhir.org/r4)versão 📍4.0.1

 

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
  "id" : "BREstadoDocumento-1.0",
  "meta" : {
    "lastUpdated" : "2020-03-12T13:26:59.318+00:00"
  },
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoDocumento-1.0",
  "version" : "1.0.0",
  "name" : "BREstadoDocumento",
  "title" : "Estado do Documento",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-12T13:26:58.6069366+00:00",
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
  "description" : "Classifica o estado do documento que está sendo trafegado.",
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
        "system" : "http://hl7.org/fhir/composition-status",
        "version" : "*",
        "concept" : [
          {
            "code" : "preliminary",
            "display" : "Preliminary",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Preliminar"
              }
            ]
          },
          {
            "code" : "final",
            "display" : "Final",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Finalizado"
              }
            ]
          },
          {
            "code" : "amended",
            "display" : "Amended",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Atualizado"
              }
            ]
          },
          {
            "code" : "entered-in-error",
            "display" : "Entered in error",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Em estado de erro"
              }
            ]
          }
        ]
      }
    ]
  }
}

```
