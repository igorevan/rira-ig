# Classificação Internacional de Doenças - Décima Revisão - CID-10 - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Classificação Internacional de Doenças - Décima Revisão - CID-10**

## ValueSet: Classificação Internacional de Doenças - Décima Revisão - CID-10 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/ValueSet/BRCID10-1.0 | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRCID10 |

 
Classificação Internacional de Doenças - Décima Revisão - CID-10 

 **References** 

* [CID10 Avaliado](StructureDefinition-BRCID10Avaliado-1.0.md)

### Logical Definition (CLD)

Última atualização: 2020-03-11 19:14:51+0000; Língua: pt-BR

* Include todos os códigos definidos em `http://www.saude.gov.br/fhir/r4/CodeSystem/BRCID10`versão 📍

 

### Expansion

Expansão a partir de tx.fhir.org com base em [codesystem Classificação Internacional de Doenças - Décima Revisão (CID-10) v1.0.0 (CodeSystem)](CodeSystem-BRCID10.md)

Este conjunto de valores contém mais de 1000 códigos. A fim de manter o tamanho da publicação gerível, é apresentada apenas uma seleção (1000 códigos) de todo o conjunto de códigos

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
  "id" : "BRCID10-1.0",
  "meta" : {
    "lastUpdated" : "2020-03-11T19:14:51.806+00:00"
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRCID10-1.0",
  "version" : "1.0.0",
  "name" : "BRCID10",
  "title" : "Classificação Internacional de Doenças - Décima Revisão - CID-10",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-11T19:15:12.2909517+00:00",
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
  "description" : "Classificação Internacional de Doenças - Décima Revisão - CID-10",
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
        "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCID10",
        "version" : "*"
      }
    ]
  }
}

```
