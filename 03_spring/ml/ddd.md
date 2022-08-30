<h1>Introdução ao Domain Driven Design</h1>

**Domain Driven Design (DDD)** ou **Design Orientado ao Domínio**, é uma abordagem de Desenvolvimento de Software, que visa corresponder ao modelo mental do Domínio do problema que estamos trabalhando para criar uma solução computacional. O conceito de DDD é uma abordagem de modelagem de software que segue um  conjunto de boas práticas com o objetivo de facilitar a implementação de regras complexas e processos de negócios que tratamos como o Domínio da aplicação.

O conceito de ***Domain Driven Design*** como o próprio nome já diz é um assunto que se refere ao ***Design de Código***. Esse design é guiado pelo ***Domínio*** de sua aplicação, ou seja uma ***modelagem de software*** focada em resolver os problemas de complexidade das ***Regras de Negócio***.

> **Regras de negócio:**  O termo regras de negócio refere-se às **diretrizes que definem ou restringem as ações, mostrando como os Métodos devem  funcionar, o que deve ser checado em cada Método e quais são os limites  da aplicação**. Essas regras são importantes para que a pessoa  desenvolvedora tenha uma visão clara do que deve ser feito, como e por qual razão.

*“Domain Driven Design é um conjunto de princípios com foco no Domínio, na exploração de modelos de formas criativas e definição de uma linguagem Ubíqua, baseada em um contexto delimitado.”*

>  **Linguagem Ubíqua** é a linguagem falada no dia dia, no contexto da empresa. É a  linguagem que utiliza as terminologias da realidade do negócio .

O DDD não é uma receita pronta sobre  como desenvolver uma arquitetura baseada em camadas. O DDD não depende de nenhuma tecnologia que você irá utilizar para fornecer sua  aplicação, ou seja, ele é agnóstico. 

*“Toda Arquitetura de Software é Design, mas nem todo o Design é uma Arquitetura”* – **Grady Booch**

> **Arquitetura de software:** É o processo de converter  características do software como flexibilidade, escalabilidade,  viabilidade, reutilização e segurança em uma solução estruturada que  atenda às expectativas técnicas e de negócios. 
>
> **Design de software:** Enquanto a arquitetura do software é responsável pelo esqueleto e pela  infraestrutura de alto nível de um software, o design do software é  responsável pelo design do nível de código, como o que cada módulo está  fazendo, o escopo das classes e os objetivos dos Métodos, entre outros.

<h2>1. Domínio</h2>

O Domínio é o coração do negócio em que você está trabalhando. O Domínio é baseado em um conjunto de ideias, regras, conhecimentos e processos de negócio. Sem um domínio todo o sistema, todos os processos, não servirão para nada. Sempre que falamos em domínio, estaremos falando da razão, do objetivo, da justificativa daquele software existir. 

Quando falamos em DDD (Domain Driven Design), não falamos apenas em  desenvolver um software, mas sim em entender a modelagem do projeto como um todo. Se você não souber modelar o software, não conseguirá fazê-lo crescer e ser mantido a médio e longo prazo.

<h2>2. Exploração de Modelos e Formas Criativas</h2>

O DDD preza que as pessoas desenvolvedoras façam parte do processo, entendendo o  negócio e todos os seus modelos nos diferentes ângulos e não somente participando de reuniões com Especialistas ou com o seu Time de Desenvolvedores.

Antigamente, a pessoa desenvolvedora se preocupava apenas com a codificação do software. O novo perfil das pessoas desenvolvedoras exige que todo o Time de Desenvolvedores participe de todo o processo, desde o levantamento de requisitos até o contato com o Domain Expert, desta forma a base de conhecimento dos integrantes do Time de Desenvolvedores não pode se limitar apenas ao conhecimento técnico. Entre as habilidades recomendadas, podemos destacar:

- Comunicação

- Criatividade
- Senso Crítico
- Proatividade
- Resiliência

<h2>3. A História do DDD</h2>

O DDD não é um conceito moderno, uma ideia nova recém-descoberta. Ele nasceu entre os anos 50 e 60 com o  surgimento dos primeiros conceitos da Orientação a Objetos, criados para solucionar problemas muito complexos, no qual uma abordagem procedimental não era suficiente.

