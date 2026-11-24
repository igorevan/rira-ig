# Classificação de uma condição - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Classificação de uma condição 

 **References** 

* [Problema/Diagnóstico](StructureDefinition-BRProblemaDiagnostico.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRCategoriaCondicao",
  "meta" : {
    "lastUpdated" : "2020-03-11T19:14:51.806+00:00"
  },
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRCategoriaCondicao",
  "version" : "1.0.0",
  "name" : "BRCategoriaCondicao",
  "title" : "Classificação de uma condição",
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
  "description" : "Tradução para o português do brasil da classificação de uma condição",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://terminology.hl7.org/CodeSystem/condition-category",
      "concept" : [{
        "code" : "problem-list-item",
        "display" : "Problem List Item",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Problema listado"
        }]
      },
      {
        "code" : "encounter-diagnosis",
        "display" : "Encounter Diagnosis",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Diagnóstico"
        }]
      }]
    }]
  }
}

```
