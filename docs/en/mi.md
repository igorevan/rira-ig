# Modelo de Informação - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Modelo de Informação

### Contexto

A Regulação Assistencial desempenha um papel fundamental na organização e gestão dos serviços de saúde no âmbito do Sistema Único de Saúde (SUS). Tem como principal objetivo promover o acesso do usuário às ações e serviços de saúde, em tempo oportuno e de forma resolutiva, por meio da organização, controle, gerenciamento e priorização do acesso e dos fluxos assistenciais no âmbito do SUS.

Para alcançar seus objetivos, a Regulação Assistencial utiliza uma variedade de mecanismos. Um exemplo são as Centrais de Regulação, responsáveis por organizar o fluxo de atendimento dos pacientes e gerenciar a oferta de serviços de saúde em uma determinada região. Essas centrais desempenham um papel crucial na distribuição equitativa dos recursos disponíveis, direcionando os usuários para os serviços adequados com base em suas necessidades.

A implementação efetiva da Regulação Assistencial é crucial para garantir a eficiência e a efetividade dos serviços de saúde. Ela evita a sobrecarga de alguns serviços, distribuindo equitativamente a demanda, ao mesmo tempo em que garante que nenhum usuário fique sem atendimento adequado. Além disso, contribui para uma melhor utilização dos recursos financeiros e humanos disponíveis, garantindo a sustentabilidade do sistema de saúde como um todo.

O Registro de Informações de Regulação Assistencial (RIRA) é um marco na padronização e compartilhamento de informações no âmbito da regulação assistencial no Sistema Único de Saúde (SUS). Este modelo visa garantir a troca de informações dos processos regulatórios entre os diversos pontos de gestão e atenção à saúde, promovendo a continuidade do cuidado durante toda a vida do cidadão.

Considera a necessidade de garantir a troca da informação entre os diversos pontos de atenção e gestão do acesso à saúde, buscando promover a continuidade e a integralidade do cuidado, apoiar os profissionais de saúde para uma assistência mais resolutiva e segura, disponibilizar ao paciente informações sobre seu estado de saúde enquanto protagonista do seu cuidado, e garantir informações de qualidade para a tomada de decisão em saúde por meio da RNDS. 

A criação do Registro de Informações de Regulação Assistencial (RIRA), instituído pela Portaria Conjunta SAES/SEIDIGI nº 3, de 18 de abril de 2023, marca um passo significativo na evolução da Rede Nacional de Dados Saúde (RNDS). Este modelo estabelece um arcabouço robusto para a coleta, organização e compartilhamento de informações no âmbito da regulação assistencial no Sistema Único de Saúde (SUS), promovendo a interoperabilidade entre os sistemas de informação.

O Web Service da RNDS foi desenvolvido para permitir que estabelecimentos de saúde públicos ou privados compartilhem os registros da regulação assistencial no SUS, disponibilizando informações confiáveis para quem precisa no momento que precisa.

### Objetivo

Estabelecer a estrutura do Registro de Informações de Regulação Assistencial (RIRA) com o objetivo de promover o cuidado adequado, em tempo oportuno, aos usuários do SUS, tendo como base os princípios que norteiam o SUS, quais sejam, a universalidade, a equidade e a integralidade.

* Proporcionar a continuidade do cuidado;
* Qualificar a atenção em saúde e a segurança do indivíduo;
* Fortalecer a coordenação do cuidado;
* Otimizar o uso de recursos públicos;
* Fortalecer a Rede Nacional de Dados em Saúde (RNDS) e a qualidade das informações prestadas;
* Facilitar a coleta, agregação, tratamento e análise de dados para tomada de decisão e produção de conhecimento. 

### Marcos Legais