No final da década de 60, surge o que muitas pessoas consideram ser a primeira linguagem Orientada a Objetos (POO, Programação Orientada a Objetos - *Object-Oriented Programming*), o Simula 67, que apresentava um resumo de todos os conceitos e experiências reunidos até o momento naquela direção.

<div align="center"><img src="https://i.imgur.com/CQv6VAN.png" title="source: imgur.com" /></div>

Anos mais tarde, em 1982, surge um novo estágio evolutivo da POO, a Análise e Design Orientado a Objetos (também conhecido como ADOO, em inglês *object-oriented analysis and design).*

Em 2003, surge um novo marco e um novo termo: **DDD - Domain Driven Design**, que reúne um conjunto das melhores práticas, além de novos conceitos, gerando uma estruturação revolucionária do ADOO.

Se considerarmos todos estes conceitos, estamos falando em pelo menos **50 anos de sabedoria e experiência da comunidade de desenvolvedores de software**, sobre como lidar com **domínios de problemas complexos**.

<div align="left"><img src="https://i.imgur.com/l2A1aPc.png" title="source: imgur.com" width="35px"/><a href="https://www.wikiwand.com/pt/Simula_67" target="_blank"><b>Linguagem de Programação - Simula 67</b></a></div>

<br />

<h2>4. Como utilizar o DDD</h2>

Embora o DDD não possua um modelo rígido ou um passo a passo de como implementar, podemos tentar criar um resumo básico inspirado nos seus princípios e boas práticas.

<h3>👣 Passo 01 – Entender o Negócio</h3>

Sem entender o negócio não tem como implementar o DDD. Antes de iniciar qualquer projeto é fundamental compreender como o Negócio funciona.  A análise do negócio possibilita entender a estrutura, as políticas e as operações de uma organização e recomendar soluções para que uma organização atinja seus objetivos. 

Para entender o negócio é importante conversar com as pessoas envolvidas no processo, sejam pessoas colaboradoras da empresa ou pessoas desenvolvedoras, através de entrevistas, reuniões e observação da rotina da empresa.  As pessoas envolvidas no projeto, basicamente são classificadas em duas categorias:

- **Domain Experts**, ou Experts do Negócio, que são as pessoas que entendem do negócio, que acumularam um grande conhecimento  e que vão guiar o time de desenvolvimento no projeto tirando dúvidas, definindo regras, processos e nomeando os termos a serem utilizados.
- O **Time de Desenvolvimento**, que são as pessoas que irão desenvolver o software, ou seja, um grupo multidisciplinar de pessoas, responsável por realizar o trabalho de desenvolvimento do produto de ponta a ponta. 

<br />

<h3>👣 Passo 02 – Definir a Linguagem Ubíqua</h3>

Um dos pontos mais importantes do DDD, onde 99% das pessoas desenvolvedoras acabam ignorando, é falar e extrair a **Linguagem Ubíqua**.

**Linguagem Ubíqua é a linguagem falada no dia dia, no contexto da empresa. É a  linguagem que utiliza as terminologias da realidade do negócio .**

Como citado anteriormente, é preciso conhecer a linguagem utilizada pelas pessoas envolvidas no negócio. Ignorar esta linguagem é o primeiro grande passo para o fracasso do software, por este motivo é importante familiarizar-se com a linguagem Ubíqua do negócio. 

A Linguagem Ubíqua deve ser elaborada pelo Time de Desenvolvimento em conjunto com os Experts no negócio.

<div align="center"><img src="https://i.imgur.com/MZhCw00.png" title="source: imgur.com" /></div>

Lembre-se que o Time de Desenvolvimento falará diretamente com os **Domain Experts**, que é a  pessoa que trabalha na empresa e conhece o negócio a fundo. Esta pessoa utiliza esta linguagem no seu dia a dia, assim como nós falamos sobre código no nosso dia a dia, logo para compreender os requisitos e as regras do negócio, as pessoas desenvolvedoras precisa se familiarizar com os conceitos e os termos utilizados pelo Domain Expert.

Um processo importante na definição da Linguagem Ubíqua do negócio é definir um Glossário das palavras. Observe a lista de palavras abaixo:

