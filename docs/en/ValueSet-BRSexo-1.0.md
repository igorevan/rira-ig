# Sexo - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Sexo 

 
Sexo de um indivíduo. 

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
  "id" : "BRSexo-1.0",
  "language" : "en",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRSexo-1.0",
  "version" : "1.0.0-release",
  "name" : "BRSexo",
  "title" : "Sexo",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-04-07T21:07:00.8812267+00:00",
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
  "description" : "Sexo de um indivíduo.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/administrative-gender",
      "concept" : [{
        "code" : "male",
        "display" : "Male",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Masculino"
        },
        {
          "language" : "es",
          "value" : "Masculino"
        }]
      },
      {
        "code" : "female",
        "display" : "Female",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Feminino"
        },
        {
          "language" : "es",
          "value" : "Femenino"
        }]
      },
      {
        "code" : "unknown",
        "display" : "Unknown",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Ignorado"
        },
        {
          "language" : "es",
          "value" : "Desconocido"
        }]
      }]
    }]
  }
}

```
