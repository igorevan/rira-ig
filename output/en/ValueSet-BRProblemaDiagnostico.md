# Classificação Internacional de Doenças e Atenção Primária - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Classificação Internacional de Doenças e Atenção Primária 

 
Código Internacional de Atenção Primária (CIAP2) e Classificação Internacional de Doenças (CID10) 

 **References** 

* [Problema/Diagnóstico](StructureDefinition-BRProblemaDiagnostico.md)

### Logical Definition (CLD)

 

### Expansion

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRProblemaDiagnostico",
  "meta" : {
    "lastUpdated" : "2020-03-11T19:14:51.806+00:00"
  },
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
        "valueCanonical" : "http://fhir.saude.gov.br/rira/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "normative",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "http://fhir.saude.gov.br/rira/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-normative-version",
    "valueCode" : "4.0.1"
  }],
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRProblemaDiagnostico",
  "version" : "1.0.0-release",
  "name" : "BRProblemaDiagnostico",
  "title" : "Classificação Internacional de Doenças e Atenção Primária",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-11T19:15:12.2909517+00:00",
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
  "description" : "Código Internacional de Atenção Primária (CIAP2) e Classificação Internacional de Doenças (CID10)",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCID10"
    },
    {
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCIAP2"
    }]
  }
}

```
