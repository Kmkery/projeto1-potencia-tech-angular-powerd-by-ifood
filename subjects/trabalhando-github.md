## Trabalhando com o GitHub

Até aqui, o projeto criado existe unicamente no ambiente de desenvolvimento (repositório local), agora, ele deve ir para o servidor remoto (repositório em nuvem), neste caso, o GitHub.

### Criando uma conta no GitHub

O procedimento para criação de uma conta é bem simples, basta entrar na página do GitHub, clicar em _"Sign Up"_ e seguir os passos indicados.

### Autenticação segura

Antes de integrar GIT e GitHub, pode-se fazer algumas configurações adicionais para tornar a conexão entre repositório local / repositório remoto mais segura, para isto, fazendo uso do recurso de _**chaves SSH e tokens**_.

Chave SSH é uma forma de estabelecer conexão encriptada entre duas máquinas (máquina local e servidor GitHub), gerando duas chaves - uma pública e outra privada - onde a primeira é a usada para que o GitHub reconheça a máquina do usuário.

Para configurar a conexão entre máquina x GitHub, é necessário criar uma conta no GitHub e seguir os seguintes passos:

 - No GIT Bash, gerar uma chave por meio do comando ``ssh keygen --ed25519 --emaildoGitHub``. O ed25519 define o tipo de criptografia;

    Ao gerar as chaves, o GIT irá informar onde estão guardadas na máquina. Ao pressionar "enter", o GIT pedirá uma frase qualquer, preencher e confirmar. A chave pública terá a extensão _``.pub``_ no nome. O diretório _``.ssh``_ criado neste processo é oculto e _"id_25519"_ é o nome da chave. Para ver a chave, digitamos ``cat id_ed25519.pub``;

 - Dentro da pasta .ssh, digitamos ``ls`` para listar 

 - Ir até a página pessoal no GitHub, acessar o menu e clicar em _"Settings"_, em seguida, 
 - Clicar em _"SSH and GPG Keys"_ e preecher os campos _Title_ e o _"Key"_. Colocar algo que faça alusão à máquina a ser conectada e inserir a chave pública.
 - No GIt Bash, inicializar o _SSH agent_ para validar a chave, digitando ``eval $(ssh-agent -s)``. O console irá mostrar o número do agente (_Agent pid_), que varia conforme o processo. O agente deve receber a chave criada, para isto, informar o caminho onde ela se encontra. Inserir o comando ``ssh-add id_ed25519`` (com isso, passamos também a chave privada, pois com ela é possível descriptografar informações quando necessário). Ao dar "enter", o GIT irá mostrar o email e id adicionados;
 

Quando clonar um repositório do GitHub, usar o caminho SSH indicado na página do repositório: ``git clone caminhoSSHdorepositorioGitHub``.
A primeira vez que for usada a chave, aparecerá uma mensagem que deve ser confirmada com "yes". Importante lembrar que  o repositório clonado conterá a pasta .git com as informações do projeto, inclusive, irá mostrar para onde está apontando (i.e. a origem dele), o que pode ser verificado entrando na pasta e digitando no GIT o comando ``git remote –v``. 


A segunda forma de autenticação segura é o _**token de acesso pessoal**_. O processo é um pouco parecido, porém sempre que é feito um commit, o GitHub vai pedir senha, que é o token de acesso propriamente dito. Para configurar:
 - No GitHub, clicar em _"Settings"_ e acessar _"Developer settings"_ no canto lateral inferior esquerdo da página, depois, clicar em _"Personal access token"_;
 - Em _"Generate new token"_, preencher o campo _"Note"_ e, caso seja conveniente, escolher tempo de validade do token. No campo _"Select scopes"_ é possível definir a que o token permitirá acesso. Uma explicação mais detalhada pode ser vista na seção [Scopes for OAuth Apps do GitHub](https://docs.github.com/pt/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps);
 - Clicar em _"Generate token"_, copiar e guardar a chave em local seguro para quando for usar.

### Criando um repositório do GitHub

Para criar um repositório, os seguintes passos devem ser executados:

 - Estando logado no GitHub, clicar em _"Repositories"_ e depois no botão _"New"_, abrirá a página para configuração do novo repositório;
 - Dar um nome ao repositório;
 - Adicionar uma descrição sobre o respositório no campo _"Description"_;
 - Escolher a visibiidade do repositório (_Public_ ou _Private_);
 - Caso o projeto ainda não tenha um arquivo README.md, deixar marcada a opção de _"Add a README.md"_;
 - A opção _"Add .gitignore template"_ permite criar um arquivo .gitignore que informa ao GitHub quais arquivos/pastas deve ignorar em um projeto. É recomendável criar este arquivo na pasta raíz do projeto, no [GitHub é possível consultar vários modelos deste arquivo](https://github.com/github/gitignore) ;
 - Em _"Choose a license"_ é possível escolher o tipo de licensa, que irá determinar o que pode ou não ser feito com o projeto (permissões de uso);
 - Clicar em _"Create"_.

### Transferindo repositório local para o GitHub

Estando o repositório local devidamente commitado e o repositório no GitHub criado, a transferência pode ser feita:

 - Copiar o endereço HTTPS do repositório criado no GitHub, este será usado para apontar a origem do repositório;
 - Digitar no GIT o comando ``git remote add origin linkdorespositorioGitHub``. _"Origin"_ é um apelido dado por convenção que permite que possa ser usado para referir-se ao link, dispensando assim a necessidade de digitar o endereço completo toda vez que o projeto precisar ser manipulado. Caso haja necessidade de conferir quais repositórios estão cadastrados, digitamos ``git remote -v``;
 - Para efetivamente os arquivos do projeto serem passados ao GitHub, digitar o comando ``git push origin master``;
 - O GIT pedirá autenticação, caso tenha sido usado um token, podemos inserir, se não, o login deve ser feito e deve ser confirmada a autorização de ecossistema.

Inspecionando o repositório no GitHub, os arquivos transferidos estarão lá. Um detalhe importante é que no canto da página aparecerá um número que informa o último commit, que é o início do SHA1 mencionado em [Como o GIT funciona](./como-git-funciona.md).

Ao clicar em _"commits"_, na mesma região da página, é possível ver o histórico dos commits realizados.

Importante ter em mente que o GitHub também segue o sistema de commits, porém, toda vez que novos processos forem realizados no repositório remoto, será preciso sincronizar os repositórios local / remoto.








