# Arch-contents

## Estilos arquiteturais
Uma arquitetura é a estrutura global (Que emgloba todas as arquiteturas)

---

**O que é Design?** *O design é o micro, como estruturar as classes, já a arquitetura é o macro*

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

---
# Tier, layer?
Em discussões de arquitetura de três camadas(tier), o nível é frequentemente usado de forma intercambiável e equivocadamente pela camada, como um 'nível de apresentação' ou 'nível lógico de negócios'. Não são o mesmo!

## Tier(Nível)
Refere-se normalmente a uma divisão física do software executada em infraestrutura separada das outras divisões.

## Layer(Camada)
Se refere a uma divisão lógica da sua aplicação, sendo normalmente executada em uma única infra e processos distintos.

---

## Event-Driven-Architeture

### Event-Drive-Achitetura (EDA)

É um estilo arquitetetural em que os componentes do sistema se comunicão através de geração e manipulação de eventos. Um evento é uma mudança significativa de estado ou ocorrência que pode ser capturada e respondida por outros componentes do sistema.

- Event Producers (Publicadores): Geram e emitem eventos.
- Event Consumers (Assinantes): Recebem e processam os eventos.
- Event Channel (Broker de Mensagem): Middleware que gerencia a distribuição de eventos dos publicadores para os assinantes
- Event Processors: Componentes que processam eventos e podem gerar novos eventos.
  
  Exemplo: [10 exemplos de utilização de EDA no setor de logística](https://nexocode.com/blog/posts/event-driven-architecture-examples-in-logistics-apache-kafka-to-handle-supply-chain-network/) (Utilizando o Apache Kafka)
  
---
### Mikroernel
Estilo arquitetural que busca manter o núcleo do sistema o mais simples e reduzido possível, delegando a maioria das funcionalidades para módulos ou serviços externos adicionados ao núcleo.

### Características:
  - Núcleo Mínimo: Apenas as funcionalidades essenciais.
  - Serviços e Módulos: Funcionalidades adicionais.
  - Comunicação: Normalmente feita por meio de chamadas de sistema ou mensagens.

Exemplos:
Sistemas operacionais: Minix, QNX.
FrameWorks: Eclipse IDE.

---
### Citação
_"The microkernel architecture style involves designing a minimal core system with additional features provided by separate modules or services. This approach is considered a style because it defines a high-level organization of components and their interactions, rather than a specific implementation pattern."_  (Software Architecture in Practice, P. 207)

---
## MicroServices
É um estilo arquitetural que estrutura uma aplicação como um conjunto de pequenos serviços independentes, cada um executando um processo único e comunicando-se por meio de APIs bem definidas. Cada microserviços é desenvolvido, implantado e escalado de forma independente, permitindo uma maior flexibilidade e agilidade no desenvolvimento e na manutenção do software.

### Características:
 - Desenvolvimento independente (Maior serviço)
 - Desenvolvimento poliglota
 - Desenvolvimento e escabilidade (Maior serviço)
 - Descrentralização

   O API gateway é basicamente o "Porteiro" sabendo onde cada microserviço está e sabe o ip deles
   Ele fica responsável por saber qual microserviço irá chamar.
   Também faz o _reverse Proxy_ que ele pega a requisição que está caindo nele e joga para o microserviço correto.

   - Cada microserviço tem um banco de dado segregado.
     
![imagem](https://middleware.io/wp-content/uploads/2021/09/How-Microservices-architecture-works-1024x786.jpg)

---
## Trade-Offs
  - Complexidade do gerenciamento
  - Latência na comunicação entre microserviços
  - Consistência de dados
  - Custos operacionais e segurança
    
    [Repo Usando MicroServiços](https://github.com/Sandrolaxx/dfmicroservices)
    
    [4 Exemplos de MicroServiços](https://blog.dreamfactory.com/microservices-examples)
