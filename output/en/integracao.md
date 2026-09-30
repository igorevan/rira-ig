# Integração - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Integração

### Integração com a RNDS

 Para garantir a interoperabilidade entre as aplicações de Saúde Digital, em especial Prontuário(s) Eletrônico(s) do Paciente (PEP), portais e aplicações (*web e mobile*), a troca de informações ocorre por meio de serviços (*web services*) RESTful, desenvolvidos de acordo com o padrão [FHIR R4](https://hl7.org/FHIR/). 

### Segurança

 Somente com uma solicitação de acesso aprovada será possível realizar o consumo dos serviços (*web services*) do *EHR Services*. 

 Após a aprovação, o primeiro passo para realizar o consumo dos serviços é realizar a autenticação utilizando o serviço `GET [base]/token` no serviço *EHR Auth*. Durante o processo de autenticação é verificado se o certificado digital está dentro do período de vigência e se ele, ou um de seus superiores na cadeia, foi revogado. 

 Caso não ocorra nenhum destes problemas, a operação de autenticação será realizada com sucesso e será retornado um *token* (`access_token`) com tempo de vida de 30 minutos. Este *token* deverá ser utilizado como token de autenticação nas chamadas dos serviços (*web services*) do *EHR Services*. A estrutura do *token* retornado é a seguinte: 

```
{
      "access_token": "eyJraWQiOiJybmRzIGF...",
      "scope": "read write",
      "token_type": "jwt",
      "expires_in": 1800000
}
```

A autenticação com certificado digital da RNDS utiliza a técnica chamada “*Two-way SSL*”. No “*Two-way SSL*”, além do certificado do servidor, o cliente também deve utilizar um certificado válido e que será conferido. Por outro lado, na autenticação SSL (ou “*One-way SSL*”) somente o certificado digital do servidor deve ser válido e será conferido. 

 Vale ressaltar que o certificado digital deve ser usado somente para realizar a autenticação e obter o *token*. 

A partir desse momento, o token é seu "*ticket*" de passe e todas as chamadas devem ser usadas utilizando somente este, não gerando a degradação de performance relacionada ao uso do certificado digital. Por isso, recomenda-se reutilizar o "*ticket*" ao máximo durante seu tempo de vida e só então obter um novo token repetindo a operação de autenticação com “*Two-way SSL*”.

### Ambientes de Interoperabilidade

Seguindo as boas práticas serão disponibilizados dois ambientes para a interoperabilidade: homologação e produção.

#### Ambiente de Homologação

O ambiente de homologação tem como finalidade validar a interoperabilidade, seus parâmetros de entradas, saídas e comportamentos negociais, permitindo a realização de testes antes da efetiva comunicação com o ambiente de produção. O ambiente de homologação é único, ou seja, todos os interessados em realizar o consumo dos serviços (*web services*) utilizarão o mesmo ambiente. Porém, mesmo usando o mesmo ambiente, as informações trafegadas (incluídas ou consultadas) estarão restritas aos estabelecimentos de saúde (CNES) elencados na etapa de credenciamento. Os endereços dos componentes de integração, no ambiente de homologação, são:

* Utilizado para obtenção do *token* em ambiente de homologação:
*  Utilizado para comunicação com demais serviços do ambiente de homologação: 

#### Evidências da Homologação

Após a execução dos testes de integração e da implementação local, o integrador deve gerar um pacote de evidências contendo:

* 1 print do validador local demonstrando sucesso na validação
* 1 print do *header* de resposta de criação do registro na RNDS
* 1 print do *Bundle* enviado durante o processo

Com essas evidências, o integrador poderá solicitar acesso ao ambiente de produção diretamente pelo [Portal de Serviços](https://servicos-datasus.saude.gov.br/).

### Ambiente de Produção

O ambiente de produção é o ambiente estável e real que provê os serviços (*web services*) a serem consumidos. Para o ambiente produtivo, os integradores deverão acessar os endereços dos seus estados (UF). Durante o credenciamento, a credencial de acesso (Certificado Digital) será associada a um estabelecimento de saúde (CNES ou conjunto de estabelecimentos de saúde) no Portal de Serviços do DATASUS. Com isso, a credencial de acesso pertencerá a um estado (UF) específico. Acessos a estados diferentes não são permitidos e serão bloqueados automaticamente pelos serviços (*web services*). Os endereços dos componentes de integração, no ambiente de produção, por estado, são:

* Endpoint para autenticação (comum a todos as UFs):

| | |
| :--- | :--- |
| Acre | `https://ac-ehr-services.saude.gov.br/api/` |
| Alagoas | `https://al-ehr-services.saude.gov.br/api/` |
| Amapá | `https://ap-ehr-services.saude.gov.br/api/` |
| Amazonas | `https://am-ehr-services.saude.gov.br/api/` |
| Bahia | `https://ba-ehr-services.saude.gov.br/api/` |
| Ceará | `https://ce-ehr-services.saude.gov.br/api/` |
| Distrito Federal | `https://df-ehr-services.saude.gov.br/api/` |
| Espírito Santo | `https://es-ehr-services.saude.gov.br/api/` |
| Goiás | `https://go-ehr-services.saude.gov.br/api/` |
| Maranhão | `https://ma-ehr-services.saude.gov.br/api/` |
| Mato Grosso | `https://mt-ehr-services.saude.gov.br/api/` |
| Mato Grosso do Sul | `https://ms-ehr-services.saude.gov.br/api/` |
| Minas Gerais | `https://mg-ehr-services.saude.gov.br/api/` |
| Pará | `https://pa-ehr-services.saude.gov.br/api/` |
| Paraíba | `https://pb-ehr-services.saude.gov.br/api/` |
| Paraná | `https://pr-ehr-services.saude.gov.br/api/` |
| Pernambuco | `https://pe-ehr-services.saude.gov.br/api/` |
| Piauí | `https://pi-ehr-services.saude.gov.br/api/` |
| Rio de Janeiro | `https://rj-ehr-services.saude.gov.br/api/` |
| Rio Grande do Norte | `https://rn-ehr-services.saude.gov.br/api/` |
| Rio Grande do Sul | `https://rs-ehr-services.saude.gov.br/api/` |
| Rondônia | `https://ro-ehr-services.saude.gov.br/api/` |
| Roraima | `https://rr-ehr-services.saude.gov.br/api/` |
| Santa Catarina | `https://sc-ehr-services.saude.gov.br/api/` |
| São Paulo | `https://sp-ehr-services.saude.gov.br/api/` |
| Sergipe | `https://se-ehr-services.saude.gov.br/api/` |
| Tocantins | `https://to-ehr-services.saude.gov.br/api/` |

### Serviços Principais

A seguir estão listados os principais serviços que deverão ser utilizados para o envio ou consulta dos modelos da RNDS.


### Serviços Auxiliares

A seguir estão listados os serviços que irão auxiliar no envio ddos modelos da RNDS.


### Operações na RNDS

Como visto em Serviços Principais e Serviços Auxiliares, a RNDS disponibiliza serviços para realizar diversas operações, como: envio de registros (documentos), consulta, substituição etc. A seguir, detalhamos as operações realizadas com tais serviços.

#### Envio de registros à RNDS

O método `**POST** [base]/fhir/r4/Bundle` permite o envio (inclusão) de um registro (documento clínico) na RNDS. Os dados devem ser enviados conforme as definições do Modelo Computacional. Este processo pode ser melhor compreendido observando a Figura a seguir.

 **Figura 6 - Processo de envio de documento para a RNDS** 

##### Resposta da API – Criação de registros

Ao realizar o envio de um registro para a RNDS, este pode ser recebido com sucesso ou rejeitado devido a algum erro de estrutura ou regra negocial.

* O retorno será o status http `201 Created` e o Id RNDS será retornado por meio de 2 headers da resposta: *content-location* e *location*.
* Quando o registro é rejeitado diversos status http podem ser retornados, sendo o principal deles (no contexto da RNDS) o status `422 Unprocessable Entity`. Este status indica que o registro enviado não atendeu aos requisitos de estrutura FHIR e regras de negócio definidas para o documento, no body do retorno irá conter o código e a descrição do erro.

Exemplo de resposta com status http `422 Unprocessable Entity`:

```
{
    "resourceType": "OperationOutcome",
    "issue": [
      {
        "severity": "error",
        "code": "processing",
        "diagnostics": "(EHR-ERR793) Para a modalidade assistencial (Composition.category.coding.code) informada (http://www.saude.gov.br/fhir/r4/CodeSystem/BRModalidadeAssistencial#07) as datas de admissão (Encounter.period.start) e desfecho (Encounter.period.end) devem ser iguais (Compostion ID: urn:uuid:transient-0, Encounter ID: urn:uuid:transient-1)."
      }
    ]
}
```

#### Identificadores do Registro Enviado a RNDS

 Vale ressaltar que os registros são documentos computacionais, em formato JSON, compostos por perfis (*profiles*) do padrão FHIR R4. Cada registro enviado à RNDS possui dois identificadores: 

* **Identificador atribuído pelo sistema de origem**: também chamado de identificador local, é o ID criado pelo sistema de origem para identificar univocamente o registro em sua base.


   No arquivo JSON, o identificador local deve ser informado no profile *Bundle*, propriedade `identifier.value`. 


   Em "*system*", deve-se completar a URI ` http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-` com o número do identificador do solicitante (ver Identificador solicitante / *NamingSystem*). 
*  **Identificador atribuído pela RNDS**: também denominado de ID RNDS. Quando o registro é enviado com sucesso (*header* de resposta 201) à RNDS, no *header* `location` é gerada uma URL que é o identificador do registro na RNDS (ver Exemplos de consumo dos serviços). 

#### Consulta de registros na RNDS

 A RNDS permite a consulta de documentos enviados pelo integrador de duas maneiras: 

*  Pelo **Identificador Local**: `**GET** [base]/identifier?system=[system]&value=[id]&docType=[modelo]` 
*  Pelo **ID RNDS**: `**GET** [base]/fhir/r4/Composition/[id]/$document` 

##### Consulta por identificador local

`**GET** https://{{uf}}-ehrservices.saude.gov.br/api/identifier?system=http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-{{XXXX}}&value={{YYYY}}&docType={{modelo}}`
 
**Figura 7 - Consulta por identificador local** 

##### Resposta da API – Consulta por identificador local

A consulta por identificador local retorna um conjunto reduzido de informações do registro, incluindo as substituições realizadas.

```
[
  {
    "id": "fc1227b1-1045-4304-9f27-8a9dd883a865-c0m1",
    "cns": "702303127009117",
    "date": "2026-02-22T21:42:43.157412Z",
    "relatesTo": [],
    "status": "entered-in-error"
  },
  {
    "id": "53daabef-4bac-4874-ae8b-481ba9b7e415-c0m1",
    "cns": "702303127009117",
    "date": "2026-02-22T21:42:45.860809Z",
    "relatesTo": [
      {
        "code": "replaces",
        "targetReference": {
          "type": "Composition",
          "id": "fc1227b1-1045-4304-9f27-8a9dd883a865-c0m1"
        }
      }
    ],
    "status": "final"
  }
]
```

##### Consulta por ID RNDS

`**GET** https://{{uf}}-ehr-services.saude.gov.br/api/fhir/r4/Composition/{{idrnds}}/$document`
 
**Figura 8 - Consulta por ID RNDS** 

##### Resposta da API – Consulta por ID RNDS

A consulta por IDc RNDS retorna o Bundle completo do registro.

```
{
  "resourceType": "Bundle",
  "meta": {
    "lastUpdated": "2026-02-22T17:47:37.801-03:00"
  },
  "identifier": {
    "system": "http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-12345",
    "value": "759c8166-5900-44d5-8fcc-c54c9ec9f619-25363788754"
  },
  "type": "document",
  "timestamp": "2026-02-22T17:47:37.801-03:00",
  "entry": [
    {
      "fullUrl": "https://ehr-services-hmg.saude.gov.br/1.15/api/fhir/r4/Composition/f986ff6b-9329-4c4c-a405-aad988125bd9",
      "resource": {
        "resourceType": "Composition",
        "id": "f986ff6b-9329-4c4c-a405-aad988125bd9",
        "meta": {
          "lastUpdated": "2025-10-29T12:28:04.498-03:00",
          "profile": [
            "http://www.saude.gov.br/fhir/r4/StructureDefinition/RNDSRegistroEletronicoPrescricaoMedicamentos"
          ]
        },
        "status": "final",
        "type": {
          "coding": [
            {
              "system": "http://www.saude.gov.br/fhir/r4/CodeSystem/BRTipoDocumento",
              "code": "REPM"
            }
          ]
        }
      }
      ... outros elementos ...
    }
    ... outros recursos FHIR ...
  ]
}
```

#### Substituição de registros na RNDS

A substituição é um recurso para fins de retificação ou alteração de dados de um registro já existente na RNDS, que pode ser feita uma única vez. O documento de substituição enviado passa a ser o registro ativo e o substituído não será mais exibido. 
A seguir é descrito um exemplo de fluxo envolvendo a substituição de um registro na RNDS: 

* **R** – Registro inicial
* **S** – Registro que visa substituir o registro R
* **N** – Identificador gerado pelo estabelecimento (sistema de origem)
* **ID** – Identificador único gerado pela RNDS para cada registro

1. Estabelecimento envia o registro**R**para a RNDS com identificador**N**(gerado pelo estabelecimento)
1. RNDS grava o registro**R**e retorna o identificador único por ela criado para o registro R. Seja**ID**o valor deste identificador gerado pela RNDS
1. Observe que o registro**R**é identificado pelo estabelecimento por**N**e identificado pela RNDS por**ID**
1. Estabelecimento monta um novo registro, o registro**S**que visa substituir o registro**R**. A montagem de**S**é similar à montagem de**R**e será comentada nas seções posteriores. Duas regras devem ser observadas, contudo:
* o identificador de **S** deve ser **N**, ou seja, o identificador do documento a ser substituído, **R**, deve ser o mesmo identificador do documento que o substitui, **S**. Observe que este identificador é aquele criado pelo estabelecimento
* uma propriedade adicional, ***relatesTo***, conforme ilustrada abaixo, é necessária

Sendo assim, além dos ajustes dos dados a serem alterados, serão necessários os identificadores do sistema de origem e o atribuído pela RNDS, conforme descrito a seguir:

*  Propriedade ***Bundle.identifier***: em value, utilizar o identificador local (`{{id-sistema-origem}}`) do registro a ser substituído, ou seja, o novo registro que vai substituir deve ter o mesmo value do registro a ser substituído. ````"resourceType": "Bundle", "identifier": { "system": "http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-1111", "value": "{id-sistema-origem}" },```` 
*  Propriedade ***Composition.relatesTo***: essa propriedade apresenta a relação que este documento possui com outro já existente. 
*  O valor de ***replaces*** para ***code*** indica que o registro em questão substitui outro. A identificação do registro substituído, no fluxo acima identificado pelo registro **R**, fica por conta da propriedade reference do objeto ***targetReference***. O valor de ***targetReference*** identifica o recurso a ser substituído, neste caso um ***Composition***, e exatamente aquele cujo valor é identificado no exemplo pela sequência `{{id-rnds}}`. Convém esclarecer que este identificador não é o identificador fornecido pelo autor (estabelecimento) ao registro, mas aquele atribuído ao registro **R** pela RNDS, quando **R** foi submetido. ````"resourceType": "Composition", "relatesTo": [ { "code": "replaces", "targetReference": { "reference": "Composition/{id-rnds}" } } ]```` 

##### Resposta da API – Substituição de registros

Ao realizar a substituição de um registro para a RNDS, este pode ser recebido com sucesso ou rejeitado devido a algum erro de estrutura ou regra negocial.

* **Sucesso** O retorno será o status http `**201 Created**` e o novo Id RNDS será retornado por meio de 2 *headers* da resposta: ***content-location*** e ***location***. 
* **Rejeição** Quando o registro é rejeitado diversos status http podem ser retornados, sendo o principal deles (no contexto da RNDS) o status `**422 Unprocessable Entity**`. Este status indica que o registro enviado não atendeu aos requisitos de estrutura FHIR e regras de negócio definidas para o documento, no *body* do retorno irá conter o código e a descrição do erro. Exemplo de resposta com status http *422 Unprocessable Entity*. ````{ "resourceType": "OperationOutcome", "issue": [ { "severity": "error", "code": "processing", "diagnostics": "(EDS-MSG009) O documento fc1227b1-1045-4304-9f27-8a9dd883a865-c0m1 já foi substituído." } ] }```` 

#### Exclusão de registros na RNDS

O processo de deleção de documentos na RNDS se trata de uma exclusão lógica. Use o endereço do endpoint da UF a partir do qual o envio foi efetuado e o header Location (id) recebido mediante o envio.

`**DELETE** [base]/fhir/r4/Bundle/{{id-rnds}}`

Exemplo com o endpoint de MG e `{{id-rnds}}` fictício:

`**DELETE** https://mg-ehr-services.saude.gov.br/api/fhir/r4/Bundle/4a3133fd-d5bd-4e00-8688-283ae2ce703b-i0b0`
 
##### Resposta da API – Exclusão de registros

Ao realizar a exclusão de um registro para a RNDS, o retorno pode ser de sucesso ou de erro.

* **Sucesso** O retorno será o status http `**204 No Content**`.
* **Erro**: Quando ocorre algum erro na exclusão de registros diversos status http podem ser retornados, sendo o principal deles (no contexto da RNDS) o status `**422 Unprocessable Entity**`. No *body* do retorno irá conter o código e a descrição do erro. Exemplo de resposta com status http *422 Unprocessable Entity.* ````{ "resourceType": "OperationOutcome", "issue": [ { "severity": "error", "code": "processing", "diagnostics": "(EHR-ERR825) Para realizar a exclusão, o status do documento deve ser\"final\"." } ] }```` 

#### Consultar informações do servidor

Esta consulta permite verificar a disponibilidade do ambiente e as características do servidor FHIR da RNDS

`**GET** [base]/fhir/r4/metadata`

Exemplo com o endpoint de homologação:

`**GET** [base]/fhir/r4/metadata`
 
##### Resposta da API – Consultar informações do servidor

A consulta retorna o recurso *CapabilityStatement* com as informações do servidor FHIR.

```
{
  "resourceType": "CapabilityStatement",
  "id": "e719fde7-baa0-4d22-85db-8e075e4b99cc",
  "name": "RestServer",
  "status": "active",
  "date": "2026-03-12T02:13:30.188-03:00",
  "publisher": "Not provided",
  "kind": "instance",
  "software": {
    "name": "RNDS FHIR R4 HML Server",
    "version": "5.6.0"
  },
  "implementation": {
    "description": "HAPI FHIR",
    "url": "https://ehr-services-hmg.saude.gov.br/1.15/api/fhir/r4"
  },
  "fhirVersion": "4.0.1",
  "format": ["application/fhir+xml", "xml", "application/fhir+json", "json"],
  "rest": [
    {
      "mode": "server",
      "resource": [
        {
          "type": "Bundle",
          "profile": "http://hl7.org/fhir/StructureDefinition/Bundle",
          "interaction": [
            {
              "code": "create"
            },
            {
              "code": "delete"
            },
            {
              "code": "read"
            }
          ]
          ... outros elementos ...
        }
      ]
    }
  ]
}
```

#### Pesquisa de pacientes

A RNDS permite a pesquisa de pacientes de duas maneiras: por id e por CPF ou CNS.

##### Pesquisa de pacientes por id

`**GET** [base]/fhir/r4/Patient/[id]`
 
##### Resposta da API – Pesquisa de pacientes por id

A pesquisa de pacientes por id irá retornar o recurso *Patient* com as informações do indivíduo.

```
{
  "resourceType": "Patient",
  "id": "706800383790438",
  "meta": {
    "lastUpdated": "2020-07-31T11:38:44.000-03:00",
    "profile": [
      "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-patient-1.0"
    ]
  },
  ... outros elementos ...
  "identifier": [
    {
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf",
      "value": "00712863575"
    },
    {
      "use": "official",
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns",
      "value": "706800383790438",
      "period": {
        "start": "2012-04-24T23:39:38-03:00"
      }
    },
    {
      "use": "secondary",
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns",
      "value": "898051280670891",
      "period": {
        "start": "2008-05-29T13:40:58-03:00"
      }
    }
  ],
  "active": true,
  "name": [
    {
      "use": "official",
      "text": "NOME DO PACIENTE"
    }
  ],
  "gender": "female",
  "birthDate": "1985-07-28",
  ... outros elementos ...
}
```

**ⓘ IMPORTANTE**

 *O **id** do recurso *Patient* é igual ao **CNS definitivo** do indivíduo.* 

##### Pesquisa de pacientes por CPF ou CNS

`**GET** [base]/fhir/r4/Patient?identifier=http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf%7C[numero-cpf]`

Ou

`**GET** [base]/fhir/r4/Patient?identifier=http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns%7C[numero-cns]`


**ⓘ IMPORTANTE**

 *Os caracteres '**%7C**' correspondem ao '*pipe*' (**|**) no contexto de URL encoding (codificação de URL).* 

##### Resposta da API – Pesquisa de pacientes por CPF ou CNS

A pesquisa de pacientes por CPF ou CNS irá retornar um *Bundle* com os registros que correspondem ao parâmetro fornecido.

```
{
  "resourceType": "Bundle",
  "id": "489e8d00-77aa-434f-afa3-4ab8ea5d3139",
  "meta": {
    "lastUpdated": "2026-03-12T08:59:49.656-03:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": "https://ehr-serviceshmg.saude.gov.br/1.15/api/fhir/r4/Patient?identifier=http%3A%2F%2Frnds.saude.gov.br%2Ffhir%2Fr4%2FNamingSystem%2Fcpf%7C33339367901"
    }
  ],
  "entry": [
    {
      "fullUrl": "https://ehr-services-hmg.saude.gov.br/1.15/api/fhir/r4/Patient/700415845964843",
      "resource": {
        "resourceType": "Patient",
        "id": "700415845964843",
        "meta": {
          "lastUpdated": "2018-09-19T16:12:12.000-03:00",
          "profile": [
            "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-patient-1.0"
          ]
        },
        ... outros elementos ...
        "identifier": [
          {
            "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf",
            "value": "33339367901"
          },
          {
            "use": "official",
            "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns",
            "value": "700415845964843",
            "period": {
              "start": "2012-10-05T13:25:39-03:00"
            }
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "text": "NOME DO PACIENTE"
          }
        ],
        "gender": "male",
        "birthDate": "1981-11-24",
        ... outros elementos ...
      }
    }
  ]
}
```

#### Pesquisa de profissionais

A RNDS permite a pesquisa de profissionais de duas maneiras: por id e por CPF ou CNS.

##### Pesquisa de profissionais por id

`**GET** [base]/fhir/r4/Practitioner/[id]`
 
##### Resposta da API – Pesquisa de profissionais por id

A pesquisa de profissionais por id irá retornar o recurso *Practitioner* com as informações do profissional.

```
{
  "resourceType": "Practitioner",
  "id": "705800463790438",
  "meta": {
    "versionId": "202602",
    "lastUpdated": "2025-02-21T00:00:00.000-03:00",
    "profile": [
      "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-practitioner-1.0"
    ]
  },
  "identifier": [
    {
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf",
      "value": "00712863575"
    },
    {
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns",
      "value": "705800463790438"
    }
  ],
  "name": [
    {
      "use": "official",
      "text": "NAYANA MACHADO MEIRA"
    }
  ]
}
```

**ⓘ IMPORTANTE**

 *O **id** do recurso *Practitioner* é igual ao **CNS definitivo** do profissional.* 

##### Pesquisa de profissionais por CPF ou CNS

`**GET** [base]/fhir/r4/Practitioner?identifier=http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf%7C[numero-cpf]`

Ou

`**GET** [base]/fhir/r4/Practitioner?identifier=http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns%7C[numero-cns]`


**ⓘ IMPORTANTE**

 *Os caracteres '**%7C**' correspondem ao '*pipe*' (**|**) no contexto de URL encoding (codificação de URL).* 

##### Resposta da API – Pesquisa de profissionais por CPF ou CNS

A pesquisa de profissionais por CPF ou CNS irá retornar um *Bundle* com os registros que correspondem ao parâmetro fornecido.

```
{
  "resourceType": "Bundle",
  "id": "a4648614-97f9-48a3-9675-3dade776dce1",
  "meta": {
    "lastUpdated": "2026-03-12T10:17:03.667-03:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": "https://ehr-serviceshmg.saude.gov.br/1.15/api/fhir/r4/Practitioner?identifier=http%3A%2F%2Frnds.saude.gov.br%2Ffhir%2Fr4%2FNamingSystem%2Fcpf%7C00712863575"
    }
  ],
  "entry": [
    {
      "fullUrl": "https://ehr-serviceshmg.saude.gov.br/1.15/api/fhir/r4/Practitioner/705800463790438",
      "resource": {
        "resourceType": "Practitioner",
        "id": "705800463790438",
        "meta": {
          "versionId": "202602",
          "lastUpdated": "2025-02-21T00:00:00.000-03:00",
          "profile": [
            "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-practitioner-1.0"
          ]
        },
        "identifier": [
          {
            "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cpf",
            "value": "00712863575"
          },
          {
            "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cns",
            "value": "705800463790438"
          }
        ],
        "name": [
          {
            "use": "official",
            "text": "NAYANA MACHADO MEIRA"
          }
        ]
      }
    }
  ]
}
```

#### Consultar lotação profissional

Esta consulta permite verificar as funções dos profissionais de saúde nos estabelecimentos de saúde informando o número do CNS e o número do CNES.

`**GET** [base]/fhir/r4/PractitionerRole/[CNS]-[CNES]`
 
##### Resposta da API – Consultar lotação profissional

A consulta retorna o recurso *PractitionerRole* com o código CBO da função que o profissional de saúde exerce naquele estabelecimento de saúde.

```
{
  "resourceType": "PractitionerRole",
  "id": "207284801600008-2005654",
  "meta": {
    "versionId": "202603",
    "lastUpdated": "2025-07-09T00:00:00.000-03:00",
    "profile": [
      "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-practitionerrole-1.0"
    ]
  },
  "practitioner": {
    "reference": "Practitioner/207284801600008"
  },
  "organization": {
    "reference": "Organization/2005654"
  },
  "code": [
    {
      "coding": [
        {
          "system": "http://rnds.saude.gov.br/fhir/r4/CodeSystem/rnds-cbo-1.0",
          "code": "223565",
          "display": "Enfermeiro da estratégia de saúde da família"
        }
      ]
    }
  ]
}
```

#### Consultar estabelecimento de saúde

Esta consulta permite verificar as informações do estabelecimento de saúde desejado informando o número do CNES.

`**GET** [base]/fhir/r4/Organization/[CNES]`
 
##### Resposta da API – Consultar estabelecimento de saúde

A consulta retorna o recurso *Organization* com as informações do estabelecimento.

```
{
  "resourceType": "Organization",
  "id": "3179613",
  "meta": {
    "versionId": "202603",
    "lastUpdated": "2026-02-25T00:00:00.000-03:00",
    "profile": [
      "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-organization-1.0"
    ]
  },
  "extension": [
    {
      "url": "http://rnds.saude.gov.br/fhir/r4/StructureDefinition/rnds-operatessus-1.0",
      "valueBoolean": true
    }
  ],
  "identifier": [
    {
      "system": "http://rnds.saude.gov.br/fhir/r4/NamingSystem/cnes",
      "value": "3179613"
    }
  ],
  "active": true,
  "type": [
    {
      "coding": [
        {
          "system": "http://rnds.saude.gov.br/fhir/r4/CodeSystem/rnds-cnestype-1.0",
          "code": "02",
          "display": "CENTRO DE SAUDE/UNIDADE BASICA"
        }
      ]
    }
  ],
  "name": "UBS CONTINENTAL",
  "alias": ["PREFEITURA MUNICIPAL DE GUARULHOS"],
  "telecom": [
    {
      "system": "phone",
      "value": "1124567946"
    },
    {
      "system": "email",
      "value": "ubscontinental@gmail.com"
    }
  ],
  "address": [
    {
      "extension": [
        {
          "url": "http://hl7.org/fhir/StructureDefinition/geolocation",
          "extension": [
            {
              "url": "latitude",
              "valueDecimal": -23.468506
            },
            {
              "url": "longitude",
              "valueDecimal": -46.5310840856611
            }
          ]
        }
      ],
      "line": ["RUA PESSEGUEIRO", "111"],
      "city": "GUARULHOS",
      "district": "PQ CONTINENTAL B",
      "state": "SP",
      "postalCode": "07084250",
      "country": "BRASIL"
    }
  ]
}
```

#### Consultar detalhes de CodeSystem

Dado um código/sistema, ou uma codificação, esta consulta permite obter detalhes adicionais sobre o conceito, incluindo definição, status, designações e propriedades adicionais.

`**GET** [base]/fhir/r4/CodeSystem/$lookup?system=[url-codesystem]&code=[codigo]`

Exemplo com o endpoint de homologação:

`**GET** [base]/fhir/r4/CodeSystem/$lookup?system=http://www.saude.gov.br/fhir/r4/CodeSystem/BRCID10&code=I10`
 
##### Resposta da API – Consultar detalhes de CodeSystem

A consulta retorna o recurso *Parameters* com as informações do código consultado.

```
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "url",
      "valueUri": "http://www.saude.gov.br/fhir/r4/CodeSystem/BRCID10"
    },
    {
      "name": "code",
      "valueCode": "I10"
    },
    {
      "name": "display",
      "valueString": "Hipertensão essencial (primária)"
    },
    {
      "name": "name",
      "valueString": "Classificação Internacional de Doenças - Décima Revisão - CID-10"
    },
    {
      "name": "version",
      "valueString": "2008"
    }
  ]
}
```

### Mensagens e Erros da RNDS

 Ao enviar registros para as APIs da RNDS, a plataforma pode retornar diferentes respostas com alguns códigos. O documento abaixo tem como objetivo listar e descrever os erros **(ERRXXX)** e as mensagens **(MSG)** da RNDS, ajudando a identificar e corrigir inconsistências. 

`[Link para o documento da lista de erros](https://mobileapps-prd.saude.gov.br/portal-servicos/files/f3bd659c8c8ae3ee966e575fde27eb58/fb46e2bf9dd140ecfd74424aee49a0a2_jdpiqrqwx.pdf)`
 
Sendo: 

* A **mensagem sistêmica** é o texto cadastrado no sistema para que seja exposto aos integradores no momento de envio do documento na RNDS.
* A **descrição do erro** é uma explicação mais detalhada sobre a mensagem sistêmica apresentada pela RNDS.