- Carregador de celular
- Usuário/Cliente
- Perfil
- Estação
- Localização
- Meu históricol
- Pagamento

Algumas destas palavras podem ter vários significados dependendo do contexto, por isso é importante definir o significado destas palavras de acordo com o contexto da aplicação. Se levarmos em consideração o contexto de **aluguel de carregadores de celular portátil**, como um serviço oferecido nas Estações de Trem e Metrô, que são reservados através de um aplicativo, podemos definir o seguinte Glossário de palavras:

- **Carregador de celular** – Objeto que será alugado, cujas características serão armazenadas na aplicação.
- **Usuário/Cliente** – Pessoa que alugará o carregador de celular, cujos dados serão armazenados na aplicação.
- **Perfil** – Espaço na aplicação onde a pessoa visualiza seus dados e poderá editá-los ou excluir a conta.
- **Estação** – Local físico onde a pessoa poderá retirar o seu carregador portátil, cujos dados ficam armazenados na aplicação.
- **Localização** – Entidade responsável por verificar a localização da pessoa usuário no momento da retirada do carregador, ou seja, a estação em que foi retirado e entregue o carregador.
- **Meu histórico** – Lista o histórico de aluguéis da pessoa usuária com localização da estação de retirada e de entrega e data/hora do aluguel.
- **Pagamento** – Parte em que o usuário efetua o pagamento do aluguel do carregador.

Uma vez definido o Glossário, este será utilizado até o final do projeto, dentro de um ou mais contextos.

<br />

<h3>👣 Passo 03 – Delimitar os Contextos da aplicação</h3>

Os **Contextos Delimitados** ou **Bounded Contexts**, delimita os contextos de atuação da sua aplicação. Cada contexto possui suas responsabilidades claramente definidas que por sua vez possuem a sua própria **Linguagem Ubíqua**. A utilização de histórias e levantamento do escopo do projeto com o Domain Expert auxilia no processo de delimitação dos contextos.

<div align="center"><img src="https://i.imgur.com/p0XetJ9.png" title="source: imgur.com" /></div>

Na imagem acima vemos uma abstração dos Contextos delimitados. 

Para encontrar os Contextos Delimitados é importante criar uma descrição detalhada de cada história, ou seja, como funcionará cada processo. Veja um exemplo abaixo:

**História: *Alugar um carregador de celular portátil***

1. Criar uma conta no aplicativo.
2. Fazer login no aplicativo.
3. Adicionar seus dados pessoais e salvar em seu *Perfil*.
4. Habilitar o GPS para compartilhar a sua localização com o aplicativo. 
5. Visualizar uma mensagem de confirmação se a *Estação* em que se localiza corresponde à captada pelo GPS. 
6. Habilitar a câmera para captar os dados do carregador portátil via QR Code.
7. Visualizar mensagem de confirmação de dados coletados. 
8. Visualizar tela para preenchimento das informações de *Pagamento*. 
9. Inserir as informações de *Pagamento*.
10. Visualizar mensagem de confirmação do carregador portátil liberado.

Com os itens acima, é possível delimitar todos os contextos da aplicação, as entidades envolvidas em cada um e as ações (Métodos) que o aplicativo irá realizar.

<br />

<h3>👣 Passo 04 – Modelagem Estratégica</h3>

A **Modelagem Estratégica** é a definição formal dos contextos que utilizaremos no sistema. Neste momento faremos a representação gráfica dos nossos domínios e classificar cada um deles, como mostra a imagem abaixo:

<div align="center"><img src="https://i.imgur.com/tRE6W9z.png" title="source: imgur.com" /></div>

Os itens acima são os contextos delimitados, que têm as suas Regras, Métodos e Linguagem Ubíqua própria. Observe que cada contexto é chamado de **Domínio** e foi classificado pelos seguintes critérios:

**Domínio principal:** quando o Domínio é a razão de existir do sistema proposto, ou seja, sem ele o software não existe. Num sistema de aluguel de carregadores de celular portátil, sem o Domínio carregador, o serviço não existe.

**Domínio genérico (Subdomínio):** quando o Domínio ajuda em todo o processo e faz com que o domínio principal funcione. ele é chamado de genérico porque trabalha de forma independente e pode servir para diversas coisas, não somente para um único propósito. Pagamento é um bom exemplo, pois ele não se limita apenas ao pagamento do carregador.

