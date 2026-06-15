# Justificativa da Impossibilidade de Identificação do Indivíduo (ValueSet) - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Justificativa da Impossibilidade de Identificação do Indivíduo (ValueSet) 

 
Classifica as razões pelo qual não foi possível obter os dados de identificação do indivíduo em um contato assistencial. (Port. nº 84/SAS/MS/1997 e Port. nº02/SAS/SGEP/MS/2012) 

 **References** 

* [Informações Complementares de Indivíduos Não Identificados](StructureDefinition-BRIndividuoNaoIdentificado-1.0.md)

### Logical Definition (CLD)

 

### Expansion

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRJustificativaIndividuoNaoIdentificado-1.0",
  "meta" : {
    "lastUpdated" : "2020-04-07T20:51:20.256+00:00"
  },
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRJustificativaIndividuoNaoIdentificado-1.0",
  "version" : "1.0.0-release",
  "name" : "BRJustificativaIndividuoNaoIdentificado",
  "title" : "Justificativa da Impossibilidade de Identificação do Indivíduo (ValueSet)",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-04-07T20:51:17.5349531+00:00",
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
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRJustificativaIndividuoNaoIdentificado"
    }]
  }
}

```
