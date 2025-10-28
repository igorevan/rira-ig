# Procedimento realizado - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Procedimento realizado**

## ValueSet: Procedimento realizado 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BRProcedimentosNacionais-1.0 | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRProcedimentosNacionais |

 
ValueSet das classificações brasileiras para procedimentos adotadas em contexto nacional, os CodeSystems apresentam os códigos da competência atual, para o envio de competência anterior os códigos devem ser consultados na RTS. 

 **References** 

* [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)
* [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)

### Logical Definition (CLD)

Última atualização: 2020-04-07 18:23:28+0000; Língua: pt-BR

Este conjunto de valores inclui códigos baseados nas seguintes regras:

* Incluir todos os códigos definidos em `http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBHPMTUSS`versão 📍
* Incluir todos os códigos definidos em `http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS`versão 📍

 

### Expansion

No Expansion for this valueset (Unknown Code System)

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
  "id" : "BRProcedimentosNacionais-1.0",
  "meta" : {
    "lastUpdated" : "2020-04-07T18:23:28.563+00:00"
  },
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRProcedimentosNacionais-1.0",
  "version" : "1.0.0",
  "name" : "BRProcedimentosNacionais",
  "title" : "Procedimento realizado",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-04-07T18:23:26.5540616+00:00",
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
  "description" : "ValueSet das classificações brasileiras para procedimentos adotadas em contexto nacional, os CodeSystems apresentam os códigos da competência atual, para o envio de competência anterior os códigos devem ser consultados na RTS.",
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
        "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBHPMTUSS",
        "version" : "*"
      },
      {
        "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS",
        "version" : "*"
      }
    ]
  }
}

```
