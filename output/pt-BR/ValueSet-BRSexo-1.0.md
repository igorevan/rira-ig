# Sexo - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Sexo 

 **References** 

* [Informações Complementares de Indivíduos Não Identificados](StructureDefinition-BRIndividuoNaoIdentificado-1.0.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRSexo-1.0",
  "language" : "en",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRSexo-1.0",
  "version" : "1.0.0",
  "name" : "BRSexo",
  "title" : "Sexo",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-04-07T21:07:00.8812267+00:00",
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
  "description" : "Sexo de um indivíduo.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/administrative-gender",
      "concept" : [{
        "code" : "male",
        "display" : "Male",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Masculino"
        },
        {
          "language" : "es",
          "value" : "Masculino"
        }]
      },
      {
        "code" : "female",
        "display" : "Female",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Feminino"
        },
        {
          "language" : "es",
          "value" : "Femenino"
        }]
      },
      {
        "code" : "unknown",
        "display" : "Unknown",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Ignorado"
        },
        {
          "language" : "es",
          "value" : "Desconocido"
        }]
      }]
    }]
  }
}

```
