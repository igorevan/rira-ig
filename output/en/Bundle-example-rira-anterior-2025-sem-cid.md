# Bundle de exemplo do RIRA (Anterior à 2025 sem CID-10) - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Example Bundle: Bundle de exemplo do RIRA (Anterior à 2025 sem CID-10)



## Resource Content

```json
{
  "resourceType" : "Bundle",
  "id" : "example-rira-anterior-2025-sem-cid",
  "identifier" : {
    "system" : "http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-12345",
    "value" : "AMB_271831370_0701172"
  },
  "type" : "document",
  "timestamp" : "2024-11-18T12:14:01-03:00",
  "entry" : [{
    "fullUrl" : "urn:uuid:transient-0",
    "resource" : {
      "resourceType" : "Composition",
      "id" : "c1256970-5464-403d-99f9-f1ef1d1f81ea",
      "meta" : {
        "profile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRegulacaoAssistencial"]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><a name=\"Composition_c1256970-5464-403d-99f9-f1ef1d1f81ea\"> </a><p class=\"res-header-id\"><b>Narrativa gerada: Composition c1256970-5464-403d-99f9-f1ef1d1f81ea</b></p><a name=\"c1256970-5464-403d-99f9-f1ef1d1f81ea\"> </a><a name=\"hcc1256970-5464-403d-99f9-f1ef1d1f81ea\"> </a><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\"/><p style=\"margin-bottom: 0px\">Perfil: <a href=\"StructureDefinition-BRRegulacaoAssistencial.html\">Regulação Assistencial</a></p></div><p><b>status</b>: Final</p><p><b>type</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento RA}\">Regulação Assistencial</span></p><p><b>category</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial 04}\">Atenção Hospitalar</span></p><p><b>date</b>: 2024-11-18 12:14:01-0300</p><p><b>author</b>: Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0</code>/6450091</p><p><b>title</b>: Regulação Assistencial</p><blockquote><p><b>event</b></p><p><b>code</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial booked}\">Booked</span></p><p><b>period</b>: ?? --&gt; 2024-06-10 16:18:43-0300</p><p><b>detail</b>: </p><ul><li>Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0</code>/0440620</li><li><a href=\"Bundle-example-rira-anterior-2025-com-ciap.html#urn-uuid-transient-1\">Appointment: status = proposed; serviceCategory = Atenção Hospitalar; serviceType = COLONOSCOPIA (COLOSCOPIA); specialty = MEDICO CIRURGIAO GERAL; appointmentType = Routine; created = 2024-03-02 14:18:43-0300</a></li></ul></blockquote></div>"
      },
      "status" : "final",
      "type" : {
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento",
          "code" : "RA"
        }]
      },
      "category" : [{
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
          "code" : "04"
        }]
      }],
      "subject" : {
        "identifier" : {
          "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0",
          "value" : "708165325093340"
        }
      },
      "date" : "2024-11-18T12:14:01-03:00",
      "author" : [{
        "identifier" : {
          "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
          "value" : "6450091"
        }
      }],
      "title" : "Regulação Assistencial",
      "event" : [{
        "code" : [{
          "coding" : [{
            "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRStatusRegulacaoAssistencial",
            "code" : "booked"
          }]
        }],
        "period" : {
          "end" : "2024-06-10T16:18:43-03:00"
        },
        "detail" : [{
          "identifier" : {
            "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
            "value" : "0440620"
          }
        },
        {
          "reference" : "urn:uuid:transient-1"
        }]
      }],
      "section" : [{
        "entry" : [{
          "reference" : "urn:uuid:transient-1"
        }]
      }]
    }
  },
  {
    "fullUrl" : "urn:uuid:transient-1",
    "resource" : {
      "resourceType" : "Appointment",
      "meta" : {
        "profile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRAgendamentoRegulacaoAssistencial"]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><a name=\"Appointment_null\"> </a><p class=\"res-header-id\"><b>Narrativa gerada: Appointment </b></p><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\"/><p style=\"margin-bottom: 0px\">Perfil: <a href=\"StructureDefinition-BRAgendamentoRegulacaoAssistencial.html\">Agendamento de Regulação Assistencial</a></p></div><p><b>status</b>: Booked</p><p><b>serviceCategory</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial 04}\">Atenção Hospitalar</span></p><p><b>serviceType</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS 0209010029}\">COLONOSCOPIA (COLOSCOPIA)</span></p><p><b>specialty</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBO 225225}\">MEDICO CIRURGIAO GERAL</span></p><p><b>appointmentType</b>: <span title=\"Códigos:{http://hl7.org/fhir/request-priority routine}\">Routine</span></p><p><b>start</b>: 2024-09-25 09:00:00-0300</p><p><b>end</b>: 2024-09-25 09:30:00-0300</p><p><b>created</b>: 2024-03-02 14:18:43-0300</p><p><b>basedOn</b>: <a href=\"Bundle-example-rira-anterior-2025-com-ciap.html#urn-uuid-transient-2\">ServiceRequest COLONOSCOPIA (COLOSCOPIA)</a></p><h3>Participants</h3><table class=\"grid\"><tr><td style=\"display: none\">-</td><td><b>Type</b></td><td><b>Actor</b></td><td><b>Status</b></td></tr><tr><td style=\"display: none\">*</td><td><span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante PCT}\">Paciente</span></td><td>Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0</code>/708108612093340</td><td>Accepted</td></tr></table></div>"
      },
      "status" : "booked",
      "serviceCategory" : [{
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
          "code" : "04"
        }]
      }],
      "serviceType" : [{
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS",
          "code" : "0209010029"
        }]
      }],
      "specialty" : [{
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBO",
          "code" : "225225"
        }]
      }],
      "appointmentType" : {
        "coding" : [{
          "system" : "http://hl7.org/fhir/request-priority",
          "code" : "routine"
        }]
      },
      "start" : "2024-09-25T09:00:00-03:00",
      "end" : "2024-09-25T09:30:00.000-03:00",
      "created" : "2024-03-02T14:18:43-03:00",
      "basedOn" : [{
        "reference" : "urn:uuid:transient-2"
      }],
      "participant" : [{
        "type" : [{
          "coding" : [{
            "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoParticipante",
            "code" : "PCT"
          }]
        }],
        "actor" : {
          "identifier" : {
            "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0",
            "value" : "708108612093340"
          }
        },
        "status" : "accepted"
      }]
    }
  },
  {
    "fullUrl" : "urn:uuid:transient-2",
    "resource" : {
      "resourceType" : "ServiceRequest",
      "meta" : {
        "profile" : ["http://www.saude.gov.br/fhir/r4/StructureDefinition/BRRequisicaoRegulacaoAssistencial"]
      },
      "text" : {
        "status" : "generated",
        "div" : "<div xmlns=\"http://www.w3.org/1999/xhtml\"><a name=\"ServiceRequest_null\"> </a><p class=\"res-header-id\"><b>Narrativa gerada: ServiceRequest </b></p><div style=\"display: inline-block; background-color: #d9e0e7; padding: 6px; margin: 4px; border: 1px solid #8da1b4; border-radius: 5px; line-height: 60%\"><p style=\"margin-bottom: 0px\"/><p style=\"margin-bottom: 0px\">Perfil: <a href=\"StructureDefinition-BRRequisicaoRegulacaoAssistencial.html\">Requisição de Regulação Assistencial</a></p></div><p><b>status</b>: Active</p><p><b>intent</b>: Proposal</p><p><b>category</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial 04}\">Atenção Hospitalar</span></p><p><b>priority</b>: Routine</p><p><b>code</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS 0209010029}\">COLONOSCOPIA (COLOSCOPIA)</span></p><p><b>subject</b>: Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0</code>/708108612093340</p><p><b>authoredOn</b>: 2024-03-02 14:18:43-0300</p><p><b>requester</b>: Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0</code>/6994547</p><p><b>performerType</b>: <span title=\"Códigos:{http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBO 225225}\">MEDICO CIRURGIAO GERAL</span></p><p><b>performer</b>: Identifier: <code>http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0</code>/0440620</p></div>"
      },
      "status" : "active",
      "intent" : "proposal",
      "category" : [{
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial",
          "code" : "04"
        }]
      }],
      "priority" : "routine",
      "code" : {
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTabelaSUS",
          "code" : "0209010029"
        }]
      },
      "subject" : {
        "identifier" : {
          "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BRIndividuo-1.0",
          "value" : "708108612093340"
        }
      },
      "authoredOn" : "2024-03-02T14:18:43-03:00",
      "requester" : {
        "identifier" : {
          "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
          "value" : "6994547"
        }
      },
      "performerType" : {
        "coding" : [{
          "system" : "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCBO",
          "code" : "225225"
        }]
      },
      "performer" : [{
        "identifier" : {
          "system" : "http://www.saude.gov.br/fhir/r4/StructureDefinition/BREstabelecimentoSaude-1.0",
          "value" : "0440620"
        }
      }]
    }
  }]
}

```
