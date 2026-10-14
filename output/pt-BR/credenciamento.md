# Credenciamento - Guia de Implementação do Registro de Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Credenciamento

### Requisitos técnicos

 A interoperabilidade com a RNDS dar-se-á por meio dos serviços (*web services*) mencionados anteriormente. Para que seja possível acessar esses serviços disponibilizados no *EHR Services* é necessário realizar solicitação de acesso no [Portal de Serviços do DATASUS](https://servicos-datasus.saude.gov.br/). 

#### Acesso ao Barramento de Serviços

O processo de credenciamento de um estabelecimento de saúde junto à RNDS é realizado em duas fases. Na primeira o estabelecimento requisita o acesso ao ambiente de homologação. Na segunda, o estabelecimento requisita acesso ao ambiente de produção. Quando esta última é concedida, o estabelecimento está autorizado a trocar informações com a RNDS. 

##### Fluxo típico

1. O gestor do estabelecimento de saúde deve obter um certificado digital, caso não possua.
1. O gestor deve criar uma conta[gov.br](https://www.gov.br/), caso ainda não a possua.
1. O gestor deve solicitar acesso à RNDS (primeira fase). A solicitação de acesso é feita pelo[Portal de Serviços](https://servicos-datasus.saude.gov.br/), cujo acesso exige uma conta[gov.br](https://www.gov.br/)(passo anterior). São requisitadas várias informações sobre o estabelecimento de saúde, inclusive o certificado digital (primeiro passo).
1. O gestor deve obter o identificador do solicitante, ou seja, um identificador fornecido pelo DATASUS para o estabelecimento de saúde em questão, cujo acesso ao ambiente de homologação é concedido.
1. O integrador deve ambientar-se com os serviços (entradas/saídas) oferecidos e, dessa forma, conhecê-los e compreendê-los. Observe que esta atividade pode ser iniciada antes dos passos anteriores.
1. O integrador deve desenvolver a solução tecnológica, aqui chamada de conector, para a interoperabilidade com a RNDS.
1. O integrador deve verificar a conformidade do conector com o contrato estabelecido para a interoperabilidade com a RNDS.
1. O integrador deve produzir as evidências necessárias para homologar o conector desenvolvido.
1. O gestor deve solicitar acesso ao ambiente de produção e aguardar a resposta do DATASUS.
1. O integrador deve colocar em produção o software que realiza a interoperabilidade entre o estabelecimento de saúde e a RNDS, homologado no passo anterior.

##### Diagrama

O diagrama abaixo, na notação BPMN, ilustra o fluxo de atividades de credenciamento, distribuídas entre três atores: DATASUS, Gestor e Integrador, conforme Figura 1. 

 **Figura 1 - Diagrama do fluxo de atividades de credenciamento** 

##### Processo de Credenciamento

 A solicitação de acesso à RNDS deve ser feita pelo estabelecimento de saúde, seja laboratório, secretaria estadual, hospital, unidade básica de saúde, entre outros. Se o estabelecimento de saúde tiver um provedor de tecnologia, esse provedor pode apoiar no processo de integração. Dessa forma, o provedor de tecnologia entra como um facilitador, pois a solicitação de acesso deverá ser efetuada pelo responsável do estabelecimento a ser conectado à RNDS. 

 **ⓘ NOTA** 

 *Vale contextualizar que o parceiro tecnológico (integrador) poderá abrir chamado a equipe técnica do DATASUS por meio do [Suporte ao Usuário](https://webatendimento.saude.gov.br/faq/rnds) caso tenha dúvidas nos testes ou algum problema no processo de interoperabilidade.* 

#### Portal de Serviços do DATASUS

Inicialmente, é apresentada ao usuário a tela inicial com todos os serviços disponibilizados. O usuário deve identificar e clicar no serviço desejado para solicitar a interoperabilidade. Em seguida, será direcionado à página principal do serviço selecionado, onde encontrará todas as informações necessárias, incluindo material de apoio e canal de suporte. Nessa página, há também um botão denominado “Solicitar Acesso”, que o usuário deve clicar para prosseguir com os próximos passos da interoperabilidade. 

 **Figura 2 - Portal de Serviços do DATASUS** 

#### Gov.br

O acesso aos serviços digitais oferecidos pelo governo deve ser autenticado inicialmente pela plataforma [gov.br](https://www.gov.br/), a qual exige uma conta que qualquer cidadão pode criar pelo portal [https://acesso.gov.br/](https://acesso.gov.br/), ilustrado na Figura 3. 

 **Figura 3 - Tela de acesso ao gov.br** 

##### Página de autenticação da plataforma gov.br

 O gestor do estabelecimento de saúde deverá criar uma conta [ gov.br](https://www.gov.br/), e caso não possua uma, deverá providenciá-la, pois será necessária para requisitar a solicitação de acesso à RNDS. 

#### Certificado Digital

O certificado digital é premissa obrigatória para acesso à RNDS, vez que esse é um dos controles mais fortes de segurança utilizado na rede. É necessário o certificado digital do estabelecimento principal. Vale contextualizar que os estabelecimentos que emitem nota fiscal ou acessam algum portal do governo já tem um certificado A1 do tipo e-CNPJ.

No contexto de uso do CPF da pessoa Responsável (solicitante do acesso no Portal de Serviços), vinculada ao estabelecimento, pode ser utilizado o certificado A1 do tipo e-CPF. Os certificados devem ser da cadeia ICP Brasil, pois quando o usuário carregar o seu certificado digital (chave pública “.cer” ou privada “.pfx”) ocorre a captura das informações de CNPJ ou CPF e a validade do certificado.

Em nenhum momento é capturada informação da sua chave privada, ela precisa ser instalada na máquina porque é necessidade do esquema de autenticação “two way ssl”, onde é necessário ter um certificado digital em cada uma das pontas para poder trocar um token (assinado em ambos os lados) garantindo assim uma comunicação segura.

 **ⓘ NOTA** 

 *O certificado ficará associado ao estabelecimento de saúde (ou lista de estabelecimentos de saúde) informado na solicitação de acesso.* 

#### Estabelecimentos Filhos

Caso a solicitação envolva uma lista de estabelecimentos de saúde, todos deverão ser listados e obrigatoriamente devem ser do mesmo estado (UF).

 **Figura 4 - Tela de cadastro e identificação de estabelecimentos filhos** 

#### Identificador Solicitante / NamingSystem

 O identificador do solicitante é um número fornecido pela RNDS quando a solicitação de acesso à RNDS é aprovada, este número é fundamental para iniciar o processo de Homologação e deve ser encontrado no menu “Gerenciar Credenciais”, conforme a imagem abaixo. 

 **Figura 5 - Tela de gerenciamento de credencial** 

 
Este número deve ser sempre empregado na construção da identificação de uma requisição submetida para a RNDS. 

