# Credenciamento - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Credenciamento

### Acesso ao Barramento de Serviços

 A integração com a RNDS dar-se-á por meio dos serviços (*web services*) mencionados anteriormente. Para que seja possível acessar esses serviços disponibilizados no *EHR Services* é necessário realizar solicitação de acesso no [Portal de Serviços do DATASUS](https://servicos-datasus.saude.gov.br/). 

 A solicitação de acesso à RNDS deve ser feita pelo estabelecimento de saúde, seja laboratório, secretaria estadual, hospital, unidade básica de saúde, entre outros. Se o estabelecimento de saúde tiver um provedor de tecnologia, esse provedor pode apoiar no processo de integração. Dessa forma, o provedor de tecnologia entra como um facilitador, pois a solicitação de acesso deverá ser efetuada pelo responsável do estabelecimento a ser conectado à RNDS. 

 **Nota**: *Vale contextualizar que o parceiro tecnológico pode acionar a equipe técnica do DATASUS por meio do [link de suporte](https://webatendimento.saude.gov.br/faq/rnds) se houver dúvidas nos testes ou algum problema no processo de integração.* 

 A Figura 3 apresenta uma imagem do portal de serviços do DATASUS. 

 **Figura 3 - Portal de Serviços do DATASUS** 

 Inicialmente é apresentado ao usuário a tela inicial que contempla todos os serviços disponibilizados, onde o usuário deverá identificar e clicar naquele que deseja solicitar a integração. 

 Após isso, o usuário será direcionado para a página principal dos serviços, onde podem ser encontradas todas as informações necessárias sobre o serviço selecionado juntamente com seu material de apoio e canal de suporte. Há também um botão denominado “Solicitar Acesso”, o qual o usuário deverá clicar para ser encaminhado os próximos passos da integração. 

### Conta GOV.BR

 O acesso aos serviços digitais oferecidos pelo governo deve ser autenticado inicialmente pela plataforma gov.br, a qual exige uma conta que qualquer cidadão pode criar pelo portal [https://acesso.gov.br](https://acesso.gov.br). 

 **Figura 4 - Página de autenticação da plataforma GOV.BR** 

 O gestor do estabelecimento de saúde deverá criar uma conta gov.br, e caso não possua uma, deverá providenciar, pois será necessária para requisitar a solicitação de acesso à RNDS. 

### Certificado Digital

O certificado digital é premissa obrigatória para acesso à RNDS, vez que esse é um dos controles mais fortes de segurança utilizado na rede. É necessário o certificado digital do estabelecimento principal. Vale contextualizar que os estabelecimentos que emitem nota fiscal ou acessam algum portal do governo já tem um certificado A1 do tipo e-CNPJ.

No contexto de uso do CPF da pessoa Responsável (solicitante do acesso no Portal de Serviços), vinculada ao estabelecimento, pode ser utilizado o certificado A1 do tipo e-CPF. Os certificados devem ser da cadeia ICP Brasil, pois quando o usuário carregar o seu certificado digital (chave pública “.cer” ou privada “.pfx”) ocorre a captura das informações de CNPJ ou CPF e a validade do certificado.

Em nenhum momento é capturada informação da sua chave privada, ela precisa ser instalada na máquina porque é necessidade do esquema de autenticação “two way ssl”, onde é necessário ter um certificado digital em cada uma das pontas para poder trocar um token (assinado em ambos os lados) garantindo assim uma comunicação segura.

**Nota**: *O certificado ficará associado ao estabelecimento de saúde (ou lista de estabelecimentos de saúde) informado na solicitação de acesso.*

### Estabelecimentos Filhos

Caso a solicitação envolva uma lista de estabelecimentos de saúde, todos deverão ser listados e obrigatoriamente devem ser do mesmo estado (UF).

 **Figura 5 - Identificação de estabelecimentos Filhos** 

### Identificador Solicitante / NamingSystem

 O identificador do solicitante é um número fornecido pela RNDS quando a solicitação de acesso à RNDS é aprovada, este número é fundamental para iniciar o processo de Homologação e deve ser encontrado no menu “Gerenciar Credenciais” conforme a imagem abaixo. 

 **Figura 6 - Gerenciador de Credenciais** 

 Este número deve ser sempre empregado na construção da identificação de uma requisição submetida para a RNDS. 

