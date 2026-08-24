# Modalidade Assistencial - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## CodeSystem: Modalidade Assistencial 

 
Classifica os contatos assistenciais de acordo com as especificidades do modo, local e duração do atendimento 

This Code system is referenced in the definition of the following value sets:

* [Modalidade Assistencial MIRA](ValueSet-BRModalidadeAssistencialMIRA.md)

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRModalidadeAssistencial",
  "language" : "pt-BR",
  "extension" : [{
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-wg",
    "valueCode" : "ehr"
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
    "valueInteger" : 1,
    "_valueInteger" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
    "valueCode" : "normative",
    "_valueCode" : {
      "extension" : [{
        "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
        "valueCanonical" : "https://fhir.saude.gov.br/fhir/r4/rira/1.0.0/ImplementationGuide/br.gov.saude.rira.fhir"
      }]
    }
  },
  {
    "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-normative-version",
    "valueCode" : "4.0.1"
  }],
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRModalidadeAssistencial",
  "title" : "Modalidade Assistencial",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-11T18:16:19.9468275+00:00",
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
  "description" : "Classifica os contatos assistenciais de acordo com as especificidades do modo, local e duração do atendimento",
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
    "display" : "Atenção Básica"
  },
  {
    "code" : "02",
    "display" : "Atenção Domiciliar"
  },
  {
    "code" : "03",
    "display" : "Atenção Intermediária"
  },
  {
    "code" : "04",
    "display" : "Atenção Hospitalar"
  },
  {
    "code" : "05",
    "display" : "Atenção Psicossocial"
  },
  {
    "code" : "06",
    "display" : "Atenção à Urgência/Emergência"
  },
  {
    "code" : "07",
    "display" : "Ambulatorial Especializada"
  },
  {
    "code" : "08",
    "display" : "Assistência Farmacêutica"
  },
  {
    "code" : "09",
    "display" : "Assistência Ambulatorial"
  }]
}

```
