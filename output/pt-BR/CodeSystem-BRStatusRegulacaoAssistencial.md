# Status da regulação assistencial - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## CodeSystem: Status da regulação assistencial 

Este sistema de códigos é referenciado na definição dos seguintes conjuntos de valores:

* [Status de regulação assistencial](ValueSet-BRStatusRegulacaoAssistencial.md)

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRStatusRegulacaoAssistencial",
  "language" : "en",
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial",
  "version" : "1.0.0",
  "name" : "BRStatusRegulacaoAssistencial",
  "title" : "Status da regulação assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-26T13:19:46.9743559+00:00",
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
  "description" : "Status da regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "pending",
    "display" : "Pending",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Pendente"
    }]
  },
  {
    "code" : "booked",
    "display" : "Booked",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Agendado"
    }]
  },
  {
    "code" : "attended",
    "display" : "Attended/Hospitalized",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Atendido/Internado"
    }]
  },
  {
    "code" : "cancelled",
    "display" : "Cancelled",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Negado/Cancelado"
    }]
  },
  {
    "code" : "absence",
    "display" : "Absence",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Falta"
    }]
  },
  {
    "code" : "excluded",
    "display" : "Excluded",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Excluído"
    }]
  },
  {
    "code" : "returned-to-requester",
    "display" : "Returned to requester.",
    "designation" : [{
      "language" : "pt-BR",
      "value" : "Devolvido para o solicitante."
    }]
  }]
}

```
