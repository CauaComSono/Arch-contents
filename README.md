# Arch-contents

## Estilos arquiteturais
Uma arquitetura é a estrutura global (Que emgloba todas as arquiteturas)

---

**O que é Desing?** *O design é o micro, como estruturar as classes, já a arquitetura é o macro*

---
## Quais são os estilos arquiteturais globais?

### Client-Server
O estilo arquitetural client-server é um paradigma que distribui funcionalidades entre servidores que fornecem serviços e clientes que consomem esses serviços

### Thin-Client vs Fat-Client (Thick Client)
  Em um modelo de thin-client, a maior parte do processamento e armazenamento é feita no servidor, com o cliente focando apenas na interface do usuário, já no Fat-Client o cliente também executa uma parte significativa da lógica da aplicação 
  
  ![imagem](https://www.baeldung.com/wp-content/uploads/sites/4/2023/04/thin_thick.drawio-1.png)

  ## Contextos de aplicação
  Aplicações web e sistemas de banco de dados são exemplos típicos de arquiteturas client-server.
  Normalmente combinado com outros estilos, Component-based, layered e utilizado em padrões arquiteturais como MVC.
  
---
## Component-Based
Fowler descreve que Component-Based Architecture como uma abordagem para organizar sistemas de software em componentes reutilizáveis, que podem ser desenvolvidos e implantados de forma independente (Muito utilizado no Front-End)

## Principais benefícios
Reutilização: Componentes bem definidos podem ser reutilizados em diferentes sistemas, reduzindo o tempo de desenvolvimento e os custos
Facilidade de Manutenção: A modularidade dos componentes facilita a manutenção e a evolução do sistema, permitindo que componentes individuais sejam atualizados ou substituídos sem afetar o restante do sistema.

---
## Exemplos de _Component-based_
- Sistema de gestão empresarial (ERP) - [Monólito modular](https://www.thoughtworks.com/en-us/insights/blog/microservices/modular-monolith-better-way-build-software) (Bem estruturado, pode durar anos)
- Plataforma de comércio eletrônico - Magento, Shopify.
- Sistema de gerenciamento de conteúdo(CMS) - WordPress, Drupal.
- Componentes em aplicações web
- E Microserviços?
   No livro "Building Microservices: Designing Fine-Grained Systems", Sam Newman argumenta que os microsserviços são uma extensão natural dos princípios de Component-Based Architecture, aplicada ao desenvolvimento de sistemas distribuídos modernos.

  Citação: "Microservices are a form of component-based architecture where the components are services that are independently deployableand scalable."
---
## Layerd & N-Tiers
### Lyered
  É uma abordagem onde o sistema é organizado em camadas,  cada uma com responsabilidades específicas e interações bem definidas. Este estilo promove a separação de preocupações, facilitando o desenvolvimento, a manutenção e a evolução do software.
  Fowler descreve a arquitetura em camadas como um padrão estrutural comum em aplicações empresariais, dividindo a
aplicação em camadas como apresentação, aplicação, domínio e infraestrutura. Ele defende padrões específicos que se encaixam
na arquitetura em camadas, como "Presentation Layer," "Domain Layer" e "Data Source Layer".

  Em resumo, vai possuir uma interação com o usuário, seja ela qual for, vai possuir um domínio e vai ter uma camada de acesso a dados.
  
---
## N-Tiers

  Refere-se à separação física das diferentes camadas da aplicação, onde cada nível pode ser distribuído em diferentes máquinas ou servidores. Esse estilo é focado na distribuição e   escalabilidade do sistema.
  
---
A separação física permite que cada nível seja escalado de forma independente, aumentando a capacidade do sistema de lidar com uma maior carga de trabalho.
