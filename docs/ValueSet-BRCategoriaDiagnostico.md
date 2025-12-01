# Categoria do Diagnóstico - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Categoria do Diagnóstico**

## ValueSet: Categoria do Diagnóstico 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BRCategoriaDiagnostico | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRCategoriaDiagnostico |

 
ValueSet utilizado para definir o tipo de categoria do diagnóstico realizado. 

 **References** 

* [CID10 Avaliado](StructureDefinition-BRCID10Avaliado-1.0.md)

### Logical Definition (CLD)

Última atualização: 2022-05-19 11:10:40+0000; Língua: pt-BR

* Include todos os códigos definidos em `http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico`versão 📍

 

### Expansion

Expansão a partir de tx.fhir.org com base em [codesystem Categoria do Diagnóstico v1.0.0 (CodeSystem)](CodeSystem-BRCategoriaDiagnostico.md)

Este conjunto de valores contém 2 conceitos

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
  "id" : "BRCategoriaDiagnostico",
  "meta" : {
    "lastUpdated" : "2022-05-19T11:10:40.0457007+00:00"
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRCategoriaDiagnostico",
  "version" : "1.0.0",
  "name" : "BRCategoriaDiagnostico",
  "title" : "Categoria do Diagnóstico",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-05-19T11:10:40.0457007+00:00",
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
  "description" : "ValueSet utilizado para definir o tipo de categoria do diagnóstico realizado.",
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
        "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico",
        "version" : "*"
      }
    ]
  }
}

```
