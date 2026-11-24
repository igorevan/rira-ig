# Categoria do Diagnóstico (CodeSystem) - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0

## CodeSystem: Categoria do Diagnóstico (CodeSystem) 

Este sistema de códigos é referenciado na definição dos seguintes conjuntos de valores:

* Este CodeSystem não é utilizado aqui; pode ser utilizado noutro local (por exemplo, em especificações e/ou implementações que utilizem este conteúdo)

-------

 [Descrição do(s) quadro(s) acima](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRCategoriaDiagnostico",
  "language" : "pt-BR",
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCategoriaDiagnostico",
  "version" : "1.0.0",
  "name" : "BRCategoriaDiagnostico",
  "title" : "Categoria do Diagnóstico (CodeSystem)",
  "status" : "active",
  "experimental" : false,
  "date" : "2022-05-19T11:00:40.0457007+00:00",
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
  "description" : "Códigos para representação do tipo de categoria do diagnóstico realizado.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [{
    "code" : "01",
    "display" : "Principal"
  },
  {
    "code" : "02",
    "display" : "Secundário"
  }]
}

```
