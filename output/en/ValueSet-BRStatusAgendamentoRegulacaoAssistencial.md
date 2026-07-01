# Status de agendamento de regulação assistencial (ValueSet) - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## ValueSet: Status de agendamento de regulação assistencial (ValueSet) 

 
Status de agendamento de regulação assistencial. 

 **References** 

* [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)

### Logical Definition (CLD)

 

### Expansion

-------

 [Description of the above table(s)](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#terminology). 



## Resource Content

```json
{
  "resourceType" : "ValueSet",
  "id" : "BRStatusAgendamentoRegulacaoAssistencial",
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
  "url" : "http://www.saude.gov.br/fhir/r4/ValueSet/BRStatusAgendamentoRegulacaoAssistencial",
  "version" : "1.0.0-release",
  "name" : "BRStatusAgendamentoRegulacaoAssistencial",
  "title" : "Status de agendamento de regulação assistencial (ValueSet)",
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
  "description" : "Status de agendamento de regulação assistencial.",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "BR"
    }]
  }],
  "immutable" : false,
  "compose" : {
    "include" : [{
      "system" : "http://hl7.org/fhir/appointmentstatus",
      "concept" : [{
        "code" : "proposed",
        "display" : "Proposed",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Solicitado"
        }]
      },
      {
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
        "code" : "arrived",
        "display" : "Arrived",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Recebido"
        }]
      },
      {
        "code" : "fulfilled",
        "display" : "Fulfilled",
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
        "code" : "noshow",
        "display" : "No Show",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Falta"
        }]
      },
      {
        "code" : "entered-in-error",
        "display" : "Entered in error",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Em estado de erro"
        }]
      },
      {
        "code" : "checked-in",
        "display" : "Checked in",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Confirmado"
        }]
      },
      {
        "code" : "waitlist",
        "display" : "Waitlisted",
        "designation" : [{
          "language" : "pt-BR",
          "value" : "Em espera"
        }]
      }]
    },
    {
      "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusAgendamentoRegulacaoAssistencial"
    }]
  }
}

```
