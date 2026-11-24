# Modalidade Assistencial MIRA - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Modalidade Assistencial MIRA 

 **References** 

* [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)
* [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)
* [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRModalidadeAssistencialMIRA",
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRModalidadeAssistencialMIRA",
  "version" : "1.0.0",
  "name" : "BRModalidadeAssistencialMIRA",
  "title" : "Modalidade Assistencial MIRA",
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
  "description" : "Modalidade assistencial que gerou a solicitação do procedimento.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
      "concept" : [{
        "code" : "04"
      },
      {
        "code" : "09"
      }]
    }]
  }
}

```
