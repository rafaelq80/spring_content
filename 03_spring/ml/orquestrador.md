<h1>Introdução a Orquestradores de Containers</h1>

Antes de entrarmos a fundo no conteúdo técnico, eu vou propor o seguinte problema:

Imagine que você é a pessoa responsável por manter uma aplicação funcionando, esta aplicação precisa rodar “fulltime” ou seja não pode haver interrupções ou quedas na aplicação, pois a cada vez que a aplicação cai por algum motivo o nosso cliente (empresa que nos contratou), perde um valor muito alto em vendas, um outro ponto importante é que quando há uma grade quantidade de requisições (acessos simultâneos na aplicação), a aplicação perde performance.

*Qual estratégia poderíamos usar para suprir a necessidade do nosso cliente?*

Orquestradores de containers caberia como uma luva e garantiria a integridade e a alta disponibilidade da nossa aplicação.

### Mas afinal, o que é um Orquestrador de container?
O termo orquestração é utilizado na TI por conta da sua alusão aos vários instrumentos musicais (ferramentas) usadas por vários músicos (programadores e [sysadmins](https://fabiorafael.wordpress.com/2007/08/08/o-que-e-ser-um-sysadmin/)) que são minuciosamente coordenados por um maestro (orquestrador).
Tudo isso para que seja entregue a melhor experiência musical (serviços e apps) para o usuário final.

Um orquestrador dita como a banda toca, organizando e disponibilizando microsserviços de acordo com a demanda naquele momento.

Costuma-se dizer que utilizar containers é algo que tende ao caos, pois é uma arquitetura cujos componentes se multiplicam muito rapidamente, por isso, há a necessidade de um super componente que organize tudo.
Essa arquitetura se popularizou com o Docker, que entrega containers que compartilham recursos do kernel do sistema hospedeiro e entrega apenas camadas adicionais, isolando sistemas e aplicações.

> **Kernel é uma  palavra inglesa usada na computação para designar o núcleo do sistema  operacional, que é a parte principal de um computador**. Uma simples  alteração da versão do Kernel para uma mais antiga ou mais atual pode  ser suficiente para resolver problemas de hardware e também de  compatibilidade no computador.

Então uma imagine que temos um cluster com apenas um container da nossa aplicação rodando assim como na imagem abaixo:

![enter image description here](https://i.imgur.com/tKrw0LG.png)

> Um **Cluster no Docker** se refere a um ou vários nós (nodes) unidos usando o modo Swarm. 

Desta forma caso haja algum evento que derrube o container ou interrompa a conexão com a internet, ou até mesmo excesso de requisições, estes eventos podem causar lentidão ou até mesmo a interrupção da nossa aplicação.

Já com um orquestrador de container podemos disponibilizar outras instancias com o mesmo container dentro do cluster assim como na figura abaixo.

![enter image description here](https://i.imgur.com/1UBbFKd.png)

Um orquestrador possui duas funcionalidades que são de extrema importância, que são:

- **Replica set:** O replica set é responsável por manter exatamente o numero de replicas de containers que definimos para que nosso orquestrador gerencie, caso alguma dessas replicas fique fora do ar o replica set irá construir uma replica para substituir a que ficou fora do ar.
- **Load Balance:** O load balance é o responsável por fazer o balanceamento das requisições, ou seja, ele garante que cada container receba a quantidade de requisições que é definido na sua configuração.

***Afinal de contas aonde fica o serviço que gerenciará tudo isto?***

Na imagem abaixo, podemos ver que existem 3 tipos de instancias: **Leader, Reachable e Worker**:

- **Leader:** É esta instancia que gerenciará as demais instancias (Reachable e Worker), ou seja, é ela que gerenciará o load balance e o replica set. Esta instancia também executará os containers. **importante**: só pode existir apenas uma maquina Leader no Cluster.
- **Reachable:** Caso o Leader caia, é feito uma eleição para decidir qual instancia será o próximo Leader, **importante**: quanto maior é o numero de instancias Reachable maior é o tempo de demora na eleição de um novo leader, porque esta instancia também executará os containers.
- **Worker:** Esta instancia serve apenas para rodar os containers.

![enter image description here](https://i.imgur.com/b72XsQT.png)

<h2>2. Docker Swarm</h2>

O **Docker Swarm** é uma ferramenta nativa do Docker, que permite a criação de clusters de Docker, ou seja, podemos fazer com que diversos hosts de Docker estejam dentro do mesmo pool de recursos, facilitando assim o deploy de containers. É possível por exemplo criar um container sem necessariamente saber em qual host ele está, pois o Swarm disponibilidade uma API de integração, onde é possível realizar grande parte das atividades administrativas de um container.


### Vamos ver tudo isso na prática usando o [Docker Playground](https://labs.play-with-docker.com/)

Vamos criar 4 maquinas, clicando no botão **+ add new instance** (uma vez para cada máquina), como mostra a imagem abaixo: 

![enter image description here](https://i.imgur.com/v2UCKUd.png)

Na primeira maquina vamos digitar o comando:

 `docker swarm init --advertise-addr “ip_da_instância”`

![enter image description here](https://i.imgur.com/vEacKnI.png)

Ao executar o comando: `docker swarm init --advertise-addr “ip_da_instância”` teremos no console o comando para transformarmos as outras instancias em workers: `docker swarm join --token <token> <ip:porta>` 

Vamos executar este comando nas outras 3 maquinas:

![enter image description here](https://i.imgur.com/D2NFflH.png)

Para conferir se as maquinas esta conectadas na instancia que esta o container leader execute o comando `docker node ls`

![enter image description here](https://i.imgur.com/YxgODLg.png)

Na imagem acima podemos observar que temos uma instancia leader e as que não possuem manager status preenchido, são consideradas como instancias workers. Para promover uma instancia para Reachable, basta executar o camando: `docker node promote <HOSTNAME>` e neste caso promoveremos o node1

![enter image description here](https://i.imgur.com/GYp0J8i.png)

Vamos listar os nodes novamente para ver as alterações com o comando: `docker node ls`

![enter image description here](https://i.imgur.com/GtisdG9.png)

Pronto! acabamos de promover uma instancia/node para Reachable. Para remover a promoção bastar usar o comando `docker node demote <HOSTNAME>`.

<h2>3. Criando um service no Docker Swarm</h2>


Vamos executar o comando:

 `docker service create --name my_web --replicas 6 --publish published=8080,target=80 nginx` 

Entendendo o comando:

- **docker service create:** criando um service.
- **--name:** Dando um nome para a nossa aplicação.
- **--replicas:** Definindo a quantidade de replicas a serem distrubuidas em nossas instancias/node.
- **--publish:** Mapeamento de portas internas e externas sendo que, target é a porta interna e published é a porta externa.
- **nginx:** como já sabemos é a imagem que iremos rodar.

**Preparando e criando as 6 replicas...**

![enter image description here](https://i.imgur.com/Qblrp8W.png)

**Pronto!**

![enter image description here](https://i.imgur.com/B1GnXM1.png)

Para verificar se todos as replicas/serviços estão online, podemos utilizar o comando: `docker service ls` na nossa instancia leader.
Podemos notar na imagem abaixo que temos 6/6 replicas do service my_web.

![enter image description here](https://i.imgur.com/3GcGSp3.png)

Agora vamos em uma instancia worker e executar o comando: `docker ps` para ver um serviço do Nginx rodando.

![enter image description here](https://i.imgur.com/wCJ7of4.png)

E se deletarmos a uma maquina worker o que acontece?

No caso de uma deleção de uma das maquinas, o Docker Swarm entenderá que houve uma falha em algum sistema que apagou as replicas dentro da maquina que foi excluída, sendo assim ele criará novas replicas para suprir a necessidade estabelecida de 6 replicas.

Na imagem abaixo temos 6 replicas porem desta vez com 3 maquinas sendo que 2 replicas por maquinas:

![enter image description here](https://i.imgur.com/uA4ezCe.png)

<h2>4. Principais Comandos do Docker Swarm</h2>

|Comando													|Ação  |
|-----------------------------------------------------------|------|
| `docker swarm init --advertise-addr “ip_da_instância”` 	| Inicia o service swarm |
| `docker swarm join --token <token> <ip:porta>`			| Adiciona as maquinas em um nó como  worker ou reachable |
| `docker node ls`											| lista as instancias/nodes |
| `docker node promote <HOSTNAME>`							| Promove uma instancia para leader ou reachable |
| `docker node demote <HOSTNAME>`							| Rebaixa uma instancia para worker |
| `docker service ls`										| Lista os serviços que estão rodando |
| `docker swarm leave`										| Sai do Docker Swarm |
| `docker swarm join-token manager`							| Resgata o token para sincronizar com uma instancia leader ou reachable |
| `docker swarm join-token worker`										| Resgata o token para sincronizar com uma instancia worker |
| `docker service create --name <App Name> --replicas <Qtd Replivas> --publish published=<Port externa>,target=<Port interna> <Imagem>`	| Cria um service no docker swarm  |



<br /><br />

<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
