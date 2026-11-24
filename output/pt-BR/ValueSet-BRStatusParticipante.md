# Status do Participante do agendamento - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## ValueSet: Status do Participante do agendamento 

 **References** 

* [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)

### Definição lógica (CLD)

 

### Expansão

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRStatusParticipante",
  "language" : "en",
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusParticipante",
  "version" : "1.0.0",
  "name" : "BRStatusParticipante",
  "title" : "Status do Participante do agendamento",
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
  "description" : "Status do Participante do agendamento.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/participationstatus",
      "concept" : [{
        "code" : "accepted",
        "display" : "Accepted",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Aceito"
        }]
      },
      {
        "code" : "declined",
        "display" : "Declined",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Negado"
        }]
      },
      {
        "code" : "tentative",
        "display" : "Tentative",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Tentativa"
        }]
      },
      {
        "code" : "needs-action",
        "display" : "Needs Action",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Aguardando resposta"
        }]
      }]
    }]
  }
}

```