**Domínio auxiliar:** pode até ser confundido com domínio genérico, mas não é, pois ele auxilia o sistema como um todo, inclusive os domínios genéricos a funcionarem. Autenticação, que é responsável pelo login do usuário no sistema é um bom exemplo.

Resumindo, quando conseguimos entender quais os contextos e tipos de domínios que  temos na aplicação e como eles podem se relacionar, ficará muito mais fácil o desenvolvimento da aplicação. Observe que nesta etapa o nível de detalhamento é muito maior do que na etapa anterior.

<h3>👣 Passo 05 - Context Map</h4>


O **Context Map** ou **Mapa de contexto** é o mapeamento dos Contextos Delimitadores, ou seja, a representação Gráfica dos Contextos Delimitadores e as relações entre eles.

<div align="center"><img src="https://i.imgur.com/9jt3sXw.png" title="source: imgur.com" /></div>

Observe que nesse Mapa de Contexto existe a relação entre domínios principais e domínios genéricos. Os domínios principais são **upstream**, ou seja, **têm prioridade em relação aos genéricos**, que são **downstream**. Isso significa que na ordem de prioridade, quando alguma coisa mudar, será  prioritariamente do lado dos domínios genéricos. 

Já na relação entre domínios genéricos, **prevalece o que nós não temos autonomia para alterar**. Observe que nas relações **perfil/pagamento**, **estação/localização** e **conta/autenticação**, nós não  temos controle sobre a API de pagamento e sobre a API do Google Maps, assim como não temos a garantia de que o usuário será autenticado, logo a relação é **simultaneamente upstream/downstream**. Neste caso, chamamos de **Relação Conformista**. 

O que podemos fazer é criar uma **Camada  anticorrupção** para não termos que refazer todo o processo novamente, caso haja alguma alteração no meio do caminho. Em relação a autenticação temos um núcleo compartilhado onde todos poderão acessar esse processo. 

> **Camada anticorrupção:** É um intermediador, que de maneira isolada permite apenas a troca de dados que sejam válidos entre os dois sistemas, prevenindo que não dependam do design um do outro.

Observando esse Mapa de contextos, concluímos que o DDD é uma questão de relacionamento e de entendimento de linguagem ubíqua, assim como o  funcionamento dos contextos e seus relacionamentos.

<br />

<h3>👣 Passo 06 - Definir a Arquitetura</h3>

Após a conclusão do Mapa de contexto é necessário definir qual a Arquitetura de Software será utilizada. Cada contexto pode possuir uma  arquitetura independente dos demais ou a combinação de duas ou mais arquiteturas. O DDD não impõe o mesmo estilo arquitetural para todos os contextos, é a análise do contexto que indica qual a melhor opção.

O DDD não prega a necessidade de uma  arquitetura específica, ou seja, o arquiteto tem a liberdade de definir o melhor estilo  arquitetural para atender a necessidade da aplicação.

Existem diversos Modelos de Arquitetura de Software, entre os quais podemos citar:

- MVC (Model - View - Controller)

- Arquitetura REST
- Arquitetura Onion
- Arquitetura Hexagonal
- Microsserviços
- Arquitetura em Camadas

Existem outras Arquiteturas que podem ser utilizadas. Aqui estamos dando destaque as mais utilizadas no Mercado atualmente. Uma pessoa arquiteta de software deve conhecer as diversas Arquiteturas e principalmente saber reconhecer onde e quando devem ser utilizados.

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://github.com/rafaelq80/cookbook_spring/blob/main/03_spring/01.md#4-arquitetura-mvc-" target="_blank"><b>Modelo MVC (Model - View - Controller)</b></a></div>

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://github.com/rafaelq80/cookbook_spring/blob/main/03_spring/01.md#3-api-rest" target="_blank"><b>Arquitetura REST</b></a></div>

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://medium.com/p/551f460c3b2c" target="_blank"><b>Artigo: Arquitetura Onion: Definição, Camadas e Benefícios.</b></a></div>

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://github.com/rafaelq80/cookbook_nest/blob/main/03_nest/01.md#arquitetura-hexagonal" target="_blank"><b>Arquitetura Hexagonal</b></a></div>

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://medium.com/@marcelomg21/arquitetura-de-microsservi%C3%A7os-bc38d03fbf64" target="_blank"><b>Artigo: Arquitetura de Microsserviços</b></a></div>