*  [PORTARIA CONJUNTA SAES/SEIDIGI Nº 3, DE 18 DE ABRIL DE 2023](https://www.in.gov.br/en/web/dou/-/portaria-conjunta-saes/seidigi-n-3-de-18-de-abril-de-2023-478301026) 

### Modelo de Informação

 O modelo de informação é uma representação conceitual e canônica, onde os elementos referentes a um documento específico são modelados em seções e blocos de dados, com seus respectivos tipos de dados a serem informados. Também são apresentadas as referências para o uso de recursos terminológicos, da seguinte maneira: 

*  **Coluna 1** - Nível: apresenta o nível do elemento no modelo de informação; 
* **Coluna 2** - Ocorrência: descreve o número de vezes (cardinalidade) que o elemento deve/pode aparecer:
*  **Coluna 3** - Seção/Item: nome do bloco ou da informação a ser enviada; 
*  **Coluna 4** - Tipo de dado: descreve o tipo de dado a ser preenchido; 
*  **Coluna 5** - Conceito: apresenta as definições do elemento; 
*  **Coluna 6** - Definição de uso do elemento: Observações e regras de negócio relacionadas ao elemento; 
*  **Coluna 7** - Conteúdo: apresenta, quando necessário, o grupo de códigos (*ValueSet*) a ser utilizado para preenchimento do elemento; 
*  **Coluna 8** - Recurso FHIR: relaciona o atributo do Modelo Informacional com o perfil do Modelo Computacional em FHIR. 

### Blocos do Modelo de Informação

 Segue abaixo o modelo de informação para o RIRA: 

#### Caracterização da Regulação

| | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 1..1 | Caracterização da regulação | Seção |  |  |  |  |
| 2 | 1..1 | Identificador do registro | Identificador | Identificador do registro no sistema de origem.**Regra Negocial 01**: Deverá ser utilizado o identificador do registro no sistema de origem para registro da solicitação. Neste campo deverá constar o identificador único do registro no sistema de origem. **Regra Negocial 02**: Para as operações de consulta, alteração e exclusão, deverá ser considerado como identificador único do evento de regulação, o identificador do documento na Rede Nacional de Dados em Saúde (RNDS).  | O identificador único do registro de regulação no sistema de origem |  | *Bundle*de envio |
| 2 | 1..1 | Status da solicitação | Texto codificado:- Pendente- Agendado- Atendido/Internado- Falta- Negado/Cancelado- Excluído- Devolvido para o solicitante | Status da solicitação do procedimento. | O código que identifica unicamente o status da solicitação, conforme tabela de status de solicitação. | [Status de Regulação Assistencial](ValueSet-BRStatusRegulacaoAssistencial.md) | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)* |
| 2 | 0..1 | Data de alteração de status | Data | Data e hora da alteração de status da solicitação do procedimento no padrão ISO8601. | A data e hora de alteração de status da solicitação de procedimento regulado. |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)* |
| 2 | 1..1 | Código do procedimento | Texto codificado | Identificador único do procedimento. Texto codificado: SIGTAP. | O código que identifica unicamente o procedimento conforme tabela SUS. | [Procedimento Realizado](ValueSet-BRProcedimentosNacionais-1.0.md) | [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 1..1 | Data da solicitação | Data | Data e hora da solicitação do procedimento no padrão ISO8601. | A data e hora de criação da solicitação inicial do procedimento regulado. |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)* |
| 2 | 0..1 | Data de autorização | Data | Data e hora da autorização do procedimento no padrão ISO8601. | A data e hora em que a solicitação de procedimento regulado foi autorizada. |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 0..1 | Data de agendamento | Data | Data e hora da autorização do procedimento no padrão ISO8601. | A data e hora do agendamento da solicitação de procedimento regulado. |  | [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 0..1 | Data da execução | Data | Data e hora da execução do procedimento no padrão ISO8601. | A data e hora em que o procedimento regulado foi executado. |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)* |

#### Caracterização dos Participantes

| | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 1..1 | Caracterização dos participantes | Seção |  |  |  |  |
| 2 | 1..1 | Identificador de paciente | Identificador | Identificação única do participante, por meio de CPF ou CNS. | O identificador nacional do participante que poderá ser CPF ou CNS |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 1..1 | Identificador do estabelecimento de saúde solicitante | Identificador | Identificação única do estabelecimento solicitante, por meio do CNES. | O identificador nacional do estabelecimento no Cadastro Nacional de Estabelecimento de Saúde |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)* |
| 2 | 0..1 | Identificador do estabelecimento de saúde regulador | Identificador | Identificação única do estabelecimento regulador , por meio do CNES. | O identificador nacional do estabelecimento no Cadastro Nacional de Estabelecimento de Saúde |  | [Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 0..1 | Identificador do estabelecimento de saúde executante | Identificador | Identificação única do estabelecimento executante, por meio do CNES. | O identificador nacional do estabelecimento no Cadastro Nacional de Estabelecimento de Saúde |  | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)* |
| 2 | 0..1 | Especialidade médica do executante | Texto codificado | Identificação da especialidade médica do profissional executante do procedimento. Texto codificado: CBO.**Regra Negocial 03**: Caso o procedimento informado pertença aos grupos 03 ou 04 da tabela SUS, o código CBO será obrigatório. | O código que identifica unicamente a especialidade do executante conforme tabela de CBO. O código CBO da especialidade está diretamente vinculado ao procedimento solicitado. Assim, para determinados procedimentos esse ponto será obrigatório. | [Classificação Brasileira de Ocupações (CBO)](ValueSet-BROcupacao-1.0.md) | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |

#### Caracterização da Solicitação

| | | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 1..1 | Caracterização da solicitação | Seção |  |  |  |  |
| 2 | 1..1 | Modalidade assistencial | Texto codificado:- Ambulatorial- Hospitalar | Modalidade assistencial que gerou a solicitação do procedimento. | O código que identifica unicamente a modalidade, conforme tabela de modalidades. | [Modalidade Assistencial (RIRA)](ValueSet-BRModalidadeAssistencialMIRA.md) | [Regulação Assistencial](StructureDefinition-BRRegulacaoAssistencial.md)*(Composition)*[Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 1..1 | Caráter da solicitação | Texto codificado:- Eletivo- Urgência | Caráter da solicitação do procedimento. | O código que identifica unicamente o grau de prioridade da solicitação no modelo de informação assistencial, conforme tabela de caráter da solicitação. | [Caráter de Atendimento no MIRA](ValueSet-BRCaraterAtendimentoMIRA.md) | [Requisição de Regulação Assistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)*(ServiceRequest)*[Agendamento de Regulação Assistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)*(Appointment)* |
| 2 | 1..1 | Motivo da solicitação | Texto codificado | Identificação do motivo da solicitação do procedimento. Texto codificado por terminologia externa CID-10. | O código que identifica unicamente a condição clínica conforme tabela de Classificação Internacional de Doenças na versão 10 (CID10). | [Classificação Internacional de Doenças - Décima Revisão (CID-10)](ValueSet-BRCID10-1.0.md) | [CID10 Avaliado](StructureDefinition-BRCID10Avaliado-1.0.md)*(Condition)* |

