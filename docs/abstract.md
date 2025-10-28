# Abstract - Guia de Implementação da Regulação Assistencial (RIRA) da RNDS v1.0.0

* [**Índice**](toc.md)
* **Abstract**

## Abstract

| |
| :--- |
| *Page standards status:*[Informative](http://hl7.org/fhir/R4/versions.html#std-process) |

### Introduction

The Implementation Guide for the Assistance Regulation Information Model (RIRA) of the [National Health Data Network (RNDS)](https://www.gov.br/saude/pt-br/composicao/seidigi/rnds) is a comprehensive document designed to guide various health entities, including states, municipalities, the Federal District, health establishments, and private companies, in utilizing the services developed for the RNDS. This guide aims to ensure the seamless integration of local systems with the national network for the submission of [Assistance Regulation Information Model (RIRA)](https://servicos-datasus.saude.gov.br/detalhe/u286CON7Qz) following the [HL7 FHIR R4 standard](https://hl7.org/fhir/R4/).

### Contextualization

The RNDS is a national platform that integrates health data as part of the ["Meu SUS Digital"](https://www.gov.br/saude/pt-br/composicao/seidigi/meu-sus-digital) program, which is a federal initiative to materialize [Brazil's Digital Health Strategy](https://www.gov.br/saude/pt-br/composicao/seidigi/saude-digital). By leveraging cloud computing and emerging technologies, the RNDS creates a repository of health documents that stores citizens' health information in an accessible and interoperable manner. This platform not only facilitates healthcare professionals' access to patients' clinical histories, ensuring continuity of care, but also empowers individuals by providing them access to their health data.

The guide emphasizes the importance of interoperability, detailing how information exchange between digital health applications, such as electronic health records, portals, and mobile applications, is achieved through [RESTful](https://en.wikipedia.org/wiki/REST) web services developed according to the FHIR R4 standard. It outlines the necessary steps for credentialing, security measures to protect transactions, and the operations required for integration with the RNDS. Additionally, it defines the information and computational models for the RIRA, consolidates [FHIR](https://hl7.org/FHIR/) resources for the computational model, and provides example instances and downloadable artifacts for integrators.

In essence, the Implementation Guide for the RIRA of the RNDS is a crucial resource for ensuring that health data is shared timely and reliably across Brazil's healthcare ecosystem, thereby enhancing the quality and continuity of patient care.

