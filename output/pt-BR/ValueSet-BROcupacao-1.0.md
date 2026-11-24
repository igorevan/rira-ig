# Classificação Brasileira de Ocupações - CBO - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Classificação Brasileira de Ocupações - CBO 

 **References** 

* [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)
* [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BROcupacao-1.0",
  "meta" : {
    "lastUpdated" : "2020-03-12T13:22:07.223+00:00"
  },
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BROcupacao-1.0",
  "version" : "1.0.0",
  "name" : "BROcupacao",
  "title" : "Classificação Brasileira de Ocupações - CBO",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-12T13:22:05.8261152+00:00",
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
  "description" : "Classifica as profissões do mercado de trabalho brasileiro.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBO"
    }]
  }
}

```
