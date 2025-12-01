# Categoria do Diagnóstico - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Categoria do Diagnóstico**

## CodeSystem: Categoria do Diagnóstico 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRCategoriaDiagnostico |

 
Códigos para representação do tipo de categoria do diagnóstico realizado. 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRCategoriaDiagnostico](ValueSet-BRCategoriaDiagnostico.md)

Língua: pt-BR

Este case-sensitive sistema de código `http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico` define o seguinte códigos:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRCategoriaDiagnostico",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico",
  "version" : "1.0.0",
  "name" : "BRCategoriaDiagnostico",
  "title" : "Categoria do Diagnóstico",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-05-19T11:00:40.0457007+00:00",
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
  "description" : "Códigos para representação do tipo de categoria do diagnóstico realizado.",
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
      "display" : "Principal"
    },
    {
      "code" : "02",
      "display" : "Secundário"
    }
  ]
}

```
