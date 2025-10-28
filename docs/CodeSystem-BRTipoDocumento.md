# Tipo de Documento - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Tipo de Documento**

## CodeSystem: Tipo de Documento 

| | | |
| :--- | :--- | :--- |
| *Official URL*:http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento | *Version*:1.0.0 | |
| *Standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) | [Maturity Level](http://hl7.org/fhir/versions.html#maturity): 1 | *Computable Name*:BRTipoDocumento |

 
Classificação dos tipos de documentos compartilhados no Brasil. 

 This Code system is referenced in the content logical definition of the following value sets: 

* [BRTipoDocumento](ValueSet-BRTipoDocumento-1.0.md)

Língua: pt-BR

Este sistema de código define o seguinte código:



## Resource Content

```json
{
  "resourceType" : "CodeSystem",
  "id" : "BRTipoDocumento",
  "language" : "pt-BR",
  "extension" : [
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-fmm",
      "valueInteger" : 1,
      "_valueInteger" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
            "valueCanonical" : "http://www.saude.gov.br/fhir/r4/ImplementationGuide/br.gov.saude.rira.fhir"
          }
        ]
      }
    },
    {
      "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-standards-status",
      "valueCode" : "informative",
      "_valueCode" : {
        "extension" : [
          {
            "url" : "http://hl7.org/fhir/StructureDefinition/structuredefinition-conformance-derivedFrom",
            "valueCanonical" : "http://www.saude.gov.br/fhir/r4/ImplementationGuide/br.gov.saude.rira.fhir"
          }
        ]
      }
    }
  ],
  "url" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento",
  "version" : "1.0.0",
  "name" : "BRTipoDocumento",
  "title" : "Tipo de Documento",
  "status" : "active",
  "experimental" : false,
  "date" : "2020-03-26T13:19:46.9743559+00:00",
  "publisher" : "Ministério da Saúde do Brasil",
  "contact" : [
    {
      "name" : "Ministério da Saúde do Brasil",
      "telecom" : [
        {
          "system" : "url",
          "value" : "http://www.saude.gov.br"
        }
      ]
    }
  ],
  "description" : "Classificação dos tipos de documentos compartilhados no Brasil.",
  "jurisdiction" : [
    {
      "coding" : [
        {
          "system" : "urn:iso:std:iso:3166",
          "code" : "BR"
        }
      ]
    }
  ],
  "caseSensitive" : true,
  "content" : "complete",
  "concept" : [
    {
      "code" : "CMD",
      "display" : "Conjunto Mínimo de Dados",
      "definition" : "Documento público que coleta os dados mínimos dos atendimentos em saúde realizados em qualquer estabelecimento de saúde do país, público ou privado, em cada contato assistencial."
    },
    {
      "code" : "SA",
      "display" : "Sumário de Alta",
      "definition" : "Relato clínico objetivo sobre as intervenções realizadas, as instruções para continuidade do cuidado pós-alta e o estado de saúde do indivíduo ao final de sua permanência na internação em estabelecimentos de saúde como: hospital, clínica, hospital-dia, internação domiciliar e urgência."
    },
    {
      "code" : "RAC",
      "display" : "Registro de Atendimento Clínico",
      "definition" : "Registro de dados essenciais de uma consulta realizada a um indivíduo no âmbito da atenção básica, especializada ou domiciliar (atendimento diário)."
    },
    {
      "code" : "RIA",
      "display" : "Registro de Imunobiológico Administrado"
    },
    {
      "code" : "RPM",
      "display" : "Registro de Prescrição de Medicamento"
    },
    {
      "code" : "RDM",
      "display" : "Registro de Dispensação de Medicamento"
    },
    {
      "code" : "REL",
      "display" : "Resultado de Exame(s) Laboratoriais(s)"
    },
    {
      "code" : "RA",
      "display" : "Regulação Assistencial"
    },
    {
      "code" : "ATM",
      "display" : "Atestado Médico/Odontológico"
    },
    {
      "code" : "REPM",
      "display" : "Registro Eletrônico da Prescrição de Medicamento"
    },
    {
      "code" : "REDFM",
      "display" : "Registro Eletrônico de Dispensação ou Fornecimento de Medicamentos"
    }
  ]
}

```
