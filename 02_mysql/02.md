
<h1>Banco de Dados com MySQL - parte 01</h1>

O que veremos por aqui:

1. Introdução ao MySQL
2. Entendendo: Comandos e Conceitos Básicos

<h2>1. MySQL</h2>

O MySQL é um sistema de gerenciamento de banco de dados (SGBD), que utiliza a linguagem SQL (Linguagem de Consulta Estruturada - Structured Query Language) como interface. É atualmente um dos Sistemas de Gerenciamento de Banco de dados mais populares da Oracle Corporation, com mais de 10 milhões de instalações pelo mundo. Possui versões pagas e a versão Community (gratuita).

<br />

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://dev.mysql.com/doc/" target="_blank"><b>Site Oficial: <i>MySQL</i></b></a>

<br /><br />

| <img src="https://i.imgur.com/RfjtOFi.png" title="source: imgur.com" width="80px"/> | <p align="justify"> **DICA:** *Caso você tenha alguma dúvida quanto a instalação do MySQL, consulte o Guia de Instalação do MySQL. </p> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br />
	
<h3>1.1. Entendendo: Comandos e Conceitos Básicos</h3>

A IDE que utilizaremos para criar e manipular o nosso banco de dados será o MySQL Workbench

<br />

<div align="center"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQZsyBJ1rEuTOhKEnGFf6BOaSM8OHnFH8MR-o-ia6bGoz4zvu91" title="source: imgur.com" width="90%"/>
</div>

<br />
	
<h3>1.2. Criando nosso primeiro Banco de Dados</h3>

1. Uma vez que estamos o MySql Workbench aberto, precisamos criar uma conexão local. Portanto, **clique no item com símbolo de “+”**, ao lado das palavras **MySQL Connections**.

<div align="center"><img src="https://i.imgur.com/iRZMPal.png" title="source: imgur.com" width="90%"/></div>

2. Defina um nome para a sua conexão.

<div align="center"><img src="https://i.imgur.com/ObHr5Oj.png" title="source: imgur.com" width="90%"/></div>

3.  Defina uma senha para esta conexão clicando em **Store in Vault…**, e clique em OK.

<div align="center"><img src="https://i.imgur.com/OlvVsti.png" title="source: imgur.com" width="90%"/></div>

4. Uma vez feito os passos acima, já temos nossa conexão criada.

<div align="center"><img src="https://i.imgur.com/sOMAmui.png" title="source: imgur.com" width="90%"/></div>


5. Após acessar a conexão criada teremos um ambiente onde vamos criar nossas tabelas e relaciona-las.

<div align="center"><img src="https://i.imgur.com/zHLaOTc.png" title="source: imgur.com" width="90%"/></div>

<h3>1.3. Executando consultas no MySQL Workbench</h3>

Para escrever o código SQL das nossas Queries, utilize a aba **Query** do MySQL Workbench.

Para executar a Query existem duas maneiras:

|                                                              | Descrição                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| <img src="https://i.imgur.com/xH6Ei9O.png" title="source: imgur.com" /> | Executa todas as linhas ou apenas as linhas selecionadas de uma vez só na sequência. |
| <img src="https://i.imgur.com/9FtJQlk.png" title="source: imgur.com" width="30px"/> | Executa apenas a linha onde o cursor do mouse está posicionado ou apenas a primeira linha de uma seleção. |

<h3>1.4. Banco de Dados - Exemplo</h3>

Utilizaremos como Banco de dados guia para testarmos as SQL Queries no MySQL o Banco **db_quitanda**. Primeiro vamos criar a tabela **tb_produtos**, que possui estrutura abaixo:

<div align="center"><img src="https://i.imgur.com/sH0OsaD.png" title="source: imgur.com" width="25%"/></div>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/>Criar o Banco de dados</h3>

Na aba **Query**, digite e execute a query abaixo utilizando o segundo raio <img src="https://i.imgur.com/9FtJQlk.png" title="source: imgur.com" width="30px"/>:

<h4>CREATE DATABASE</h4>

```sql
CREATE DATABASE db_quitanda;
```
Ao executar a query, será criado o **Banco de Dados** e no campo de Output aparecerá o log/mensagem informando que a operação foi efetuada com sucesso.

