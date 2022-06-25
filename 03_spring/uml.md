<h1>Diagrama de Classes</h1>



A **Programação Orienteda à Objetos (POO)** é um paradigma baseado no conceito de envolver dados (**Atributos**), e comportamentos (**Métodos**), relacionados aqueles dados, em uma coleção chamada Objetos, que são construídos de um conjunto de “planos de construção” (**Métodos Construtores**), definidos por uma pessoa Desenvolvedora ou por um Analista de Sistemas, chamados de **Classes**. Uma classe é como uma planta de construção que define a estrutura para objetos, que são instâncias concretas daquela classe.

Da mesma forma que o **DER**, Diagrama de Entidades e Relacionamentos apresentam o nosso Modelo de dados Relacional de forma gráfica, o **Diagrama de Classes** representam de forma gráfica as nossas Classes e as suas relações. A **UML** (Unified Modeling Language), que **significa** Linguagem Unificada de Modelagem é uma linguagem padrão para modelagem orientada a objetos, utilizada na construção dos Diagramas de Classes e outros tipos de Diagramas como Casos de Uso, Sequência e etc.

<div align="center"><img src="https://i.imgur.com/UMOWspD.png" title="source: imgur.com" /></div>

Observe no Diagrama de Classe acima que podemos visualizar todos os Métodos e Atributos que compõem a Classe Cat, inclusive a visibilidade, simplificando processo de implementação.

<br /><br />

<h2>Relações entre objetos</h2>



Quando falamos de uma única Classe, tudo fica muito simples, entretanto, nenhuma aplicação Orientada a Objetos se resume em apenas uma Classe, e além disso, os Objetos gerados por estas Classes possuem relações entre si, de acordo com o planejamento do projeto. Para simplificar o entendimento destas relações, construímos os Diagramas de Classes com as suas respectivas Relações. Vamos conhecer os tipos de relação entre os Objetos:

<h3>Herança</h3>

A Herança é a habilidade de construir novas classes em cima de classes já existentes. O maior benefício da herança é a reutilização de código. Se você quer criar uma classe que é apenas um pouco diferente de uma já existente, não há necessidade de duplicar o código. Ao invés disso, você estende a classe existente e coloca a funcionalidade adicional dentro de uma subclasse resultante, que herdará todos os campos de métodos da superclasse.

<div align="center"><img src="https://i.imgur.com/J263Uf4.png" title="source: imgur.com" /></div>

No exemplo acima, Gato é um animal, logo ele herda todas características da Classe Animal. 

<h3>Implementação</h3>

Interfaces são um conceito  da programação orientada a objetos que tem a ver com o comportamento esperado para uma ou um conjunto de classes. Interfaces definem o que uma classe deve fazer e não como. Assim, interfaces não  possuem a implementação de métodos pois apenas declaram o conjunto de  métodos. 

Na interface, todos os métodos são portanto abstratos e públicos, já que são apenas declarados na interface sendo  obrigatoriamente implementados pelas classes que implementam a  interface. Uma vez definida uma interface é implementada pelas classes de devem ter o  comportamento descrito na interface, ou seja, devem ter os mesmos  métodos definidos na interface. Dizemos que as classes implementam a  interface pois de fato uma classe ao implementar uma interface deve  prover a implementação de todos os métodos definidos na interface.

Em diagramas UML, o relacionamento de Implementação é mostrado por uma seta igual a da Herança, com a linha tracejada, desenhada de um objeto e apontada para outro que ele implementa.

<div align="center"><img src="https://i.imgur.com/aDHrDKh.png" title="source: imgur.com" /></div>

No exemplo acima, a Classe Cat está implementando os Métodos das Interfaces Quatro Patas e Respira Oxigênio

<h3>Associação</h3>

A associação é um relacionamento no qual um objeto usa ou interage com outro. Em diagramas UML, o relacionamento de
associação é mostrado por uma seta simples desenhada de um objeto e apontada para outro que ele utiliza. A propósito,
ter uma associação bi-direcional é uma coisa completamente normal. Neste caso, a flecha precisa apontar para ambos. A
associação pode ser vista como um tipo especializado de dependência, onde um objeto sempre tem acesso aos objetos os quais ele interage, enquanto que a dependência simples não estabelece uma ligação permanente entre os objetos.

<div align="center"><img src="https://i.imgur.com/7wsXDFJ.png" title="source: imgur.com" /></div>

No exemplo acima, Professor interage com aluno.

<h3>Agregação</h3>

A agregação é um tipo especializado de associação que representa relações individuais, múltiplas, e totais entre múltiplos objetos, enquanto que uma associação simples descreve relações entre pares de objetos.
Geralmente, sob agregação, um objeto “tem” um conjunto de outros objetos e serve como um contêiner ou coleção. O componente pode existir sem o contêiner e pode ser ligado através de vários contêineres ao mesmo tempo. 

Em Diagramas UML a relação de agregação é mostrada como uma linha e um diamante vazio na ponta do contêiner e uma flecha apontando para o componente.

<div align="center"><img src="https://i.imgur.com/8XGJuk4.png" title="source: imgur.com" /></div>

No exemplo acima, um objeto Departamento contém diversos professores e os objetos professores continuam existindo mesmo sem o objeto departamento.



<h3>Composição</h3>

A composição é um tipo específico de agregação, onde um objeto é composto de um ou mais instâncias de outro. A distinção entre esta relação e as outras é que o componente só pode existir como parte de um contêiner. No UML a relação de composição é desenhada do mesmo modo que para a agregação, mas com um diamante preenchido na base da flecha.

<div align="center"><img src="https://i.imgur.com/bYPAd1L.png" title="source: imgur.com" /></div>

No exemplo acima, a universidade consiste de departamentos e os departamentos só existem enquanto o objeto universidade existir.



<h2>Resumindo...</h2>



<div align="center"><img src="https://i.imgur.com/1QDcyZp.png" title="source: imgur.com" /></div>

| Relação           | Descrição                                                    |
| ----------------- | ------------------------------------------------------------ |
| **Associação**    | Objeto A sabe sobre objeto B. Classe A depende de B;         |
| **Agregação**     | Objeto A sabe sobre objeto B, e consiste de B. Classe A depende de B; |
| **Composição**    | Objeto A sabe sobre objeto B, consiste de B, e gerencia o ciclo de vida de B. Classe A depende de B; |
| **Implementação** | Classe A define métodos declarados na interface B. objetos de A podem ser tratados como B. Classe A depende de B; |
| **Herança**       | Classe A herda a interface e implementação da classe B mas pode estende-la. Objetos de A podem ser tratados como B. Classe A depende de B. |


