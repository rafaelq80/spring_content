<h1>Deploy do Backend no Heroku - Github Organization</h1>

Quando estamos trabalhando com Organizações, além de conectar o Heroku com a Conta do Github é necessário autorizar o acesso do Heroku na Organização, para poder acessar os repositórios.
Neste material, o Passo 11 foi adaptado para o Deploy do Projeto Integrador via Github Organization. Substitua o Passo 11 do Guia do Deploy do Projeto Blog Pessoal pelas instruções abaixo. Os demais passos são iguais.

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="200px"/> | <p align="justify"> **ATENÇÃO:**  *Crie a conta no Heroku utilizando o e-mail que foi criado para o projeto, ou seja, a mesma conta que o grupo utilizou para criar a conta no Github, onde foi criada a Organização*. </p> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<h2>👣 Passo 11 - Deploy da Organização no Heroku</h2> 

1. Para configurar o **Deploy** do seu projeto, clique na guia **Deploy**.

<div align="center"><img src="https://i.imgur.com/WSNVenp.png?1" title="source: imgur.com" /></div>

2. Na sequência, clique no ícone do **Github**

<div align="center"><img src="https://i.imgur.com/dYrPaJw.png?1" title="source: imgur.com" /></div>

3. No item **App connected to Github**, clique no botão **Connect to Github**

<div align="center"><img src="https://i.imgur.com/lL0TdnQ.png?1" title="source: imgur.com" /></div>

4. Conecte-se com a conta do **Github do Projeto Integrador**.

      <div align="center"><img src="https://i.imgur.com/L21dPiM.png" title="source: imgur.com" /></div> 

   5. Na próxima tela, não esqueça de liberar o acesso do Heroku na Organização, como mostra a figura abaixo, clicando no botão **Grant** ao lado da Organização (em nosso exemplo **Projeto-Integrador-Modelo**).

   <div align="center"><img src="https://i.imgur.com/GwIJRBZ.png" title="source: imgur.com" /></div>

   6. Em seguida clique no botão **Authorize heroku**

   7. Caso você não tenha autorizado o Heroku no passo anterior, depois de conectar a conta do Heroku com a conta do Github, clique no link **Ensure Heroku Dashboard has team access**, conforme indicado na figura abaixo:

   <div align="center"><img src="https://i.imgur.com/yTEmigm.png" title="source: imgur.com" /></div>

   8. Na próxima tela, clique no botão **Grant** ao lado da Organização (em nosso exemplo **Projeto-Integrador-Modelo**), como mostra a figura abaixo, para liberar o acesso.

   <div align="center"><img src="https://i.imgur.com/aEUSmcE.png" title="source: imgur.com" /></div>

   9. Observe que no Item **Select for a repository to connect to** estará disponível tanto a Conta do Github, quanto a Organização. Selecione a Organização, em nosso exemplo **Projeto-Integrador-Modelo**

   <div align="center"><img src="https://i.imgur.com/uBZdkZ1.png" title="source: imgur.com" /></div>

4. Em seguida, vamos procurar o **Repositório do Projeto Integrador**

7. No item **Connect to Github**, na caixa de pesquisa **repo-name**, digite o **Nome do Repositório do Projeto Integrador, em nosso exemplo backend,** e clique no botão **Search**.

<div align="center"><img src="https://i.imgur.com/JZf08K4.png" title="source: imgur.com" /></div>

8. Será exibido o repositório. Clique no botão **Connect** ao lado do Repositório backend.

<div align="center"><img src="https://i.imgur.com/7d1HEpA.png" title="source: imgur.com" /></div>

9. Observe que o Heroku indicará que a aplicação está **Conectada com o Repositório**.

<div align="center"><img src="https://i.imgur.com/Grk5C2A.png" title="source: imgur.com" /></div>

10. No item **Automatic deploys**, no item **Choose a branch to deploy**, selecione a **Branch** que será usada para fazer o Deploy (main). Na sequência, clique no botão **Enable Automatic Deploys**, para automatizar o processo, ou seja, toda vez que você fizer um **push no Repositório no Github**, o Heroku tentará fazer o Deploy automaticamente.

<div align="center"><img src="https://i.imgur.com/tErTzAl.png?1" title="source: imgur.com" /></div>


| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="150px"/> | <p align="justify"> **ATENÇÃO:** *O Deploy automático será concluído, APENAS E SOMENTE SE o código que foi enviado para o Github esteja sem erros e com o perfil PROD habilitado. </p> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |


11. No item **Manual deploy**, clique no botão **Deploy branch**.

<div align="center"><img src="https://i.imgur.com/BdZnZnQ.png?1" title="source: imgur.com" /></div>

12. Logo abaixo, será exibida a janela do **Console do Heroku**. Acompanhe o processo do Deploy e aguarde a conclusão

<div align="center"><img src="https://i.imgur.com/UWlFFXa.png" title="source: imgur.com" /></div>

13. Se o Deploy foi bem sucedido, será exibida a mensagem **Deploy to Heroku - Your app was succesfully deployed**.

<div align="center"><img src="https://i.imgur.com/TCCFf2j.png" title="source: imgur.com" /></div>

14. Clique no botão **View** para abrir a aplicação.

| <img src="https://i.imgur.com/hOgWvSc.png" title="source: imgur.com" width="100px"/> | <p align="justify"> **ATENÇÃO:** *Caso aconteça algum erro no processo do Deploy será exibida a mensagem: Build failed!.  Verifique o seu código e tente novamente.</p> |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

<br /><br />
	
<div align="left"><a href="README.md"><img src="https://i.imgur.com/XMgF3gl.png" title="source: imgur.com" width="3%"/>Voltar</a></div>