<div align="center"><img src="https://i.imgur.com/gqmdMFh.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_create_db.asp" target="_blank"><b>Documentação: <i>Create database - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/>Selecionando o Banco de Dados</h3>

Antes de criarmos nossa primeira tabela, é necessário indicar ao MySQL qual banco de dados queremos trabalhar. Para isso utilize a query abaixo, e em seguida execute a query abaixo utilizando o segundo raio <img src="https://i.imgur.com/9FtJQlk.png" title="source: imgur.com" width="30px"/>.

<h4>USE</h4>

```sql
USE db_quitanda;
```

Ao executar a query, aparecerá no log/mensagem do campo de Output a seguinte mensagem:

<div align="center"><img src="https://i.imgur.com/23CWoiM.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.mysqltutorial.org/mysql-select-database/" target="_blank"><b>Documentação: <i>Use - MySQL Tutorial</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Criando nossa primeira Tabela</h3>

O processo para criação de uma tabela é bem simples, basta inserir a query abaixo, e em seguida execute a query abaixo utilizando o segundo raio <img src="https://i.imgur.com/9FtJQlk.png" title="source: imgur.com" width="30px"/>.

<h4>CREATE TABLE</h4>

```sql
CREATE TABLE tb_produtos(
    id bigint auto_increment,
	nome varchar(255) not null,
	quantidade int,
	preco decimal not null,
    PRIMARY KEY (id)
);
```

Caso a query tenha sido executada corretamente, no canto esquerdo na aba das **Tabelas** aparecerá a tabela criada: 

<div align="center"><img src="https://i.imgur.com/MSMZ2fE.png" title="source: imgur.com" width="40%"/></div>

E aparecerá no log/mensagem do campo de Output a seguinte mensagem:

<div align="center"><img src="https://i.imgur.com/zhlzcK5.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_create_table.asp" target="_blank"><b>Documentação: <i>Create Table - W3Schools</i></b></a>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_primarykey.asp" target="_blank"><b>Documentação: <i>Primary Key - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Inserindo dados na Tabela</h3>

Uma vez que já temos a tabela criada, precisamos popula-la, ou seja, inserir dados. Para tal digite o código abaixo seguindo a sintaxe/estrutura de código abaixo e em seguida selecione as 6 linhas e execute a query utilizando o primeiro raio <img src="https://i.imgur.com/xH6Ei9O.png" title="source: imgur.com" />.

<h4>INSERT INTO</h4>

```sql
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("tomate",100, 8.00);
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("maçã",20, 5.00);
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("laranja",50, 10.00);
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("banana",200, 12.00);
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("uva",1200, 30.00);
INSERT INTO tb_produtos(nome, quantidade, preco) 
values ("pêra",500, 2.99);
```

Feito isto os dados dos produtos Tomate, Maçã, Laranja e das outras frutas serão inseridos na tabela. 

<br>

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="180px"/> | **IMPORTANTE:** Como definimos que o campo `id` será chave primária (`PRIMARY KEY`) e será atualizado automaticamente de um em um a cada registro inserido, através do código `auto_increment`, não inserimos nenhum valor nesse campo. |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_insert.asp" target="_blank"><b>Documentação: <i>Insert Into - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Selecionando dados da Tabela</h3>

Agora vamos fazer a nossa primeira consulta no bando para ver se os dados foram devidamente inseridos na tabela. Para isto basta fazer um `Select ` na tabela:

<h4>SELECT</h4>

```sql
SELECT * FROM tb_produtos;
```

Ao executar a query, aparecerá o console com a seguinte tabela:

<br>

<div align="center"><img src="https://i.imgur.com/BvchVDN.png" title="source: imgur.com" width="60%"/></div>

<br>

Caso seja necessário selecionar apenas um atributo como por exemplo o nome, basta substituir o ( * ) **asterisco** pelo nome do atributo desejado.

```sql
SELECT nome FROM tb_produtos;
```

Ao executar a query, aparecerá o console com a seguinte tabela:

<div align="center"><img src="https://i.imgur.com/36KsurN.png" title="source: imgur.com" width="50%"/></div>

Caso seja necessário mostrar mais de um atributo, **devemos separa-los por vírgula.**

```sql
SELECT nome, preco FROM tb_produtos;
```

Ao executar a query, aparecerá no log/mensagem do campo de Output a seguinte tabela:

