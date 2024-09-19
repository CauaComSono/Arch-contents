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
### Microkernel
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
 - Desenvolvimento independente (Maior serviço) (De times também)
 - Desenvolvimento poliglota
 - Desenvolvimento e escabilidade (Maior serviço)
 - Descrentralização

   O API gateway é basicamente o "Porteiro" sabendo onde cada microserviço está e sabe o ip deles
   Ele fica responsável por saber qual microserviço irá chamar.
   Também faz o _reverse Proxy_ que ele pega a requisição que está caindo nele e joga para o microserviço correto.

   - Cada microserviço tem um banco de dado segregado.

   - Maior ponto negativo é complexidade.
   
![imagem](https://middleware.io/wp-content/uploads/2021/09/How-Microservices-architecture-works-1024x786.jpg)

---
## Trade-Offs
  - Complexidade do gerenciamento
  - Latência na comunicação entre microserviços
  - Consistência de dados
  - Custos operacionais e segurança
    
    [Repo Usando MicroServiços](https://github.com/Sandrolaxx/dfmicroservices)
    
    [4 Exemplos de MicroServiços](https://blog.dreamfactory.com/microservices-examples)

---
## Pipes e Filters
Organiza o sistema como uma série de filtros conectadas por pipes (tubos). Cada filtro é responsável por processar dados, enquanto os pipes transportam os dados entre os filtros. Este estilo é ideal para sistemas que processam dados em etapas sequenciais, como pipelines de processamento de dados. Exemplo classico é o shell do linux: $ ls | grep b | sort -r | tee arquivo.out | wc -l

---
## Representational State Transfer (REST)
É um esilo arquitetural para sistemas distribuídos que utiliza o protocolo HTTP e opera sobre os conceitos de recursos e representações.

Em REST, os recursos são identificados por URLs e manipulados usando métodos HTTP.

---
## Service_oriented Architecture (SOA): 
Estilo arquitetural que organiza o sistema como um conjunto de serviços independentes que se comunicam entre si por meio de interfaces bem definidas. Cada serviço é responsável por uma parte específica da funcionalidade do sistema e pode ser acessado remotamente por outros serviços ou aplicações. Possuem o mesmo banco e são uma parte completa do domínio.

---
# Clean Arch & Hexagonal

## Arquitetura Limpa
Este estilo de arquitetura enfatiza a separação de preocupações e a independência dos frameworks, interfaces de usuário, bancos de dados e outros detalhes externos. Podemos considerar como um avanço da onion architeture.

_"The Clean Architecture is an architectural style that can be applied to a wide range of applications. It emphasizes the separation of concerns, making sure that the business rules are isolated from frameworks, user interfaces, and external agencies"._ (Clean Architecture: A Craftsman's Guide to Software Structure and Design, p. 18).

---
## Hexagonal-Ports and Adapters
Foi proposta por Alistair Cockburn, visa criar sistemas de software que sejam altamente desecoplados e testáveis, permitindo que as partes centrais da aplicação permaneçam independentes de suas interfaces de entrada e saída.

![imagem](https://miro.medium.com/v2/resize:fit:720/format:webp/1*aD3zDFzcF5Y2_27dvU213Q.png)

---
### Comparação entre estilos (Clean Arch x Hexagonal x Onion)
Layered é criticada por focar em banco de dados, causando dependências transitivas, limites confusos e dificuldades na manutenção e testes. Já a arquitetura hexagonal prioriza a lógica de negócio, desenvolvendo-a antes da persistência dos dados. Ela se adapta melhor a aplicativos complexos com componentes adicionais, como APIs REST, evitando dependências excessivas e duplicação da lógica de negócios.

A Arquitetura Limpa coloca a lógica de negócios no centro, com adaptadores de interface ao redor conectando a interface do usuário, banco de dados e outros componentes externos. Todas as dependências do código apontam para o núcleo, seguindo o Princípio de Inversão de Dependência. Arquitetura Hexagonal mapeia-se quase diretamente para a Arquitetura Limpa.

Arquitetura Limpa pode ser vista comouma evolução da Arquitetura Onion e Hexagonal, devido à sua abordagem mais detalhada e abrangente para a organização de sistemas de software.

A Arquitetura Limpa refina e expande os conceitos da Arquitetura Hexagonal, oferecendo uma estrutura clara e sistemática para a construção de aplicações desacopladas, modulares e testáveis.

---
# Serverless
Arquitetura serverless é um modelo de computação em nuvem onde os provedores de nuvem gerenciam a execução do código, alocando dinamicamente os recurso necessários.

Esse modelo permite que os desenvolvedores se concentrem mais na lógica de negócios e menos na infaestrutura, uma vez que tudo isso é rseponsabilidade do provedor de serviços de nuvem.

### Características:
  - Execução sob demendam, escabilidade automática
  - Custo-eficiência, gerenciamento simplificada.
### Funções como Serviço (FaaS)
 - AWS Lambda, Google Cloud Functions, e Azure Functions.
### BackEnd como Serviço (BaaS)
 - Firebase authentication, FireStore e Amazon S3

   Podemos encontrar muitos dos conceitos no [artigo de Mike Roberts](https://martinfowler.com/articles/serverless.html).

---
# Qual o estilo arquitetural correto?
Depende...
Temos de levar em conta o problema que queremos resolver, budget do projeto, senioridade do time, isso também vale para quando buscamos alterar o estilo atual.

---

1º - Quero criar uma nova aplicação web, uma
ferramenta de gestão de projeto, o que seria
interessante ter nela? 

O budget para implementar é relativamente baixo

Deve permitir adicionar novas funcionalidades

Senioridade do time é baixa. 

R: _Microkernel_

---
2º Quero fazer uma API simples com Spring para o PDV de uma loja, qual a melhor escolha?

Projeto pessoal/MVP
Budget baixo

R: _Mvc e monólito_

---
### Padrões Arquiteturais
São soluções recorrentes para problemas específicos de design em um contexto arquitetural. Eles são mais específicos que estilos arquiteturais e fornecem detalhes sobre a implementação.

 - Solucionam problemas especificos.
 -  Guias de implementação.
 -  Reutilização de soluções.

## MVC - Model, View e Controller.
É um padrão de design de software que separa uma aplicação em três partes principais:
### 1° Model (Modelo):
  - Representa os dados e a lógica de negócios.
  - Gerencia o comportamento e os dados da aplicação.
### 2° View (Visão):
  - Apresenta os dados ao usuário.
  - Atualiza a interface do usuário quando o modelo muda.
### 3° Controller (Controlador):
  - Recebe a entrada do usuário.
  - Interage com o modelo e seleciona a visão para apresentar a saída.

### Beneficios:
  - Separação de preocupações: Facilita a manutenção e a escalabilidade
  - Reutilização de código: Componentes podem ser reutilizados em diferentes partes da aplicação.

---
## Plug-ins
Núcleo e plug-ins ou extensões que adicionam funcionalidades. O núcleo fornece a base e a infraestrutura, enquanto os plug-ins fornecem funcionalidades específicas.

Alguns locais citam como estilo arquitetural, porém partilho da visão de que ela como solução não possui "tamanho" suficiente para ser um estilo completo, se enquadrando como padrão que pode ser composto em estilos arquiteturais como o Layered e Componend-based.


Exemplos: Navegadores, IDE’s como Eclipse

[artigo que aborta mais profundamente](https://medium.com/omarelgabrys-blog/plug-in-architecture-dec207291800).

---
## Three-tier
A arquitetura de três camadas é um modelo de arquitetura de software que separa uma aplicação em três camadas físicas distintas: a camada de apresentação (Presentation Tier), a camada de lógica de negócios (Business Logic Tier), e a camada de dados (Data Tier). 

Essas camadas são distribuídas em diferentes servidores ou máquinas para melhorar a escalabilidade, a segurança e a manutenibilidade do sistema.

### Beneficios:
 - Escalabilidade
 - Segurança
 - Manutenibilidade
 - Flexibilidade e reutilização

---
## Publisher-subscriber
Padrão arquitetural que permite que os sistemas de software se comuniquem de forma assíncrona e desacoplada. Nesse modelo, os componentes de software são divididos em dois principais papéis: publicadores (publishers) e assinantes (subscribers). Esse padrão é amplamente utilizado em sistemas distribuídos e arquiteturas orientadas a eventos.

### Beneficios:
 - Desacoplamento: Publishers e subscribers são desacoplados, permitindo que componentes do sistema evoluam independentemente.
 - Escalabilidade: Facilita a escalabilidade, pois múltiplos subscribers podem receber a mesma mensagem sem aumentar a carga no publisher.
 - Flexibilidade: Suporta diversos padrões de comunicação (um-para-n, n-para-n).

---
### Como escolher o padrão correto?
O que faça mais sentido com o estilo, ou estilos de arquitetura utilizados no projeto. Podemos ter um certo relacionamento entre os estilos e seus padrões que possuem mais sinergia.

---
# Design Patterns (Padrões de projeto - Padrões criacionais)

---
## Visão Geral
Padrões de projeto são soluções criadas, já testadas, estruturadas e documentadas por outros desenvolvedores.

Citação: "_Design Patterns are descriptions of communicating objects and classes that are customized to solve a general design problem in a particular context._"
- Gamma et al., 1995, p. 3

---
Os padrões de projeto são isso, eles dão um norte para resolvermos o problema.

Cristopher Alexander mapeou e compreendeu que existiam padrões para vários problemas encontrados.

Um padrão é uma regra de três partes, queexpressa uma relação entre um determinado contexto, um problema e uma solução.

---

De posse desses conhecimentos em 1995 Erich Gamma, John Vlissides, Ralph Johnson e Richard Helm publicaram “Design Patterns: Elements of Reusable Object-Oriented Software”, onde foram descritos 23 padrões que resolviam vários problemas de design orientado a objetos e se tornou um best-seller muito rapidamente. Devido ao seu nome ser muito extenso o livro foi batizado de GoF (Gang of Four).

## Beneficios

### Reutilização de código
Design patterns promoveram a reutilização de soluções testadas, evitando a necessidade de "reinventar a roda" e economizando tempo durante o desenvolvimento.

### Manutenção
O uso de padrões facilita a manutenção do código, pois as soluções são reconhecíveis e compreendidas por desenvolvedores familiarizados com os padrões.

### Comunicação
Ao usar design patterns, desenvolvedores podem se comunicar de maneira mais eficiente, referindo-se a uma solução complexa com um nome simples e amplamente compreendido, como "Factory Method" ou "Observer".

### Escabilidade e flexibilidade
Ajudam a criar sistemas facilmente  estendidos ou modificados à medida que novos requisitos surgem.

---
## Onde não usar?
Mesmo sendo muito úteis, eles não devem ser aplicados de maneira discriminada:

  - Complexidade desnecessária: Aplicar um pattern em um problema que pode ser resolvido com uma solução mais simples pode adicionar complexidade desnecessária no código.
  - Problemas mal definidos: Não tente forçar um padrão em um problema que não é claramente compreendido. Primeiro, compreenda completamente o problema antes de buscar uma solução padrão.
  - Overengineering: Evite overengineering, que é a tendência de criar uma solução mais complexa do que o necessário, por aplicar padrões de design onde não são necessários.
---
### Três categorias de Patterns
 - Criacionais: Tratam do processo de criação de objetos, promovendo a flexibilidade e a reutilização de código. Ajudam a gente a instanciar.
 - Estruturais: Lidam com a composição de classes ou objetos, formando estruturas maiores de forma eficiente.
 - Comportamentais: Lidam com a comunicação entre os objetos e com a maneira como eles se interagem e suas rensponsabilidades.

---

## Singleton
É um padrão de design criacional que garante que uma classe tenha apenas uma única instância e fornece um ponto global de acesso a essa instância.

Ele é útil em situações onde é importante que apenas um objeto de uma classe seja criado, como em gerenciadores de recursos, conexões de banco de dados ou configurações globais de uma aplicação.

Características:

 - Única instância: Apenas uma instância da classe é criada durante o ciclo de vida da aplicação.
 - Controle de acesso: A classe controla como e quando sua única instância é criada.
 - Ponto de acesso global: Fornece uma forma globalde acessar essa instância única.

[Refactoring Guru](https://refactoring.guru/design-patterns). Pode ajudar muito nos estudos

Resolve problema de uma única classe.

---
## Abstract Factory
Padrão que permite criar famílias de objetos relacionados ou dependentes sem especificar suas classes concretas. 

Ele define uma interface para criar diferentes tipos de objetos (como botões e checkboxes), permitindo que o cliente trabalhe com essas famílias de objetos de forma independente de suas implementações específicas.

Características:

 - Criação de famílias de objetos: Permite criar grupos de objetos relacionados que devem ser usados juntos.
 - Independência de implementação: O cliente usa interfaces abstratas, sem saber quais classes concretas estão sendo instanciadas.
 - Flexibilidade: Facilita a troca entre diferentes famílias de objetos, como mudar a interface do usuário de Windows para macOS sem alterar o código cliente.

Ele instancia várias fámilias de classes de uma única vez;
Definimos uma interface chamada Factory;

---
## Factory Method 
Define um método para criar objetos em uma classe, permitindo que as subclasses decidam qual classe concreta será instanciada.

Em vez de instanciar objetos diretamente com new, o Factory Method delega essa responsabilidade para métodos especializados, oferecendo flexibilidade para criar diferentes tipos de objetos.

Características :

 - Delegação da criação: Define um método para criar objetos, delegando às subclasses a decisão de qual classe concreta instanciar.
 - Desacoplamento: Desacopla a criação de objetos da sua utilização, facilitando a adição de novas classes sem modificar o código existente.
 - Flexibilidade: Permite que uma classe defina a interface de criação, enquanto subclasses concretas implementam a lógica específica para diferentes tipos de produtos.

---
## Prototype
Permite criar novos objetos copiando instâncias existentes (protótipos), ao invés de instanciar novos objetos do zero. 

Ele é útil quando a criação direta de um objeto é cara (em termos de tempo ou recursos) ou quando você deseja evitar subclasses para criar diferentes instâncias.

Características:

 - Clonagem de objetos: Cria novos objetos copiando (clonando) instâncias existentes, sem depender de classes concretas.
 - Flexibilidade: Permite criar objetos complexos com uma configuração inicial específica, evitando a repetição de código ou configurações.
 - Independência de implementação: Você pode criar novos objetos sem depender de suas classes concretas, utilizando cópias de protótipos existentes.

---

## Builder 
Permite a construção de objetos complexos passo a passo. Ele separa o processo de construção do objeto da sua representação, permitindo criar diferentes representações do mesmo objeto.

Características:

 - Construção passo a passo: Permite criar objetos complexos em etapas, adicionando um nível de controle sobre o processo de construção.
 - Separação de preocupações: Separa a lógica de construção do objeto (Builder) de sua representação final, permitindo que o mesmo processo construa diferentes tipos de objetos.
 - Flexibilidade: Facilita a criação de objetos com configurações variadas sem precisar de múltiplos construtores ou parâmetros opcionais.

---
## Padrões de projetos estruturais

São descritas como soluções para problemas relacionados à composição de classes e objetos para formar estruturas maiores e mais flexíveis. 

Esses padrões ajudam a organizar e otimizar o design de sistemas de software, facilitando como os componentes interagem e se conectam.

Principais benefícios:
 - Flexibilidade na composição de objetos
 - Desacoplamento
 - Manutenção e extensão
 - Simplificação de complexidade

---
Citação:
 "_Structural patterns deal with object composition, creating relationships between objects to form larger structures. These patterns help ensure that if one part of a system changes the entire system does not need to change. They simplify the design by decoupling components, making the system more flexible and easier to maintain._" - Gamma et al., 1995, p. 25-26

 ---

 ### Adapter 
 Permite que interfaces incompatíveis trabalhem juntas. Ele converte a interface de uma classe em outra interface esperada pelos clientes. 

Assim, o Adapter atua como um intermediário que traduz as chamadas feitas pelo cliente para a interface da classe que não é compatível.

Usado quando é necessário integrar sistemas legados com novos sistemas ou quando se deseja adaptar uma API para uma nova interface.

---
### Bridge
Desacopla uma abstração da sua implementação, permitindo que ambas evoluam independentemente. 

É usado quando você quer separar uma abstração (a ideia principal ou conceito) de sua implementação concreta (a forma como o conceito é realizado). Isso é útil para evitar que mudanças em uma parte da estrutura (como uma classe) causem impacto na outra parte.

---
### Composite
Permite que você trate objetos individuais e composições de objetos de forma uniforme.

Isso é útil quando você tem uma estrutura hierárquica de objetos, como uma árvore, onde cada nó pode ser um objeto simples ou um grupo de objetos.

Usado quando precisar representar hierarquias de objetos, como estruturas de diretórios dearquivos ou interfaces gráficas complexas.

---
### Decorator
Permite adicionar responsabilidades a um objeto dinamicamente, sem alterar o código da classe original. Ele usa um conjunto de classes de decoração que envolvem o objeto original, adicionando funcionalidades adicionais. Utilizado para adicionar funcionalidades a objetos de maneira flexível e extensível, como adicionar estilos de janela em um sistema de GUI.
