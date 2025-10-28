# Estado da Resolução de Diagnóstico ou Problema - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Estado da Resolução de Diagnóstico ou Problema**

## ValueSet: Estado da Resolução de Diagnóstico ou Problema 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoResolucaoDiagnosticoProblema-1.0 | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BREstadoResolucaoDiagnosticoProblema |

 
Estado da resolução de um diagnóstico ou problema. 

 **References** 

* [CID10 Avaliado](StructureDefinition-BRCID10Avaliado-1.0.md)

### Logical Definition (CLD)

Última atualização: 2020-03-12 13:09:54+0000; Língua: en

* Include estes códigos, tal como definidos em [`http://terminology.hl7.org/CodeSystem/condition-clinical`](http://tx.fhir.org/r4)versão 📍4.0.1

 

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
  "id" : "BREstadoResolucaoDiagnosticoProblema-1.0",
  "meta" : {
    "lastUpdated" : "2020-03-12T13:09:54.402+00:00"
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoResolucaoDiagnosticoProblema-1.0",
  "version" : "1.0.0",
  "name" : "BREstadoResolucaoDiagnosticoProblema",
  "title" : "Estado da Resolução de Diagnóstico ou Problema",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-12T13:09:53.3447193+00:00",
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
  "description" : "Estado da resolução de um diagnóstico ou problema.",
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
        "system" : "http://terminology.hl7.org/CodeSystem/condition-clinical",
        "version" : "*",
        "concept" : [
          {
            "code" : "active",
            "display" : "Active",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Ativo"
              }
            ]
          },
          {
            "code" : "recurrence",
            "display" : "Recurrence",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Recorrente"
              }
            ]
          },
          {
            "code" : "relapse",
            "display" : "Relapse",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Recidiva"
              }
            ]
          },
          {
            "code" : "inactive",
            "display" : "Inactive",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Inativo"
              }
            ]
          },
          {
            "code" : "remission",
            "display" : "Remission",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Remissão"
              }
            ]
          },
          {
            "code" : "resolved",
            "display" : "Resolved",
            "designation" : [
              {
                "language" : "pt-BR",
                "value" : "Resolvido"
              }
            ]
          }
        ]
      }
    ]
  }
}

```
