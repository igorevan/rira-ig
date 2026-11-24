# Tipo de Documento (ValueSet) - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Tipo de Documento (ValueSet) 

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
  "id" : "BRTipoDocumento-1.0",
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRTipoDocumento-1.0",
  "version" : "1.0.0",
  "name" : "BRTipoDocumento",
  "title" : "Tipo de Documento (ValueSet)",
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
  "description" : "Classifica o tipo de documento que está sendo trafegado.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento"
    }]
  }
}

```
