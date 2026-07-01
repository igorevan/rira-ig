# Estado do Documento - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Estado do Documento 

 
Classifica o estado do documento que está sendo trafegado. 

 **References** 

* [Regulação Assistencial (RIRA)](StructureDefinition-BRRegulacaoAssistencial.md)

### Logical Definition (CLD)

 

### Expansion

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BREstadoDocumento-1.0",
  "language" : "en",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoDocumento-1.0",
  "version" : "1.0.0-release",
  "name" : "BREstadoDocumento",
  "title" : "Estado do Documento",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-12T13:26:58.6069366+00:00",
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
  "description" : "Classifica o estado do documento que está sendo trafegado.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/composition-status",
      "concept" : [{
        "code" : "preliminary",
        "display" : "Preliminary",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Preliminar"
        }]
      },
      {
        "code" : "final",
        "display" : "Final",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Finalizado"
        }]
      },
      {
        "code" : "amended",
        "display" : "Amended",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Atualizado"
        }]
      },
      {
        "code" : "entered-in-error",
        "display" : "Entered in error",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Em estado de erro"
        }]
      }]
    }]
  }
}

```
