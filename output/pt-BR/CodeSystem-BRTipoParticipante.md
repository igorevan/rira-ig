# Tipo do Participante - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## CodeSystem: Tipo do Participante 

Este sistema de códigos é referenciado na definição dos seguintes conjuntos de valores:

* [Tipo Participante](ValueSet-BRTipoParticipante.md)

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRTipoParticipante",
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante",
  "version" : "1.0.0",
  "name" : "BRTipoParticipante",
  "title" : "Tipo do Participante",
  "status" : "active",
  "experimental" : false,
  "date" : "2023-04-13T18:16:19.9468275+00:00",
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
  "description" : "Identificação do tipo do participante envolvido na solicitação.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "PCT",
    "display" : "Paciente"
  },
  {
    "code" : "ESS",
    "display" : "Estabelecimento de saúde solicitante"
  },
  {
    "code" : "ESE",
    "display" : "Estabelecimento de saúde executante"
  },
  {
    "code" : "ESR",
    "display" : "Estabelecimento de saúde regulador"
  }]
}

```
