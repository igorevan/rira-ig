# Integração - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* **Integração**

## Integração

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Integração com a RNDS

 Para garantir a interoperabilidade entre as aplicações de Saúde Digital, em especial Prontuário(s) Eletrônico(s) do Paciente (PEP), portais e aplicações (*web e mobile*), a troca de informações ocorre por meio de serviços (*web services*) RESTful, desenvolvidos de acordo com o padrão [FHIR R4](https://hl7.org/FHIR/). 

### Serviços Auxiliares

 A seguir estão listados os serviços que irão auxiliar no envio da informação principal, o RIRA. 

 


 

 Em relação ao serviço `**GET**/fhir/r4/Patient`, quando não for possível captar o CPF ou CNS do cidadão/paciente, é importante que o sistema/solução capture os dados demográficos do usuário por meio eletrônico ou físico (nas fichas de registro regular do caso de uso). Desta forma, será possível realizar a busca demográfica ou a criação do CNS (CADSUS inserir endereço eletrônico) a ser utilizado como identificador do paciente no documento eletrônico. 

### Serviços Principais

 A seguir estão listados os serviços que deverão ser usados para o envio ou consulta da informação principal, o RIRA. 

 


 

### Exclusão de Registros na RNDS

 Recomenda-se que a transação para exclusão de registros (`DELETE`) somente seja efetuada nas seguintes situações: 

 
* **1ª situação**: Paciente/cidadão errado. As informações registradas e enviadas não se referem ao cidadão vinculado ao documento clínico.
* **2ª situação**: Registros duplicados. Foi enviado mais de um documento clínico contendo as mesmas informações sobre o mesmo evento e um mesmo paciente/cidadão. Neste caso, cabe ao integrador definir qual dos documentos se mantém e quais serão excluídos.
 

 Como critério de segurança para efetivar a exclusão, será mantida a estrutura atual presente no FHIR, ou seja, o sistema de autorização irá considerar: UF, CNES, identificador do sistema (`identifier.system`) e o autor do documento (*author*). A estrutura FHIR deverá previamente verificar a existência do documento antes de realizar a ação de exclusão. Caso seja detectado que o documento não existe, a requisição será cancelada e apresentará o erro 404. 

 O status do documento excluído será (`entered-in-error`) e o status do documento válido será (`final`). Este registro não aparecerá mais nos resultados da pesquisa e as tentativas de ler o recurso falharão com uma resposta "*HTTP 410 Gone*"" (ver exemplos de consumo dos serviços). 

 **Nota**: *O[SUS Digital Profissional](https://www.gov.br/saude/pt-br/composicao/seidigi/meu-sus-digital)é uma plataforma desenvolvida pelo Ministério da Saúde para materializar a Estratégia de Saúde para o Brasil, e tem como objetivo a troca de informações em saúde entre profissionais de saúde de toda a rede de atenção à saúde. Dessa forma, os profissionais acessam as informações de saúde de um determinado paciente a partir de seu histórico já padronizado, sempre dentro de um contexto de atendimento. O contexto de atendimento indica que o paciente passou por atendimento em um estabelecimento de saúde com um profissional de saúde.* 

### Identificadores do Registro Enviado a RNDS

 Vale ressaltar que os registros são documentos computacionais, em formato JSON, compostos por perfis (*profiles*) do padrão FHIR R4. Cada registro enviado à RNDS possui dois identificadores: 

* **Identificador atribuído pelo sistema de origem**: também chamado de identificador local, é o ID criado pelo sistema de origem para identificar univocamente o registro em sua base.


   No arquivo JSON, o identificador local deve ser informado no profile *Bundle*, propriedade `identifier.value`. 


   Em "*system*"", deve-se completar a URI `http://www.saude.gov.br/fhir/r4/NamingSystem/BRRNDS-` com o número do identificador do solicitante (ver Identificador solicitante / *NamingSystem*). 
*  **Identificador atribuído pela RNDS**: também denominado de ID RNDS. Quando o registro é enviado com sucesso (*header* de resposta 201) à RNDS, no *header* `location` é gerada uma URL que é o identificador do registro na RNDS (ver Exemplos de consumo dos serviços). 


   **IMPORTANTE**: os *softwares* integradores DEVEM SALVAR o identificador local e o ID RNDS para que possam realizar ações futuras como: pesquisa, substituição (ver Substituição de registro na RNDS) e exclusão. 

### Ambientes de Integração

Seguindo as boas práticas serão disponibilizados dois ambientes para a integração: homologação e produção.

#### Ambiente de Homologação

O ambiente de homologação tem como finalidade validar a integração, seus parâmetros de entradas, saídas e comportamentos negociais, permitindo a realização de testes antes da efetiva comunicação com o ambiente de produção. O ambiente de homologação é único, ou seja, todos os interessados em realizar o consumo dos serviços (*web services*) utilizarão o mesmo ambiente. Porém, mesmo usando o mesmo ambiente, as informações trafegadas (incluídas ou consultadas) estarão restritas aos estabelecimentos de saúde (CNES) elencados na etapa de credenciamento. Os endereços dos componentes de integração, no ambiente de homologação, são:

* Utilizado para obtenção do token em ambiente de homologação:
*  Utilizado para comunicação com demais serviços do ambiente de Homologação: 

#### Evidências da Homologação

A partir dos testes realizados e da implementação local, serão aceitas como evidências dos testes em homologação um arquivo com:

* 1 print do validador com sucesso;
* 1 print do *header* de resposta de criação do registro na RNDS;
* 1 print do *Bundle* enviado.

Com essas evidências, o solicitante pode solicitar acesso ao ambiente de produção no [Portal de Serviços](https://servicos-datasus.saude.gov.br/).

### Ambiente de Produção

O ambiente de produção é o ambiente estável e real que provê os serviços (*web services*) a serem consumidos. Para o ambiente produtivo, os integradores deverão acessar os endereços dos seus estados (UF). Durante o credenciamento, a credencial de acesso (Certificado Digital) será associada a um estabelecimento de saúde (CNES) (ou conjunto de estabelecimentos de saúde) no Portal de Serviços do DATASUS. Com isso, a credencial de acesso pertencerá a um estado (UF) específico. Acessos a estados diferentes não são permitidos e serão bloqueados automaticamente pelos serviços (*web services*). Os endereços dos componentes de integração, no ambiente de produção, por estado, são:

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