<div align="center"><img src="https://i.imgur.com/vA5dlW4.png" title="source: imgur.com" width="60%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_select.asp" target="_blank"><b>Documentação: <i>Select - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Selecionando dados da Tabela com critérios</h3>

Caso haja a necessidade de retornar apenas uma linha especifica, utilizarmos a cláusula `WHERE` seguido do atributo que queremos filtrar. **Exemplo**: desejamos retornar todas as informações do Produto cujo `id` é igual 1. Nesse caso executamos a seguinte query: 

<h4>WHERE</h4>

```sql
SELECT * FROM tb_produtos WHERE id = 1;
```

Ao executar a query, teremos o seguinte resultado:

<div align="center"><img src="https://i.imgur.com/ompy7qY.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_where.asp" target="_blank"><b>Documentação: <i>Where - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/>Selecionando dados com os Operadores Relacionais</h3>

Caso haja a necessidade de retornar registro com base em comparações, basta utilizarmos o código `WHERE` junto com os Operadores Relacionais, informando o campo/coluna que será utilizado na comparação. 

| Operador | Descrição              |
| -------- | ---------------------- |
| **>**        | Maior do que           |
| **>=**       | Maior do que ou  igual |
| **<**        | Menor do que           |
| **<=**       | Menor do que ou igual  |
| **=**        | igual                  |
| **<>**       | diferente              |

**Exemplo**: desejamos retornar todos os produtos que tenham preço acima de R$ 5,00. Nesse caso executamos a seguinte query:

<h4>WHERE com Operados Relacionais</h4>

```sql
SELECT * FROM tb_produtos WHERE preco > 5.00;
```

Ao executar a query, teremos o seguinte resultado:

<div align="center"><img src="https://i.imgur.com/nvQaGdB.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_operators.asp" target="_blank"><b>Documentação: <i>Operadores - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/>Selecionando dados com os Operadores Lógicos</h3>

Caso haja a necessidade de retornar um registro com base em um resultado lógico (VERDADEIRO ou FALSO), basta utilizarmos o código `WHERE` junto com os Operadores Lógicos, informando o atributo que será utilizado na comparação. 

| Operador | Descrição                                                  |
| -------- | ---------------------------------------------------------- |
| **AND**      | Verdadeiro somente se todas as condições forem verdadeiras |
| **OR**       | Verdadeiro se 1 condição for verdadeira                    |
| **NOT**      | Negação                                                    |

**Exemplo**: desejamos retornar todos os produtos que tenham preço acima de R$5,00 **E** quantidade menor do que 100. Nesse caso executamos a seguinte query:

<h4>WHERE com Operadores Lógicos</h4>

```sql
SELECT * FROM tb_produtos WHERE preco > 5.00 AND quantidade < 100;
```

Ao executar a query, teremos o seguinte resultado:

<div align="center"><img src="https://i.imgur.com/GfaeEfw.png" title="source: imgur.com" width="70%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_operators.asp" target="_blank"><b>Documentação: <i>Operadores Relacionais- W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Atualizando dados na Tabela</h3>

Para atualizar os dados da tabela devemos utilizar o comando `Update` no registro que queremos atualizar. **Exemplo**: queremos alterar o preço do produto Tomate para R$5,00. 

| <img src="https://i.imgur.com/vVDBDG0.png" title="source: imgur.com" width="300px"/> | **ALERTA DE BSM:** *Mantenha a Atenção aos Detalhes ao construir essa Query, pois obrigatoriamente você DEVE COLOCAR o comando WHERE, pois caso contrário o MySQL Workbench irá atualizar TODOS OS REGISTROS, sem a possibilidade de desfazer a atualização errônea de maneira simples.* |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

Antes de Executar a query, execute o comando abaixo:
```sql
SET SQL_SAFE_UPDATES = 0;
```
A linha de comando acima **desabilita o modo de atualização segura** do MySQL, ou seja, é um modo que impede, por exemplo, de executar os famosos **UPDATE sem WHERE** (modifica todos o registros da tabela) e o **DELETE sem WHERE** (apaga todos o registros da tabela).

<h4>UPDATE</h4>

```sql
UPDATE tb_produtos SET preco = 5.00 WHERE id = 1;
```

Ao executar a query, aparecerá no log/mensagem do campo de Output uma mensagem que a alteração foi concluída, e para visualizar o produto alterado basta executa a seguinte query:

