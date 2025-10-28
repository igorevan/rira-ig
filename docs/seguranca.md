# Segurança - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* **Segurança**

## Segurança

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Segurança

 Somente com uma solicitação de acesso aprovada será possível realizar o consumo dos serviços (*web services*) do *EHR Services*. 

 Após a aprovação, o primeiro passo para realizar o consumo dos serviços é realizar a autenticação utilizando o serviço `POST@/token` no componente *EHR Auth*. Durante o processo de autenticação é verificado se o certificado digital está dentro do período de vigência e se ele, ou um de seus superiores na cadeia, foi revogado. 

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

Na página da RNDS no [Portal de Serviços do DATASUS](https://servicos-datasus.saude.gov.br/) há um projeto de exemplo para obtenção do *token* utilizando a linguagem [*Java*](https://www.java.com/). 

