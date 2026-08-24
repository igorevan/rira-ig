# Principal - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0-release

## Principal

### Introdução

 Este Guia de Implementação (IG) tem o objetivo de orientar Estados, Municípios, Distrito Federal, Estabelecimentos de Saúde ou Empresas Privadas que fornecem soluções/software na área de saúde a utilizarem os serviços *(web services)* que foram desenvolvidos para a [Rede Nacional de Dados em Saúde (RNDS)](https://www.gov.br/saude/pt-br/composicao/seidigi/rnds), fornecendo as orientações técnicas necessárias para a integração dos sistemas/soluções locais com a rede, para o envio do [Regulação Assistencial (RIRA)](https://rnds-guia.saude.gov.br/docs/rira/mi-rira/) seguindo as especificações do padrão [HL7 FHIR versão R4](https://hl7.org/fhir/R4/). 

### Contextualização

 A RNDS é uma plataforma nacional de integração de dados em saúde que faz parte do [Meu SUS Digital](https://www.gov.br/saude/pt-br/composicao/seidigi/meu-sus-digital), um programa do Governo Federal que tem como principal missão materializar a [Estratégia de Saúde Digital do Brasil](https://www.gov.br/saude/pt-br/composicao/seidigi/saude-digital). 

 A RNDS utiliza computação em nuvem e tecnologias emergentes para criar um repositório de documentos responsável por armazenar informações de saúde dos cidadãos, mantendo a privacidade, integridade e auditabilidade dos dados de maneira acessível e interoperável. Com isso, fornece aos profissionais de saúde acesso à história clínica do paciente, permitindo a transição e a continuidade do cuidado, além de possibilitar aos indivíduos acesso aos seus dados de saúde. 

 Dessa forma, os serviços (*web services*) permitirão que as entidades da área da saúde compartilhem as informações de Regulação Assistencial (RIRA) com a RNDS de forma oportuna e confiável a quem precisa desta informação. 

### Interoperabilidade

 Para garantir a interoperabilidade entre as aplicações de Saúde Digital, em especial Prontuário(s) Eletrônico(s) do Paciente, portais e aplicações (*web e mobile*), a troca de informações ocorre por meio de serviços (*web services*) [RESTful](https://pt.wikipedia.org/wiki/REST), desenvolvidos de acordo com o padrão [FHIR R4](https://hl7.org/FHIR/). 

### Fluxo para Integração com a RNDS

Abaixo você encontra um material com o fluxo oficial para integração com a RNDS.

<iframe src="https://mobileapps-prd.saude.gov.br/portal-servicos/files/f3bd659c8c8ae3ee966e575fde27eb58/0e3affbe4f1b86b50ae78ab652b2ebaa_pgst0fpqe.pdf" width="100%" height="600px"> Seu navegador não suporta visualização de PDF. <a href="https://mobileapps-prd.saude.gov.br/portal-servicos/files/f3bd659c8c8ae3ee966e575fde27eb58/0e3affbe4f1b86b50ae78ab652b2ebaa_pgst0fpqe.pdf">Clique
      aqui para abrir</a>. </iframe>
 
### Roteiro

*  [ *Abstract* ](abstract.md): Introdução e resumo deste guia, em inglês. *Introduction and summary of this guide, in English.* 
*  [Credenciamento](credenciamento.md): Saiba qual é o processo e requisitos a serem seguidos por um estabelecimento de saúde para a integração com a RNDS. 
*  [Integração](integracao.md): Define as operações a serem atendidas para integração com a RNDS. 
*  [Modelo de Informação](mi.md): Define o Modelo de Informação (MI) do RIRA. 
*  [Modelo Computacional](mc.md): Define o Modelo Computacional (MC) do RIRA. 
*  [Artefatos](artifacts.md): Reúne todos os recursos *(Resources)* do FHIR para elaboração do Modelo Computacional do RIRA. 
*  [Exemplos](exemplos.md): Instâncias de exemplos. 
*  [Downloads](downloads.md): Artefatos empregados pelos integradores. 
*  [Feedback](forms.md): Espaço para feedbacks, sugestões e melhorias. 
*  [Suporte da RNDS](suporte.md): Canal de suporte relacionados a RNDS. 

