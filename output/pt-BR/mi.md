# Modelo de Informação - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

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

*  **Nível**: indica a relação de dependência do elemento aos demais. Um número maior significa que aquele item depende ou está subordinado ao de número menor e anterior a ele no modelo. Assim, um elemento de nível 2 é subitem de um elemento de nível 1, um de nível 3 é subitem de um de nível 2 e assim sucessivamente; 
*  **Seção/Item**: nome do bloco (seção) ou da informação a ser enviada; 
*  **Tipo de dados**: descreve o tipo de dado a ser preenchido, ou seja, a forma de representar o elemento; 
* **Ocorrência**: descreve o número mínimo e máximo de vezes que o elemento deve/pode ocorrer, ou seja, demonstra a obrigatoriedade e a quantidade de ocorrências do elemento:
*  **Conceito/Observações**: conceitua ou esclarece a forma de utilizar o elemento; 
*  **Mapeamento Computacional - FHIR**: relaciona o atributo do Modelo Informacional com o campo do Modelo Computacional em FHIR. 
*  **Perfil FHIR**: relaciona o atributo do Modelo Informacional com o perfil do Modelo Computacional em FHIR. 

### Blocos do Modelo de Informação

 Segue abaixo o modelo de informação para o RIRA: 

| | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Caracterização da Regulação | SECTION | 1..1 | Bloco de informações de identificação do registro enviado à RNDS. | N/A | N/A |
| 2 | Identificador do Registro no Sistema de Origem | II | 1..1 | Id no sistema de origem. | `Bundle.identifier.value` | `Bundle` |
| 2 | Status da Solicitação | CD | 1..1 | Status da solicitação do procedimento. | `Composition.event.code.coding.code` | [BRRegulacaoAssistencial](StructureDefinition-BRRegulacaoAssistencial.md) |
| 2 | Código do Procedimento | CD | 1..1 | Identificador único do procedimento. Texto codificado:* SIGTAP
 | `ServiceRequest.code.coding.code``Appointment.serviceType.coding.code` | [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)[BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) |
| 2 | Data da Solicitação | TS | 1..1 | Data e hora da solicitação do procedimento, no padrão ISO8601. | `ServiceRequest.authoredOn` | [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 2 | Data de Autorização | TS | 0..1 | Data e hora da autorização do procedimento, no padrão ISO8601. | `Appointment.created` | [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) |
| 2 | Data de Agendamento | TS | 0..1 | Data e hora da solicitação do procedimento, no padrão ISO8601. | `ServiceRequest.occurrenceDateTime` | [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 2 | Data da Execução | TS | 0..1 | Data e hora agendada para a realização do procedimento, no padrão ISO8601. | `Appointment.start``Appointment.end` | [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) |
| 1 | Caracterização dos Participantes | SECTION | 1..1 | Bloco de informações referentes ao indivíduo e aos estabelecimentos envolvidos na solicitação. | N/A | N/A |
| 2 | Identificador do Paciente | II | 1..1 | Identificação unívoca do usuário das ações e serviços de saúde, mediante número único válido em todo o território nacional, sendo:* Cadastro de Pessoa Física (CPF)
* Cartão Nacional de Saúde (CNS)
 | `Composition.subject.identifier.value``ServiceRequest.subject.identifier.value``Appointment.participant.actor.identifier.value``Condition.subject.identifier.value` | [BRRegulacaoAssistencial](StructureDefinition-BRRegulacaoAssistencial.md)[BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)[BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)[BRProblemaDiagnostico](StructureDefinition-BRProblemaDiagnostico.md) |
| 2 | Identificador do Estabelecimento de Saúde Solicitante | II | 0..1 | Identificação unívoca do estabelecimento solicitante, mediante número único válido em todo o território nacional, sendo:* Cadastro Nacional de Estabelecimentos de Saúde (CNES)
 | `ServiceRequest.requester.identifier.value` | [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 2 | Identificador do Estabelecimento de Saúde Regulador | II | 0..1 | Identificação unívoca do estabelecimento regulador, mediante número único válido em todo o território nacional, sendo:* Cadastro Nacional de Estabelecimentos de Saúde (CNES)
 | `Appointment.supportingInformation.identifier.value` | [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) |
| 2 | Identificador do Estabelecimento de Saúde Executante | II | 0..1 | Identificação unívoca do estabelecimento executante, mediante número único válido em todo o território nacional, sendo:* Cadastro Nacional de Estabelecimentos de Saúde (CNES)
 | `ServiceRequest.performer.identifier.value` | [BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 2 | Especialidade Médica do Executante | CD | 0..1 | Especialidade médica do profissional executante do procedimento, de acordo com a:* Classificação Brasileira de Ocupações (CBO)
 | `Appointment.specialty.coding.code``ServiceRequest.performerType.coding.code` | [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)[BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 1 | Caracterização da Solicitação | SECTION | 1..1 | Bloco de informações adicionais referentes à solicitação | N/A | N/A |
| 2 | Modalidade Assistencial | CD | 1..1 | Modalidade assistencial que gerou a solicitação do procedimento. | `Composition.category.coding.code``ServiceRequest.category.coding.code``Appointment.serviceCategory.coding.code` | [BRRegulacaoAssistencial](StructureDefinition-BRRegulacaoAssistencial.md)[BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md)[BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md) |
| 2 | Caráter da Solicitação | CD | 1..1 | Caráter da solicitação do procedimento. | `Appointment.appointmentType.coding.code``ServiceRequest.priority` | [BRAgendamentoRegulacaoAssistencial](StructureDefinition-BRAgendamentoRegulacaoAssistencial.md)[BRRequisicaoRegulacaoAssistencial](StructureDefinition-BRRequisicaoRegulacaoAssistencial.md) |
| 2 | Motivo da Solicitação | URI | 1..1 | Motivo da solicitação do procedimento, conforme:* Classificação Internacional de Doenças - CID
* Classificação Internacional de Atenção Primária - CIAP
 | `Condition.code.coding.code` | [BRProblemaDiagnostico](StructureDefinition-BRProblemaDiagnostico.md) |