<div align="left"><img src="https://i.imgur.com/XtXfL8a.png" title="source: imgur.com" width="25px"/><a href="https://guia.dev/pt/pillars/software-architecture/layers.html#" target="_blank"><b>Arquitetura de Camadas (Layer)</b></a></div>

<br />

<h3>👣 Passo 07 - Modelagem Tática</h3>

A **Modelagem Tática** está relacionada com os blocos de construção da DDD, ou seja, um conjunto de  recursos técnicos usados na construção do *Modelo de domínio* do negócio.

Se tratando de DDD, geralmente se utiliza o padrão **Domain Model Pattern**, que é uma abordagem de como escrever as classes que vão mapear os modelos do mundo real e implementar os comportamentos do negócio. O Domain Model Pattern deve ser isolado dos detalhes da sua arquitetura como persistência (Banco de dados), Linguagem, Framework, entre outros. 

<div align="center"><img src="https://i.imgur.com/VFPZt2R.png" title="source: imgur.com" /></div>

Conforme imagem acima, o **Domain Model Pattern** pode ser dividido em dois grupos:

**1. Modelos de Domínio**

**Modelo de Domínio** ou **Domain Models**, que mantém o conhecimento estruturado do problema a ser resolvido com o  software, representando o vocabulário e conceitos-chave do domínio, identificando os relacionamentos entre todas as entidades, atuando como uma ferramenta de comunicação, em conjunto com a linguagem ubíqua.

Um Modelo de Domínio é composto pelos seguintes componentes:

- **Entidades (Entities):** é um objeto com uma identidade exclusiva que persiste ao longo do tempo. No nosso aplicativo exemplo, clientes e contas seriam entidades.
- **Objetos de valor (Value Objects):** são entidades imutáveis, um exemplo é o endereço de uma Estação de Trem ou Metrô.
- **Agregações (Aggregates):** são compostos por uma entidade ou um conjunto de entidades e Value  Objects que compartilham um mesmo contexto. Por exemplo, o pagamento e  uma transação realizada.

**2. Serviços de Domínio**

**Serviço de Domínio** ou **Domain Services**, que representa  uma estrutura sem estado que fornece comportamentos do mundo real dos  negócios. 

Um Serviço de Domínio é composto pelos seguintes componentes:

- **Repositórios (Repositories):** fazem a comunicação com o banco de dados e garantem a persistência dos dados.
- **Serviços (Services):** são objetos sem estado que executam operações específicas de domínio que podem envolver outros objetos de domínio. 

Resumindo...

<div align="center"><img src="https://miro.medium.com/max/1400/1*B4dzWNEPBnqK5jtuIAgVYQ.png" title="source: imgur.com" /></div>

<br />

<h2>5. Quais as vantagens do Domain Driven Design?</h2>

- Iterações (ciclos) de desenvolvimento mais rápidos
- Alta colaboração entre membros do time 
- Torna o código reutilizável e legível 
- Facilita a manutenção graças a definição da complexidade dos limites.

<br />

<h2>6. Quais as desvantagens do Domain Driven Design? </h2>

Cada projeto é único e deve ser estudado caso a caso, mas é importante levar em consideração as desvantagens nos contextos de: 

- **Complexidade técnica:** quando as tecnologias  envolvidas já são muito complexas e envolve um esforço grande do time  para refatorar o que existe com DDD. 
- **Complexidade de domínio:** quando existem muitos subdomínios dentro de um outro, e a manutenção  de uma funcionalidade simples exige mexer em muitos subdomínios. 

<h2>7. Quando devo utilizar o DDD?</h2>

DDD é uma filosofia de desenvolvimento voltada para domínios de negócio complexos. Envolve um conjunto de práticas de entendimento do negócio, comunicação, colaboração, e desenvolvimento de uma solução emergente que reflita o domínio no próprio código. Para ajudar a descobrir se você deve ou não implementar o DDD no seu projeto, utilize o **DDD Score Card** (tabela abaixo). 

