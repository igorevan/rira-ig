# Caráter de Atendimento no MIRA - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Caráter de Atendimento no MIRA 

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
  "id" : "BRCaraterAtendimentoMIRA",
  "language" : "en",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRCaraterAtendimentoMIRA",
  "version" : "1.0.0",
  "name" : "BRCaraterAtendimentoMIRA",
  "title" : "Caráter de Atendimento no MIRA",
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
  "description" : "Caráter da solicitação do procedimento.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/request-priority",
      "concept" : [{
        "code" : "routine",
        "display" : "Routine",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Eletivo"
        }]
      },
      {
        "code" : "urgent",
        "display" : "Urgent",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Urgência"
        }]
      }]
    }]
  }
}

```
