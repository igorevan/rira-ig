# Justificativa da Impossibilidade de Identificação do Indivíduo (CodeSystem) - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## CodeSystem: Justificativa da Impossibilidade de Identificação do Indivíduo (CodeSystem) 

 
Classifica as razões pelo qual não foi possível obter os dados de identificação do indivíduo em um contato assistencial. (Port. nº 84/SAS/MS/1997 e Port. nº02/SAS/SGEP/MS/2012) 

This Code system is referenced in the definition of the following value sets:

* [BRJustificativaIndividuoNaoIdentificado](ValueSet-BRJustificativaIndividuoNaoIdentificado-1.0.md)

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRJustificativaIndividuoNaoIdentificado",
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
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRJustificativaIndividuoNaoIdentificado",
  "version" : "1.0.0-release",
  "name" : "BRJustificativaIndividuoNaoIdentificado",
  "title" : "Justificativa da Impossibilidade de Identificação do Indivíduo (CodeSystem)",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-11T18:15:25.4061393+00:00",
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
  "description" : "Classifica as razões pelo qual não foi possível obter os dados de identificação do indivíduo em um contato assistencial. (Port. nº 84/SAS/MS/1997 e Port. nº02/SAS/SGEP/MS/2012)",
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
    "display" : "Indivíduo acidentado grave"
  },
  {
    "code" : "02",
    "display" : "Indivíduo em sofrimento mental encontrado em via pública"
  },
  {
    "code" : "03",
    "display" : "Indivíduo com problema neurológico grave ou comatoso"
  },
  {
    "code" : "04",
    "display" : "Indivíduo incapacitado por motivos sociais e/ou culturais"
  },
  {
    "code" : "05",
    "display" : "Indivíduo doador de órgãos falecido"
  },
  {
    "code" : "99",
    "display" : "Sem registro no modelo de informação de origem"
  }]
}

```
