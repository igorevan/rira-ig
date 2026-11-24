# Procedimento realizado - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Procedimento realizado 

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
  "id" : "BRProcedimentosNacionais-1.0",
  "meta" : {
    "lastUpdated" : "2020-04-07T18:23:28.563+00:00"
  },
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRProcedimentosNacionais-1.0",
  "version" : "1.0.0",
  "name" : "BRProcedimentosNacionais",
  "title" : "Procedimento realizado",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-04-07T18:23:26.5540616+00:00",
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
  "description" : "ValueSet das classificações brasileiras para procedimentos adotadas em contexto nacional, os CodeSystems apresentam os códigos da competência atual, para o envio de competência anterior os códigos devem ser consultados na RTS.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBHPMTUSS"
    },
    {
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS"
    }]
  }
}

```