```sql
SELECT * FROM tb_produtos WHERE id = 1;
```

Logo você terá a seguinte imagem:

<div align="center"><img src="https://i.imgur.com/RdbiTfT.png" title="source: imgur.com" width="50%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_update.asp" target="_blank"><b>Documentação: <i>Update - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Apagando dados na Tabela</h3>

Para apagar um ou mais registros da tabela, utilizamos o comando `DELETE`. **Exemplo**: queremos apagar o produto que tenha o id igual a 2. 

| <img src="https://i.imgur.com/vVDBDG0.png" title="source: imgur.com" width="300px"/> | **ALERTA DE BSM:** *Mantenha a Atenção aos Detalhes ao construir essa Query, pois obrigatoriamente você DEVE COLOCAR o comando WHERE, pois caso contrário o MySQL Workbench irá APAGAR TODOS OS REGISTROS, sem a possibilidade de desfazer a operação.* |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

Nesse caso executamos a seguinte query: 

<h4>DELETE</h4>

```sql
DELETE FROM tb_produtos WHERE id = 2;
```

Ao executar a query, aparecerá no log/mensagem do campo de Output uma mensagem que a exclusão foi concluída, e para visualizar se o produto foi realmente excluído basta executa a seguinte query para listar os produtos:

```sql
SELECT * FROM tb_produtos;
```

Logo você terá a seguinte imagem:

<div align="center"><img src="https://i.imgur.com/U1fgKyx.png" title="source: imgur.com" width="50%"/></div>

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_delete.asp" target="_blank"><b>Documentação: <i>Delete - W3Schools</i></b></a>

<h3><img src="https://i.imgur.com/ZL3AFqF.png" title="source: imgur.com" width="30px"/> Modificando a Estrutura da Tabela</h3>

Esse comando é usado para adicionar, excluir ou modificar as colunas (atributos), em uma tabela existente, além de poder adicionar ou excluir restrições de uma tabela, como chaves primárias e/ou chaves estrangeiras. 

**Exemplo 01:** Queremos modificar/atualizar o tipo de um Atributo/Coluna, fazendo com que o campo preco tenha 6 dígitos, sendo que 2 deles são casas decimais (1000.50). Nesse caso executamos a seguinte query: 

<h4>ALTER TABLE - MODIFY</h4>

```sql
ALTER TABLE tb_produtos MODIFY preco decimal(6,2);
```

Observe que após esta alteração o atributo preco será exibido com as casas decimais:

```sql
SELECT * FROM tb_produtos;
```

<div align="center"><img src="https://i.imgur.com/i9RtL9G.png" title="source: imgur.com" width="60%"/></div>

| <img src="https://i.imgur.com/L338M2G.png" title="source: imgur.com" width="120px"/> | **DESAFIO:** *Observe que mesmo corrigindo as casas decimais, o preço da pêra continua arredondado para R$ 3.00. Como podemos corrigir o valor deste produto?* |
| ------------------------------------------------------------ | :----------------------------------------------------------- |

**Exemplo 02:** Queremos adiciona um novo Atributo/Coluna na  Tabela. Nesse caso executamos a seguinte query: 

<h4>ALTER TABLE - ADD</h4>

```sql
ALTER TABLE tb_produtos ADD descricao varchar(255);
```

**Exemplo 03:** Queremos remover um Atributo/Coluna da tabela. Nesse caso executamos a seguinte query: 

<h4>ALTER TABLE - DROP</h4>

```sql
ALTER TABLE tb_produtos DROP descricao; 
```

**Exemplo 04:** Queremos alterar o nome de um Atributo/Coluna da tabela. Nesse caso executamos a seguinte query: 

<h4>ALTER TABLE - CHANGE</h4>

```sql
ALTER TABLE tb_produtos CHANGE nome nomeproduto VARCHAR(255); 
```

| <img src="https://i.imgur.com/RfjtOFi.png" title="source: imgur.com" width="80px"/> | **DICA:** *Após executar as consultas, execute um <code>select * from tb_produtos;</code> e veja as alterações.* |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<div align="left"><img src="https://i.imgur.com/Mh2KzWe.png" title="source: imgur.com" width="25px"/> <a href="https://www.w3schools.com/sql/sql_alter.asp" target="_blank"><b>Documentação: <i>Alter Table - W3Schools</i></b></a>
