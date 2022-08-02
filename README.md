<p align="center">
 
<img src="https://icon-library.com/images/deploy-icon/deploy-icon-8.jpg" width="120">
<h3 align="center">Deploy via Github Actions</h3>

<p align="center">Repositório com templates que podem ser utilizados nas github actions de projetos laravel e angular.</p>

<p align="center">
▸ <a href="https://github.com/tiagointerativa/template-deploy-github-actions/blob/main/template-laravel.yml">Template Laravel</a> |
▸ <a style="pointer-events: none;" href="https://github.com/tiagointerativa/template-deploy-github-actions/blob/main/template-angular.yml">Template Angular</a>

</p>

## ❔ Onde colocar o arquivo .yml?

Os arquivos com extensão .yml são arquivos que contém todas as regras para realizar o deploy, eles devem ser inseridos dentro da pasta *.github/workflows*, caso não exista, basta criá-la.

## ❔ Posso realizar alterações nos arquivos?

Os arquivos foram criados para serem utilizados em projetos laravel ou angular, mas podem ser adaptados para serem usados em projetos de outras linguagens. Também pode ser necessário alterações nos scripts, para definir por exemplo a pasta que irá rodar os comandos e etc, antes de utilizar, sempre revise o arquivo.

## 🌟 Como criar as SECRETS necessárias?

O endereço do servidor, usuário e key ficarão registradas nas secrets do github, por trazer mais segurança a esses dados de acesso ao servidor, para configurá-los basta seguir os passos abaixo.

 - Acesse **Settings**.
 - No menu a esquerda, clique em **SECRETS** > **ACTIONS**.
 - Agora clique em **NEW REPOSITORY SECRET** e crie as seguintes chaves.
 
 ➤ **PRODUÇÃO**
 
 - **PRODUCAO_HOST**: *Deve ser informado o host do servidor*
 - **PRODUCAO_USER**: *Deve ser informado o usurio de acesso ao servidor*
 - **PRODUCAO_PORT**: *Deve ser informado a porta de acesso ao servidor*
 - **PRODUCAO_KEY**: *Deve ser informado a chave privada (Para ver a chave privada rode o comando: **cat ~/.ssh/id_rsa**)*
 - **PRODUCAO_PASSWORD**: *Caso não queira utilizar chave ssh, pode ser utilizado password.*
 
  ➤ **HOMOLOGAÇÃO**
  
 - **HOMOLOGACAO_HOST**: *Deve ser informado o host do servidor*
 - **HOMOLOGACAO_USER**: *Deve ser informado o usurio de acesso ao servidor*
 - **HOMOLOGACAO_PORT**: *Deve ser informado a porta de acesso ao servidor*
 - **HOMOLOGACAO_KEY**: *Deve ser informado a chave privada (Para ver a chave privada rode o comando: **cat ~/.ssh/id_rsa**)*
 - **HOMOLOGACAO_PASSWORD**: *Caso não queira utilizar chave ssh, pode ser utilizado password.*
 
## 💡 Dicas

*Se você não tiver chave privada, você pode executar **ssh-keygen** no terminal do servidor para gerar uma nova chave, em seguida, execute o comando **cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys** para permitir a conexão com o privado chave*

*Caso o projeto tenha remote por HTTPS e não por SSH, você pode ter erros de credenciais quando o script tentar executar o git pull, uma solução seria alterar o remote para ssh, ou rodar esse comando: **git config credential.helper store** e logo em seguida rodar o git pull para ficar registrado as credenciais, assim as próximas requisiçes serão feitas usando essa credencial salva.*

Documentação Oficial: <a href="https://github.com/marketplace/actions/ssh-remote-commands">Acessar</a>