A ideia é bem simples, a primeira coluna descreve seu projeto, em seguida o número de pontos que devem ser  acumulados, a última coluna descreve algumas observações. Se no final a **somatória dos pontos for igual ou maior que 7 considere seriamente implementar o DDD em seu projeto**.

| **Se o seu Projeto…**                                        | **Pontos** | **Pensamentos de Suporte**                                   |
| ------------------------------------------------------------ | :--------: | ------------------------------------------------------------ |
| Se sua aplicação for completamente centrada em dados e se qualificar verdadeiramente para uma solução CRUD, em que cada operação é basicamente uma consulta simples de banco de dados  para criar, ler, atualizar ou excluir, você não precisa do DDD. |   **0**    | Um sistema totalmente baseado na implementação de vários CRUD's não precisa de um modelo para projetos complexos como o DDD. |
| Se seu sistema exigir apenas 30 ou menos operações de  negócio, ele provavelmente é bem simples. Isso significa  que a aplicação não teria um total de mais de 30 histórias de usuário ou fluxos de caso de uso, com cada um desses fluxos tendo apenas uma  lógica mínima de negócio. Se você puder desenvolver de forma rápida e facilmente esse tipo de aplicação, o sistema provavelmente não precisará usar o DDD. |   **1**    | Neste exemplo estamos falando de 25 a 30  únicos métodos de negócio, não de 25 a 30 interfaces de serviço completas, cada uma com vários métodos, o que seria um cenário complexo. |
| Em algum lugar no  intervalo entre 30 e 40 histórias de usuário ou fluxos de caso de uso, a complexidade poderia ser pior. Seu sistema pode estar entrando no  território do DDD. |   **2**    | Geralmente a complexidade não é reconhecida rapidamente. Nós, pessoas desenvolvedoras, costumamos subestimar a complexidade, apenas pelo desafio de codificar uma aplicação em N camadas com diversos Patterns (Padrões), mas isso não significa que devemos fazer. <br />No longo  prazo, essas aplicações poderiam prejudicar mais do que realmente ajudar. |
| Mesmo que a aplicação não seja complexa  agora, a complexidade dela aumentará no futuro? <br />Você só irá descobrir depois que os usuários reais começarem a trabalhar com ela, mas tenha cuidado aqui.<br />Se houver qualquer indício de que a aplicação tem alguma complexidade moderada no momento, talvez seja interessante ser um pouquinho precavido e considerar que isso pode ser um indicativo de que ela poderá se tornar mais do que moderadamente complexa no futuro. Avalie a possibilidade de utilizar o DDD. |   **3**    | Aqui vale a pena analisar os cenários de uso mais complexos com os Domain Experts e ver aonde eles levam. <br />Os Domain Experts: <br />1. Já estão solicitando recursos mais complexos? <br />Se sim, isso provavelmente é uma indicação de que a aplicação já é ou em breve se tornará excessivamente complexa para usar uma abordagem CRUD.<br />2. Estão entediados com os recursos ao ponto em que dificilmente vale a pena discuti-los? <br />Provavelmente a aplicação não é complexa. |
| Os recursos da aplicação serão alterados com frequência ao longo de alguns anos, e você não pode antecipar que as alterações serão simples. |   **4**    | O DDD pode ajudá-lo a gerenciar a complexidade da refatoração de seu modelo ao longo do tempo. |
| Você não entende o Domínio porque ele é novo. Na medida em que você e sua equipe se aprofundam na análise, percebem que ninguém fez isso antes. <br />Isso provavelmente significa que ele é complexo ou, pelo menos, merece a devida análise para determinar o nível de complexidade. |   **5**    | Você precisará trabalhar com os Domain Experts e testar os modelos para fazer a coisa certa. Você certamente também  pontuou em um ou mais dos critérios anteriores, portanto, use o DDD. |

Ao finalizar este exercício você terá  mais clareza para determinar se o DDD é viável ou não para o seu  projeto. Lembre-se de tomar as decisões com foco na  simplicidade, entrega e manutenção. Muitas vezes sofremos da vontade  incontrolável de implementar todos os conceitos de nossos estudos, porém estamos colocando em risco o dinheiro da empresa e nossa própria carreira.

<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
