# Status de regulação assistencial - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Status de regulação assistencial 

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
  "id" : "BRStatusRegulacaoAssistencial",
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusRegulacaoAssistencial",
  "version" : "1.0.0",
  "name" : "BRStatusRegulacaoAssistencial",
  "title" : "Status de regulação assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-04-13T13:17:18.5012669+00:00",
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
  "description" : "Status de agendamento de regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial"
    }]
  }
}

```
