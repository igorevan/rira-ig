# Estado do Documento - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Estado do Documento 

 **References** 

* [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BREstadoDocumento-1.0",
  "language" : "en",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BREstadoDocumento-1.0",
  "version" : "1.0.0",
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
          "value" : "Documento atualizado e com versão válida"
        }]
      },
      {
        "code" : "entered-in-error",
        "display" : "Entered in error",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Documento registrado com erro ou cuja versão foi invalidada após sua substituição"
        }]
      }]
    }]
  }
}

```
