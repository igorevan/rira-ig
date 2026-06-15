# Categoria do Diagnóstico (CodeSystem) - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## CodeSystem: Categoria do Diagnóstico (CodeSystem) 

 
Códigos para representação do tipo de categoria do diagnóstico realizado. 

This Code system is referenced in the definition of the following value sets:

* [BRCategoriaDiagnostico](ValueSet-BRCategoriaDiagnostico.md)

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRCategoriaDiagnostico",
  "language" : "pt-BR",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-wg",
    "valueCode" : "ehr"
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 1,
    "_valueInteger" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "normative",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-normative-version",
    "valueCode" : "4.0.1"
  }],
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico",
  "version" : "1.0.0-release",
  "name" : "BRCategoriaDiagnostico",
  "title" : "Categoria do Diagnóstico (CodeSystem)",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-05-19T11:00:40.0457007+00:00",
  "publisher" : "Ministério da Saúde do Brasil",
  "contact" : [{
    "name" : "Ministério da Saúde do Brasil",
    "telecom" : [{
      "system" : "url",
      "value" : "http://www.saude.gov.br"
    },
    {
      "system" : "email",
      "value" : "cgiis.datasus@saude.gov.br"
    }]
  }],
  "description" : "Códigos para representação do tipo de categoria do diagnóstico realizado.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "01",
    "display" : "Principal"
  },
  {
    "code" : "02",
    "display" : "Secundário"
  }]
}

```
