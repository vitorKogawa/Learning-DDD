# Learning-DDD
Repositório dedicado a estudar mais sobre a abordagem DDD para desenvolvimento de soluções, material com base no curso ministrado por Alexande Daccas, no curso : "Desenvolvendo sua aplicação com C# usando DDD" na plataforma Digital Innovation One (DIO) 

# DDD (Domain Driven Design)

"É uma abordagem de design de software disciplinada que reúne um conjunto de conceitos, técnicas e princípios para construção de softwares baseados em um modelo de domínio."

#### Domínio: 

É todo e qualquer conhecimento em uma determinada área.

## Origem do DDD

Surgiu através do livro de Eric Evans , dono da DomainLanguage que é uma empresa especializada em treinamento e consultoria para desenvolvimento de software.

![Domain-Driven Design: Tackling Complexity in the Heart of Software |  Amazon.com.br](https://images-na.ssl-images-amazon.com/images/I/51sZW87slRL._SX375_BO1,204,203,200_.jpg)

O livro é um grande catálogo de padrões baseados em experiências do autor ao longo de mais de 20 anos de desenvolvimento de software envolvendo a utilização da técnicas relacionadas a orientação a objetos.



## Principais conceitos do DDD

**Alinhamento do código com o negócio**

Contato dos desenvolvedores e especialistas na área em que a solução será implementada, para que assim todos estejam falando na mesma linguagem com relação a termos e conceitos específicos.

![Linguagem ubíqua e Contexto Delimitado | by Mayara Shoji | Bar8](https://miro.medium.com/max/1382/1*WkpiFbNOrFk91DdEqN3Tzw.png)



**Favorecer reutilização**

Blocos de construção podem e devem ser reaproveitados durantes o desenvolvimento da solução.

**Mínimo de acoplamento**

Com um modelo bem feito e organizado e totalmente possível que as diversas partes do sistema se comuniquem com o mínimo ou quase nenhum nível de dependência entre elas.

**Independência da tecnologia**

DDD não foca na tecnologia que será utilizada para implementação da solução e sim nas regras de negócio, a tecnologia a ser escolhida pela equipe de desenvolvimento é muito importante , porém não é o foco do DDD.

## Criando modelo de domínio (MDD)

A ideia por trás de MDD é a de que o seu modelo abstrato deve ser uma representação perfeita do seu domínio. 

- Tudo que existe no seu negócio deve aparecer no modelo.
- Só aparece no modelo aquilo que está no negócio

- O desenho do modelo é criado junto aos:

  - Especialistas

  - Desenvolvedores

  - Analistas

  - Arquitetos

    Sempre utilizando a linguagem ubíqua para que todos tenham o e mesmo entendimento.

- O processo de maturação de um sistema desenvolvido usando MDD deve ser contínuo, pois o modelo servirá para criação do código e, ao mesmo tempo, o código ajuda a aperfeiçoar o modelo.

## Blocos de construção do MDD

A separação do domínio das demais partes do sistema pode ser feita através de uma arquitetura baseada nas seguintes camadas:

- **Interface do usuário**
  - Exibição das informações do sistema para o usuário
  - Interpretar comandos do usuários
- **Aplicação**
  - Não possui lógica de negócio
  - Conectar a camada de usuário as camadas inferiores da solução
- **Domínio**
  - Representação dos:
    - Conceitos
    - Regras de negócio
  - Onde se concentra toda a abordagem DDD
- **Infra-estrutura**
  - Dar suporte a todas as camadas superiores
  - Camada responsável por:
    - Persistência dos dados
    - Conexões com banco de dados
    - Envio de mensagens por redes
    - Gravação e leitura de discos
    - etc;





### Esquema DDD

![DDD – Introdução a Domain Driven Design | AgileAndArt](https://lh3.googleusercontent.com/proxy/9NNnYFtOnmRQYPn1GZp5HZgEVqM0YvugULNQkex3Fw-fHwdWFeFz3IhYhdjGHID_uFrnmpZeW83PcxHNMY99mY6J_iUAjdl5jSn_r3GokPUrio9mXc9SFN9lLEDWYyb8ezpVxZ10hBQpT5o1pM3xU2G8kO4)



## Regras para modelagem de domínio

- **Entidades**

  Classes de objetos que necessitam de uma identidade, geralmente são elementos do domínio que possuem um ciclo de vida.

- **Objetos de Valores**

  São objetos que só carregam valores, porém não possuem distinção de identidade, alguns bons exemplos seriam os seguinte:

  - Strings
  - Números
  - Cores

- **Agregados**

  Compostos de entidades ou objetos de valores que são encapsulados numa única classe.

- **Fábricas**

  Classes responsáveis pelo processo de criação dos agregados ou dos objetos de valores.

- **Serviços**

  Classes que contém lógica de negócio, mais que não pertence a nenhuma Entidade ou Objetos de valores.

  :warning:Serviços não guardam estado

- **Repositórios**

  Classes responsáveis por administrar o ciclo de vida de outros objetos como:

  - Entidades
  - Objetos de Valores
  - Agregados

  Repositórios centralizam operação como: Criação, Alteração, Remoção e/ou Exclusão de objetos

- **Módulos**

  Abstrações que têm por objetivo agrupar classes por um determinado conceitos do domínio.

## Inversão de controle 

- inversão da dependência , onde todas as camadas começam a depender do domínio.
- Para que isso funcione é necessário a criação das interfaces que vão ficar no **domínio**, assim invertendo a dependência entre as camadas.
- TUDO tem que ser feito através de interfaces:
  - Garante o baixo acoplamento

## Análise da estrutura do projeto para entender um pouco mais como funciona uma aplicação que utiliza a abordagem DDD para o desenvolvimento.

- **Startup.cs**: injeção de todas as dependências do projeto.
- **Controller:** Chamando a camada de serviço para executar todos os métodos que precisam ser executados, nenhum regra de negócio precisa ser implementada aqui 


